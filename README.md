# Procurement method modalities

This extension adds a field for information on the modalities of procurement methods.

## Usage

A procurement method may be modulated in a variety of ways, for example: a buyer, in a competitive procedure with negotiation, may reserve the possibility of awarding contracts on the basis of the initial bids without negotiation.

The `tender/procurementMethodModalities` field should be used to indicate such modalities, using either `methodModality` or user-assigned codes.

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
    "procurementMethodModalities": [
      "joint",
      "negotiated"
    ]
  }
}
```

## Issues

Report issues for this extension in the [ocds-extensions repository](https://github.com/open-contracting/ocds-extensions/issues), putting the extension's name in the issue's title.
