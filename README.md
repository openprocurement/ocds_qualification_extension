# Qualification
The extension provides information qualification process in tender.

## Overview
It adds new `Qualification` definition to OCDS release schema which extends `tender` block 
and consists of these fields:

 - `qualifications/id` - The unique id of the qualification. It must be string value.
 - `qualifications/status` - The status of the qualification. 
 It should be string value which must be one of these: `pending`, `active`, `unsuccessful`, 
 `cancelled`.
 - `qualifications/status` - In Multilot tenders, lot that this Qualification 
 protocol relates to. It should be string value.
 - `qualifications/description` - The description of the qualification. 
 It must be string value.
 - `qualifications/title` - The title of qualification. It should be string value.
 - `qualifications/eligible` - Yes/No field which confirms compliance of 
 eligibility criteria set by the procuring entity in the tendering documents. 
 It should be boolean field.
- `qualifications/qualified` - Yes/No field which confirms the absence of grounds for refusal to 
participate in accordance with Article 17 of the Law of Ukraine \"On Public Procurement\".
It should be boolean value.
- `qualifications/bidID` - The bid that this Qualification protocol relates to.
It should be string value.
- `qualifications/date` - The date of the qualification. It should be string value.
- `qualifications/documents` - The container for Qualification documentation, 
protocols, reasons for qualification or disqualification. Uploaded by tender committee.
It is an array of `Documents` objects.

There are other additional fields:
 - `tender/qualificationPeriod` - The timeframe when qualifications can be submitted.
 It is `Period` object.
 - `awards/qualified` - Yes/No field which confirms the absence of grounds for 
 refusal to participate in accordance with Article 17 of the Law of Ukraine 
 \"On Public Procurement\". It is boolean value.
 - `bids/selfQualified` - Yes/No field which confirms the absence of grounds 
 for refusal to participate in accordance with Article 17 of the Law of Ukraine 
 \"On public procurement\". It is boolean value.
 - `bids/qualificationDocuments` - Documents related to qualifications. 
 It is an array of `Document` objects.
 
 ## Example
 ```.env
{
   "tender": {
        "id": "SPA160032275",
        "qualifications": [
          {
            "id": "188be2cerrf61f2ea9dac914ffd85a1e",
            "status": "active",
            "lotID": "lot-1",
            "description": "Simple qualification",
            "title": "Qualification",
            "eligible": true,
            "qualified": true,
            "bidID": "1.0",
            "date": "2017-01-17T12:00:00+04:00",
            "documents": [
              {
                "language": "uk",
                "title": "Qualification.pdf",
                "url": "http://public.docs-sandbox.openprocurement.org/get/f8910e202a3f451a904ae67142358a74?KeyID=d8e133db&Signature=gWwLvym6za8Ii%252BfpoueQoftCtQSE4M%2FyyNKu%2FtLjuy96l%2FYJoH%252BUFQ4Up8YpoFnppZo1mHxGOuZ2XMOK49ZLDg%253D%253D",
                "format": "application/pdf",
                "datePublished": "2017-06-21T17:05:22.481301+03:00",
                "id": "95a16064160d49fe820a8bee63fff415",
                "dateModified": "2017-06-21T17:05:22.481335+03:00"
              }
            ]
          }
        ],
        "qualificationPeriod": {
          "startDate": "2017-01-12T12:00:00+04:00",
          "endDate": "2017-01-17T12:00:00+04:00"
        }
   },
   "awards": [
        {
          "id": "ocds-213czf-000-00001-award-01",
          "qualified": true
        }
      ],
   "bids": {
        "details": [
          {
            "id": "1.0",
            "selfQualified": true,
            "qualificationDocuments": {
              "id": "0007",
              "documentType": "notice",
              "title": "Qualification notice",
              "description": "Qualification",
              "url": "http://example.com/tender-qualification/ocds-213czf-000-00001-04.html",
              "datePublished": "2010-05-10T10:30:00Z",
              "format": "text/html",
              "language": "en"
            },
          },
        ]
      },     
}
```
