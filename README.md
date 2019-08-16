# IR API Beta Documentation

## Authentication Setup
Setting up integration users: https://success.workiva.com/developers/guides/setup

Authentication Guide: https://success.workiva.com/developers/guides/authentication

## IR API
Base URL: `https://api.wk-dev.wdesk.org/audit/v1beta1/`

The Integrated Risk endpoints follow JSON:API (https://jsonapi.org).

### Issues
Endpoint for retriving and writing Issues.

The Issues object:
```
{
     “id”: “5400408f-14bf-483e-9a40-baed2bf22e07”,
     “type”: “issue”,
     “attributes”: {
       “alias”: null,
       “summary”: null,
       “description”: null,
       “date_reported”: null,
       “status”: “Not Started”,
       “management_response”: null,
       “severity”: “Medium”,
       “type”: “Material Weakness”,
     },
     “relationships”: {
       “issue_assignee”: {
         “data”: [
           {
             “id”: “32978542-1d20-4b9d-9c11-a678214699ff”,
             “type”: “user”,
           }
         ]
       },
       “reported_by”: {
         “data”: []
       },
       “exposed_in_procedure”: {
         “data”: []
       },
       “requested_by”: {
         “data”: []
       },
       “exposed_in_test_of_control”: {
         “data”: []
       },
       “indicates_issue_in_control”: {
         “data”: []
       }
```

#### GET `/issues`


#### PUT `/issues`


### Controls
Endpoint for retriving and writing Controls.

The Controls object:
```
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

#### GET `/controls`


#### PUT `/controls`


### Risks
Endpoint for retriving and writing Risks.

#### GET `/risks`


#### PUT `/risks`

