# Direct Lead Loader

Leads > Direct Lead Loader

**NOTE -** Comments are not valid in JSON, you will need to remove them before sending these requests.

**Endpoint:** - `POST {{ server }}/api/v1/admin/accounts/{{ accountId }}/campaigns/{{ campaignId }}/leadLoader/direct`

**Headers:**

| Header | Value |
|--------|-------|
| `Content-Type` | `application/json` |
| `X-Auth-Token` | Connect First authentication token |

**Parameters:**

| Property | Type | Description |
|----------|------|-------------|
| `duplicateHandling` | string, enum | also be: `REMOVE_ALL_EXISTING` or `REMOVE_FROM_LIST` |
| `timeZoneOption` | string, enum | an also be: `ZIPCODE` or `EXPLICIT` |
| `dialPriority` | string | allows you to insert a lead to the top of the dialer cache for immediate dialing if you want a normal insert then do not add this parameter. |
| `uploadLeads` | multiple lead objects can be uploaded in the `uploadLeads` array. |
| `lead.leadPhone` | string | piped leads canb be sent, e.g. - "leadPhone": "8888888888|8888888888" |
| `lead.externId` | integer | required field |

```json
{
   "listState":"ACTIVE",
   "duplicateHandling":"RETAIN_ALL",
   "timeZoneOption":"NPA_NXX",
   "description":"(list name goes here)",
   "dialPriority":"IMMEDIATE",
   "uploadLeads":[
      {
         "leadPhone":"8888888888",
         "externId":1,
         "title":"Dr.",
         "firstName":"Jeff",
         "midName":"John",
         "lastName":"Malfetti",
         "suffix":"Jr.",
         "address1":"3101 Fake St.",
         "address2":"Suite 120",
         "city":"Rock",
         "state":"CO",
         "zip":"80500",
         "email":"test@test.com",
         "gateKeeper":"Some one",
         "auxData1":30,
         "auxData2":"a",
         "auxData3":100,
         "auxData4":"aa",
         "auxData5":1000,
         "auxPhone":8888888888,
         "extendedLeadData":{
            "important":"data",
            "interested":true
         }
      }
   ],
   "dncTags":[

   ]
}
```