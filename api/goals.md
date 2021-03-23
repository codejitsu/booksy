| Whos        | Whats                        | Hows                         |   Inputs (source)                    | Outputs (usage)      | Goals       | Example | 
| ----------- |----------------------------- | ---------------------------- | ------------------------------------ | ------------ | ------------- | ---------------|
| Users       | Manage account  | Register account | User name (provided by user) | Account | Register account | POST /users/
| Users       |   | Log in | User name (provided by user) | Account (manage collections) | Log in user | POST /auth/
| Users       | Manage collections  | List collections | User name (provided by user) |  Collections (open collection) | List collections | GET /collections/
| Users       |  | Look up collection by name | Collection name (provided by user) |  Collections (open collection) | Look up collection | GET /collections/?name=text
| Users       |   | Create collection | Collection name |  New collection (provided by user) | Create collection | POST /collections
| Users       |   | Delete collection | Collection id (provided by user) | Collection details  | Delete collection | DELETE /collections/812ba8b7-60cb-41fd-8629-b73c60c0f01f
| Users       |   | Open collection | Collection id (provided by user) | Collection details  | Open collection | GET /collections/812ba8b7-60cb-41fd-8629-b73c60c0f01f
| Users       | Register materials in collection  | Add book to given collection | Collection (manage collection), book information  (provided by user) |  Registered book | Register book in collection | POST /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books
| Users       |  | Add e-book to given collection | Collection (manage collection), e-book information  (provided by user) |  Registered e-book | Register e-book in collection | POST /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/e-books
| Users       |  | Add video to given collection | Collection (manage collection), video information  (provided by user) |  Registered video | Register video in collection | POST /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/videos
| Users       |  | Remove item from given collection | Collection (manage collection), item ID (provided by user) |  Deleted item | Delete item from collection | DELETE /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1
| Users       | Manage materials | Mark book as currently reading | Collection (manage collection), book ID |  Book in new status | Mark book as currently reading | PATCH /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1
| Users       | | Mark e-book as currently reading | Collection (manage collection), e-book ID |  E-Book in new status | Mark e-book as currently reading | PATCH /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/e-books/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1
| Users       | | Mark video as currently watching | Collection (manage collection), video ID |  Video in new status | Mark video as currently watching | PATCH /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1
| Users       | | Mark item as finished | Collection (manage collection), item ID | Item in new status | Mark item as finished | PATCH /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1
| Users       | | Get history for item | Collection (manage collection), item ID | Item's history | Get item's history | GET /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/history
| Users       | | Add tag | Collection (manage collection), material ID |  Material with tag | Add tag to material | POST /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/tags
| Users       | | List tags | Collection (manage collection), material ID | List of tags | List tags for material | POST /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/tags
| Users       | | Remove tag | Collection (manage collection), material ID, tag ID |  Material without tag | Remove tag to material | DELETE /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/tags/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1
| Users       | | Add comment | Collection (manage collection), material ID |  Material with comment | Add comment | POST /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/comments
| Users       | | Get comments | Collection (manage collection), material ID |  Material with comments | Get comments | GET /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/comments
| Users       | | Delete comment | Collection (manage collection), material ID, comment ID |  Material without comment | Delete comment | DELETE /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/comments/3305fa5a-f70a-4dd2-aebc-02b8b9a82bea
| Users       | | Mark book as read next | Collection (manage collection), book ID |  Book in new status | Mark book as read next | POST /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/lists/ReadNext
| Users       | | Unmark book as read next | Collection (manage collection), book ID |  Book in new status | Unmark book as read next | DELETE /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/lists/ReadNext
| Users       | Explore collection | Filter by tags | Collection (manage collection), tag names (provided by user) |  List of materials | Filter by tags | GET /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/?tags=tag1,tag2
| Users       | | Filter by status | Collection (manage collection), status (provided by user) |  List of materials | Filter by status | GET /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/?status=borrowed
| Users       | | Get materials by type | Collection (manage collection) |  List of materials | Get materials by type | GET /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/
| Users       | | Get all items | Collection (manage collection) |  List of materials | Get all materials | GET /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/all/
| Users       | | Look up items in collection |  Collection (manage collection), free query (provided by user) |  List of materials across in collection | Look up items in collection | GET /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos,all?free-query=text
| Users       | Search items | Look up items | Free query (provided by user) |  List of materials across all collections | Look up items | GET /collections/all/books,e-books,videos,all?free-query=text
| Users       | Find items on external service | External search with free query | Free query (provided by user), service name (provided by user) |  Matching materials found on external service | Find items on external service | GET /services/goodreads/?free-query=text
| Users       | Read item from external service by id | External search by ID | ID (provided by user), service name (provided by user) |  Matching material found on external service | Read item from external service | GET /services/goodreads/3305fa5a-f70a-4dd2-aebc-02b8b9a82bea
| Users       | Manage quotes | Add quote | Collection, item, quote | Created quote | Add quote from item | POST /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/quotes
| Users       |  | Get quotes | Collection, item | List of quotes | List quotes | GET /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/quotes
| Users       |  | Delete quotes | Collection, item, quote ID | Deleted quote | Delete quote | DELETE /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/quotes/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1
| Users       | Manage borrowed items | Borrow item | Collection, item, free text for whom the item borrowed to | Borrowed item | Borrow item | PATCH /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1
| Users       |  | Return borrowed item | Collection, item | Returned item | Return item | PATCH /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1

### Assumptions
* no authentication/authorization for time being
* Material statuses:
  * Registered
  * Currently in use (reading/watching)
  * Finished
  * Deleted
  * Borrowed (for print books)