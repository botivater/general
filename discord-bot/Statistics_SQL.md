# Statistics SQL queries

## Get the top 10 people who used the Discord bot
```sql
SELECT gm.name, COUNT(*) as invocations
FROM `discord-bot`.command_invocation as ci
JOIN `discord-bot`.guild_member as gm ON ci.guild_member_id = gm.id
GROUP BY guild_member_id
ORDER BY invocations DESC
LIMIT 10;
```
