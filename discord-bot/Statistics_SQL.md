# Statistics SQL queries

## Get the top 10 people who used the Discord bot
```sql
SELECT
	gm.name,
    COUNT(*) as invocations
FROM `discord-bot`.command_invocation as ci
JOIN `discord-bot`.guild_member as gm ON ci.guild_member_id = gm.id
WHERE DATE(ci.created_at) > '2022-01-01' AND DATE(ci.created_at) < '2022-02-01'
GROUP BY guild_member_id
ORDER BY invocations DESC
LIMIT 10;
```
