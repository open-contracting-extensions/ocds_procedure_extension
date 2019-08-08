# Procedure 0.4.0

This extension adds a block to decribe the procedure.

## Usage

The core OCDS field `procurementMethod` broadly describes the type of method. In order to describe the procedure is more specific terms, this extension adds the `procurementMethodName`. The code list (`codelists/procurementProcedureName.csv`) for this field is inspired by the European eForms directive, but it's also compatible with TED forms and aims at supporting the broadest possible range of use cases, even in non-European contexts.

The term "method" used in this documentation corresponds to the term "procedure" in European legislation.

## Guidance

The `procurementMethod` and `procurementMethodName` are closely related. Here is a table that summarizes how method name and methods are related.

| `procurementMethodName` code | `procurementMethod` code                                     |
| ---------------------------- | ------------------------------------------------------------ |
| `open`                       | `open`                                                       |
| `restricted`                 | `selective`                                                  |
| `negotiatedWithCFC`          | `selective`                                                  |
| `competitiveDialogue`        | `selective`                                                  |
| `innovationPartnership`      | `selective`                                                  |
| `otherMultipleStage`         | Usually `selective`                                          |
| `negotiatedWithoutCFC`       | `limited` (or `direct` depending on the number of tenderers) |
| `otherSingleStage`           | Depends on the procedure                                     |

## Legal context

The [Revised Agreement on Government Procurement](https://www.wto.org/english/docs_e/legal_e/rev-gpr-94_01_e.htm) (GPA) includes: "each notice of intended procurement shall include … f. the procurement method that will be used and whether it will involve negotiation or electronic auction".

The European Union's [Directive 2014/24/EU](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=uriserv:OJ.L_.2014.094.01.0065.01.ENG) (Public contracts — setting out clear ground rules) includes:

* "Article 29(4) Contracting authorities may award contracts on the basis of the initial tenders without negotiation where they have indicated, in the contract notice or in the invitation to confirm interest, that they reserve the possibility of doing so."
* "Article 29(6) Competitive procedures with negotiation may take place in successive stages in order to reduce the number of tenders to be negotiated by applying the award criteria specified in the contract notice, in the invitation to confirm interest or in another procurement document. In the contract notice, the invitation to confirm interest or in another procurement document, the contracting authority shall indicate whether it will use that option."
* "Article 30(4) Competitive dialogues may take place in successive stages in order to reduce the number of solutions to be discussed during the dialogue stage by applying the award criteria laid down in the contract notice or in the descriptive document. In the contract notice or the descriptive document, the contracting authority shall indicate whether it will use that option."
* "Article 31(5) Negotiations during innovation partnership procedures may take place in successive stages in order to reduce the number of tenders to be negotiated by applying the award criteria specified in the contract notice, in the invitation to confirm interest or in the procurement documents. In the contract notice, the invitation to confirm interest or in the procurement documents, the contracting authority shall indicate whether it will use that option."
* "Part C: Information to be included in contract notices … 4. Where appropriate, indication that … any other form of joint procurement is involved."
* "Part C: Information to be included in contract notices … 13. Where appropriate, indication whether: … (c) an electronic auction is involved"

## Example

```json
{
  "tender": {
        "procedure": {
            "name": "innovativePartnership",
            "hasAcceleratedProcedure": true,
            "acceleratedProcedureRationale": "The medicinal  product  is  of  major  public  health  interest  particularly from the point of view of therapeutic innovation.",
        }
    }
}
```

## Issues

Report issues for this extension in the [ocds-extensions repository](https://github.com/open-contracting/ocds-extensions/issues), putting the extension's name in the issue's title.

## Release notes

### 0.4.0

- Renamed the extension "procedure"
- Nested the fields into a `Procedure` object
- removed:
    - `stagedProcedure`
    - `noNegotiationNecessary` (=> [secondStage extension](https://github.com/open-contracting-extensions/ocds_secondStage_extension))
    - `bidOpeningPlace` (=> bid opening extension)
    - `bidOpeningProcedure` (=> bid opening extension)
    - `recurrentProcurement` (=> purpose)
    - `recurrentProcurementDetails` (=> purpose)
    - `invitationsForInterestDispatchDate` (=> communication)
    - `invitationsForBidDispatchDate` (=> communication)
    - the `procurementMethodName` code list (=> [EU extension](https://github.com/open-contracting-extensions/ocds_eu_extension))

### 0.3.0

- Removed the `procurementMethodModalities` and the related code list entirely
    - the `joint` modality can be expressed by adding more buyers in the `parties` array.
    - the `staged` modality can be expressed with the `stagedProcedure` boolean

### 0.2.0

- Added the `procurementMethodName` and its code list, based on the eForms directive
- Removed most of the modalities:
    - redundant with other OCDS core properties
    - `negotiated` and `optionallyNegotiated`: replaced with relevant codes in the `procurementMethodName` code list
    - `accelerated`: replaced with `acceleratedProcedure`
    - `electronicAuction`: moved to the `electronicAuction` field in the [procurement technique extension](https://github.com/open-contracting-extensions/ocds_procurement_techniques_extension) in order to distinguish method and technique terms


### 0.1.0

Method modalities field and code list.
