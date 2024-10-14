# Delete Pending

When we added support for multiple contract versions, we ran into the issue that the Biconomy Paymaster was not configured to allow the usage of the latest contract addresses. During testing we proposed a claim on testnet and effectively created a pending resource that we ended up manually deleting from Redis. We had to do this manually because we made the mistake to delete the post object first, which prevented the vote object from being deletable. So here are the two takeaways.

* Never delete the post object first. Always delete the vote object first.
* Use the curl script below against the \`post\` and \`vote\` APIs, given your personal JWT.

```bash
curl 
    -s 
    --request 'POST' 
    --header 'Authorization: Bearer JWT' 
    --header 'Content-Type: application/json' 
    --data '{
        "object":[
            {
                "intern":{
                    "id": "1727985384745039"
                }
            }
        ]
    }' 
    https://api.testnet.uvio.network/vote.API/Delete | jq .
```

```json
{
    "filter":null,
    "object":[
        {
            "intern":{
                "status":"deleted"
            },
            "public":null
        }
    ]
}
```
