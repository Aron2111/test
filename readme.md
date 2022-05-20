If you want to start up Hasura localy on a docker follow this tutorial(after step 2 it's already done. Steps after 2 are for security so still recommended):
https://hasura.io/docs/latest/graphql/core/deployment/deployment-guides/docker/#introduction

for authentication / autherization check these toturials / docs:
    code:
    https://coding-bits.net/blog/hasura-login-docker
    explanation:
    https://hasura.io/docs/latest/graphql/core/auth/authentication/jwt/
    securing endpoint docs for docker / Heroku / Kubernetes / digital Ocean:
    https://hasura.io/docs/latest/graphql/core/deployment/securing-graphql-endpoint/


At this point the hasura console and enpoints are secured by a HASURA_GRAPHQL_ADMIN_SECRET in the docker-compose file.
if you want to use the console u have to give the correct secret this also applies to using the endpoints. So testing a enpoint means that if you use postman you have to ad x-hasura-admin-secret and the correct secret if you want to execute a Delete, Post or Put call.
Select calls are set to public by giving user named user unauthorized access but only access to select statements.
this is done with
```
HASURA_GRAPHQL_UNAUTHORIZED_ROLE: user
```

