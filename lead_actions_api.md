## Lead Actions API

### Endpoint

`PUT https://portal.vacd.biz/api/v1/admin/accounts/{{accountid}}/campaignLeads/actions?leadAction=SUPPRESS_LEADS`

Note: you can replace `SUPPRESS_LEADS` with other actions like `READY_LEADS`

### Headers

| Header | Value |
|--------|-------|
| `Content-Type` | `application/JSON` |
| `X-Auth-Token` | {{Valid auth token}} |

### Body

#### Example

```json
{
  "campaignLeadSearchCriteria":{
    "campaignId":"{{campaignId}}",
    "listIds":[

    ],
    "agentDispositions":[

    ],
    "systemDispositions":[

    ],
    "leadStates":[

    ],
    "physicalStates":[

    ],
    "leadTimezones":[

    ],
    "campaignIds":[

    ]
  },
  "leadActionParams":{
    "paramMap":{

    }
  }
}
```