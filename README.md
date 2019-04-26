# example code from

<https://engineering.thinknet.co.th/หัดเขียน-api-service-ด้วย-graphql-part-2-bdbb4eea9beb>

## how to run

- start mongodb first
- `npm install`
- `yarn dev`
- open http://localhost:4000/graphiql

## create team

```graphql
mutation{
    createTeam(
        input: {
            team: {
                fullname: "Chelsea Football Club"
                shortname: "CFC"
                nickname: "The Blues"
                founded: "March 10, 1905"
                stadium: "Stamford Bridge"
                owner: "Roman Abramovich"
                manager: "Antonio Conte"
            }
        }
    ){
        meta{
            status
            message
        }
        data{
            _id
            fullname
            shortname
            nickname
            founded
            stadium
            capacity
            owner
            manager
            created_at
            updated_at
        }
        errors{
            code
            message
        }
    }
}
```

## search team

```graphql
query{
    teams(
        input: {
            keyword: "chelsea"
        }
    ){
        meta{
            status
            message
            total
            per_page
            current_page
            last_page
        }
        data{
            _id
            fullname
            shortname
            nickname
            founded
            stadium
            capacity
            owner
            manager
            created_at
            updated_at
        }
        errors{
            code
            message
        }
    }
}
```
