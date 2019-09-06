# IR API Beta Documentation

## Authentication Setup
Setting up integration users: https://success.workiva.com/developers/guides/setup

Authentication Guide: https://success.workiva.com/developers/guides/authentication

## IR API
Base URL: `https://api.app.wdesk.com/audit/v1beta1/`

The Integrated Risk endpoints follow JSON:API specification (https://jsonapi.org).

### Issues
Endpoint for retriving and writing Issues.

##### GET `/issues`

Example Issues reponse:
```javascript
{
  "data": [
    {
      "id": "b98dedff-393e-44d7-91c3-a222243978f3",
      "type": "issue",
      "attributes": {
        "alias": "Full Issue",
        "summary": "This is an example summary",
        "description": "This is an example description",
        "date_reported": "",
        "status": "not_started",
        "management_response": "this is a mgmt response",
        "severity": "material_weakness",
        "issue_type": "design"
      },
      "relationships": {
        "issue_assignee": {
          "data": [
            {
              "id": "cd7a496b-ed98-4658-841e-928d4ea81085",
              "type": "user"
            }
          ]
        },
        "reported_by": {
          "data": [
            {
              "id": "cd7a496b-ed98-4658-841e-928d4ea81085",
              "type": "user"
            }
          ]
        },
        "exposed_in_procedure": {
          "data": []
        },
        "requested_by": {
          "data": []
        },
        "exposed_in_test_of_control": {
          "data": [
            {
              "id": "268c448d-4947-48a7-bdf8-32d4f8d6db55",
              "type": "test_of_control"
            },
            {
              "id": "e8261015-d8f0-4498-b201-79b4127dac99",
              "type": "test_of_control"
            }
          ]
        },
        "indicates_issue_in_control": {
          "data": [
            {
              "id": "6046178d-818b-46bc-b613-cad043d3ef2d",
              "type": "control"
            },
            {
              "id": "050eee4b-24c6-409b-a64f-f6e3f4a14a99",
              "type": "control"
            }
          ]
        }
      }
    }
  ],
  "included": [
    {
      "id": "cd7a496b-ed98-4658-841e-928d4ea81085",
      "type": "user",
      "attributes": {
        "name": "Jade Robbins"
      }
    },
    {
      "id": "268c448d-4947-48a7-bdf8-32d4f8d6db55",
      "type": "test_of_control",
      "attributes": {
        "alias": "C.AP.08 - Wire Transfers 2018"
      }
    },
    {
      "id": "e8261015-d8f0-4498-b201-79b4127dac99",
      "type": "test_of_control",
      "attributes": {
        "alias": "C.ELC.31 - SOX 2018"
      }
    },
    {
      "id": "6046178d-818b-46bc-b613-cad043d3ef2d",
      "type": "control",
      "attributes": {
        "alias": "C.ELC.30,,"
      }
    },
    {
      "id": "050eee4b-24c6-409b-a64f-f6e3f4a14a99",
      "type": "control",
      "attributes": {
        "alias": "Full Control"
      }
    }
  ]
}
```

### Controls
Endpoint for retriving and writing Controls.

##### GET `/controls`
Example Controls Response:
```javascript
{
  "data": [
  {
      "id": "050eee4b-24c6-409b-a64f-f6e3f4a14a99",
      "type": "control",
      "attributes": {
        "alias": "Full Control",
        "summary": "Summary of control",
        "description": "description of control",
        "creation_notes": "",
        "automated_or_manual": "automated",
        "performed_in_location": "Bridger Bowl"
      },
      "relationships": {
        "performed_at_frequency": {
          "data": [
            {
              "id": "36fc04ad-da8f-4054-ae93-aa3b889d19e1",
              "type": "frequency"
            }
          ]
        }
      }
    }
   ],
  "included": [
    {
      "id": "36fc04ad-da8f-4054-ae93-aa3b889d19e1",
      "type": "frequency",
      "attributes": {
        "value": "Annually",
        "population_size": "12345"
      }
    }
  ]
}
```

### Risks
Endpoint for retriving and writing Risks.

##### GET `/risks`
Example Risks response: 
```javascript
{
  "data": [
  {
      "id": "eee1f417-985e-4e89-8288-856be409c21a",
      "type": "risk",
      "attributes": {
        "title": "Accrued liability balances are understated or incorrect on the balance sheet; period expenses are not recognized.",
        "description": ""
      },
      "relationships": {
        "exposes_assertions": {
          "data": []
        },
        "incurred_by_processes": {
          "data": []
        }
      }
    }
  ],
  "included": []
}
```
