# Command Flows

## Building blocks
| Number | Building block name |
| ------ | ------------------- |
| 0      | None                |
| 1      | Send message        |
| 2      | Add role            |
| 3      | Remove role         |

## Building block options

### Building block: None
No options.

### Building block: Send message
```json
{
  "toType": 0,
  "to": "",
  "messageFormat": ""
}
```

`toType`:
- 0: SENDER  
Send a message to the person who reacted.
- 1: USER  
Send a message to a specific user.  
When using this type, specify the `to` option.
- 2: CHANNEL  
Send a message to a specific channel.  
When using this type, specify the `to` option.

`messageFormat`:
This specifies the format of the message to send to the user.  
Examples:
- Welcome to the server, Jonas Claes!
  ```handlebars
  Welcome to the server, {{ guildMember.nickname }}!
  ```
- Thank you for reacting, Jonas Claes!
  ```handlebars
  Thank you for reacting, {{ guildMember.nickname }}!
  ```
- Welcome to Friendship Bubble!, Jonas Claes!
  ```handlebars
  Welcome to {{ guild.name }}, {{ guildMember.nickname }}!
  ```
  
### Building block: Add role
```json
{
  "roleId": "",
}
```

`roleId`:
This is the ID of the role to add to the user that reacted.

### Building block: Remove role
```json
{
  "roleId": "",
}
```

`roleId`:
This is the ID of the role to remove from the user that reacted.
