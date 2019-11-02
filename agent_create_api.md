## Agent Creation

**Endpoint -** `POST {{server}}/api/v1/admin/accounts/{{accountID}}/agentGroups/{{agentGroupID}}/agents`

### Headers

| Header | Value |
|--------|-------|
| `Content-Type` | `application/JSON` |
| `X-Auth-Token` | {{Valid auth token}} |

### Body

#### Properties Notes

| Property | Description |
|----------|-------------|
| `username` | must be unique across the platform |
| `createdOn` | timestamp must be in the following ISO-8601 compliant format: YYYY-MM-DDTHH:MM:SS.MMM+0000, ex. 2019-10-09T19:29:09.249+0000 |
| `initLoginBaseStateId` | must be a valid base state ID number for the account that matches the above `initLoginBaseState` |
| `agentGroup` | must be a valid group ID number for the account |

#### Example

```JSON
{
  "agentId":0,
  "permissions":[

  ],
  "firstName":null,
  "lastName":null,
  "email":null,
  "username":"DesiredUsername",
  "password":"DesiredPassword",
  "defaultLoginDest":"",
  "altDefaultLoginDest":null,
  "lastLoginDate":null,
  "agentRank":0,
  "createdOn":"",
  "agentType":"AGENT",
  "maxChats":5,
  "externalAgentId":null,
  "directAgentExtension":null,
  "allowInbound":true,
  "allowOutbound":false,
  "allowExternalChat":false,
  "allowChat":false,
  "allowBlended":false,
  "allowChatVoiceConcurrent":false,
  "allowOffHook":false,
  "allowCallControl":true,
  "allowHold":true,
  "allowTransfer":true,
  "allowManualIntlTransfer":false,
  "allowDirectAgentTransfer":"DIRECT_TRANSFER_DISABLED",
  "allowHangup":true,
  "allowRequeue":true,
  "allowLoginControl":true,
  "allowLoginUpdates":true,
  "allowCrossGateRequeue":true,
  "gatesControlAgentVisibility":false,
  "allowCampStats":true,
  "allowGateStats":true,
  "allowAgentStats":true,
  "allowChatStats":true,
  "disableSupervisorMonitoring":false,
  "allowAgentReports":false,
  "allowManualCalls":true,
  "allowManualIntlCalls":false,
  "allowInboundIntlTransfer":false,
  "allowLeadInserts":false,
  "allowAutoAnswer":false,
  "defaultAutoAnswerOn":true,
  "isActive":true,
  "ghostRnaAction":"AVAILABLE",
  "loadBalanceEnabled":false,
  "transientAgent":false,
  "parentAgentId":null,
  "transientDelete":false,
  "transientDeleteDate":null,
  "phoneLoginPin":null,
  "multiAccountAgent":false,
  "initLoginBaseState":"AVAILABLE",
  "initLoginBaseStateId":1234,
  "enableSoftphone":false,
  "softphoneId":0,
  "allowFromIpAddresses":null,
  "location":null,
  "team":null,
  "showLeadHistory":true,
  "manualOutboundDefaultCallerId":"",
  "allowManualOutboundGates":false,
  "allowManualPass":true,
  "allowEndcallforeveryone":true,
  "allowHistoricalDialing":true,
  "rcUserId":null,
  "userManagedByRC":false,
  "gateAssignments":null,
  "chatQueueAssignments":null,
  "dialGroupAssignments":null,
  "agentAccountAccess":[

  ],
  "agentGateAccess":[

  ],
  "agentGateGroupAccess":[

  ],
  "agentChatGroupAccess":[

  ],
  "agentGroup":{
    "id":1234
  },
  "manualOutboundDefaultGate":null,
  "phoneLoginDialGroup":null,
  "agentSkillProfiles":null,
  "agentDialGroupMembers":[

  ],
  "agentChatQueueAccesses":[

  ],
  "agentLoadBalanceMembers":[

  ],
  "groupId":null,
  "agentLoadBalance":[

  ],
  "sipSafeUsername":null,
  "accountAccess":[

  ],
  "whereSupervisor":null,
  "whereSupervisee":[

  ],
  "active":true
}
```