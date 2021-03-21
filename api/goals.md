| Whos        | Whats                        | Hows                         |   Inputs (source)                    | Outputs (usage)      | Goals       | Example | 
| ----------- |----------------------------- | ---------------------------- | ------------------------------------ | ------------ | ------------- | ---------------|
| Users       | Manage account  | Register account | User name (provided by user) | Account | Register account | POST /users/
| Users       |   | Log in | User name (provided by user) | Account (manage collections) | Log in user | POST /auth/
| Users       | Manage collections  | List collections | User name |  Collections (open collection) | List collections | GET /collections/
| Users       |  | Look up collection by name | Collection name (provided by user) |  Collections (open collection) | Look up collection | GET /collections/?name=text
| Users       |   | Create collection | Collection name |  New collection (provided by user) | Create collection | POST /collections
| Users       |   | Delete collection | Collection id (provided by user) |   | Delete collection | DELETE /collections/812ba8b7-60cb-41fd-8629-b73c60c0f01f
| Users       |   | Open collection | Collection id (provided by user) |   | Open collection | GET /collections/812ba8b7-60cb-41fd-8629-b73c60c0f01f
| Users       | Register materials in collection  | Add book to given collection | Collection (manage collection), book information  (provided by user) |  Registered book | Register book in collection | POST /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books


### Assumptions
* no authentication/authorization for time being