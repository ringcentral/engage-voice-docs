## Add to DNC API

### Endpoint

`POST {{ server }}/api/v1/admin/accounts/{{ accountID }}/dncLists`

### Headers

| Header | Value |
|--------|-------|
| `Content-Type` | `application/JSON` |
| `X-Auth-Token` | {{Valid auth token}} |

### Body

#### Properties Notes

| Property | Description |
|----------|-------------|
| `dncTag` | Note that you can use a specific DNC tag if desired, but default account-wide tag is ID 0 and tag GLOBAL. |

#### Example

```json
{
  "dncTag":{
    "dncTagId":0,
    "dncTagLabel":"GLOBAL"
  },
  "countryCode":{
    "id":"USA"
  },
  "phone":"8888888888",
  "tag":"GLOBAL",
  "dncTagId":0
}
```