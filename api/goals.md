| Whos        | Whats                        | Hows                         |   Inputs (source)                    | Outputs (usage)      | Goals  | Status     | Example | 
| ----------- |----------------------------- | ---------------------------- | ------------------------------------ | ------------ | ------------- | ---------------|---------------|
| Users       | **Manage account**  | *Register account* | User name (provided by user) | Account | Register account || POST /users/
| Users       |  | *Log in* | User name (provided by user) | Account (manage collections) | Log in user || POST /auth/
| Users       | **Manage collections**  | *List collections for user* | User name (provided by user) |  Collections (open collection) | List collections || GET /collections/
| Users       |  | *Look up collection by name* | Collection name (provided by user) |  Collections (open collection) | Look up collection || GET /collections/?name=text
| Users       |  | *Create collection* | Collection name |  New collection (provided by user) | Collection details || POST /collections
| Users       |  | *Delete collection* | Collection id (provided by user) | Deleted collection details  | Delete collection || DELETE /collections/812ba8b7-60cb-41fd-8629-b73c60c0f01f
| Users       |  | *Open collection* | Collection id (provided by user) | Collection details  | Open collection || GET /collections/812ba8b7-60cb-41fd-8629-b73c60c0f01f
| Users       | **Register material in system**  | *Add book* | Book information  (Import from external service) |  Registered book | Register book in system |✅| POST /books/
| Users       |  | *Add e-book* | E-Book information  (Import from external service) |  Registered e-book | Register e-book in system |✅| POST /books/
| Users       |  | *Add video* | Video information  (Import from external service) |  Registered video | Register video in system |✅| POST /videos/
| Users       | **Remove material from system**  | *Remove book* | Book ID (Internal search) |  Removed book | Remove book from system |✅| DELETE /books/812ba8b7-60cb-41fd-8629-b73c60c0f01f
| Users       |  | *Remove e-book* | E-Book ID (Internal search) |  Removed e-book | Remove e-book from system |✅| DELETE /books/812ba8b7-60cb-41fd-8629-b73c60c0f01f
| Users       |  | *Remove video* | Video ID (Internal search) |  Removed video | Remove video from system |✅| DELETE /videos/812ba8b7-60cb-41fd-8629-b73c60c0f01f
| Users       | **Add material reference to collection**  | *Add book to given collection* | Collection (manage collection), book information  (provided by user) ||  Registered book | Register book in collection | POST /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books
| Users       |  | *Add e-book to given collection* | Collection (manage collection), e-book information  (provided by user) |  Registered e-book | Register e-book in collection || POST /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/e-books
| Users       |  | *Add video to given collection* | Collection (manage collection), video information  (provided by user) |  Registered video | Register video in collection || POST /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/videos
| Users       |  | *Remove item from given collection* | Collection (manage collection), item ID (provided by user) |  Deleted item | Delete item from collection || DELETE /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1
| Users       | **Manage materials** | *Mark book as currently reading* | Collection (manage collection), book ID |  Book in new status | Mark book as currently reading || POST /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/list/CurrentlyReading
| Users       |  | *Mark e-book as currently reading* | Collection (manage collection), e-book ID |  E-Book in new status | Mark e-book as currently reading || POST /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/e-books/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/lists/CurrentlyReading
| Users       |  | *Mark video as currently watching* | Collection (manage collection), video ID |  Video in new status | Mark video as currently watching || POST /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/lists/CurrentlyWatching
| Users       |  | *Mark item as finished* | Collection (manage collection), item ID | Item in new status | Mark item as finished || POST /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/lists/Finished
| Users       |  | *Get history for item* | Collection (manage collection), item ID | Item's history | Get item's history || GET /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/history
| Users       | | *Add tag to an item* | Collection (manage collection), material ID, tag ID |  Material with tag | Add tag to material || POST /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/tags
| Users       | | *List tags* | Collection (manage collection), material ID | List of tags | List tags for material || GET /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/tags
| Users       | | *Remove tag* | Collection (manage collection), material ID, tag ID |  Material without tag | Remove tag to material || DELETE /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/tags/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1
| Users       | | *Add comment* | Collection (manage collection), material ID, comment data |  Material with comment | Add comment || POST /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/comments
| Users       | | *Get comments* | Collection (manage collection), material ID | List of comments | Get comments || GET /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/comments
| Users       | | *Delete comment* | Collection (manage collection), material ID, comment ID |  Material without comment | Delete comment || DELETE /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/comments/3305fa5a-f70a-4dd2-aebc-02b8b9a82bea
| Users       | | *Mark book as read next* | Collection (manage collection), book ID |  Book in new status | Mark book as read next || PATCH /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1
| Users       | | *Unmark book as read next* | Collection (manage collection), book ID |  Book in new status | Unmark book as read next || PATCH /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1
| Users       | | *Add author to item* | Collection (manage collection), item ID, author ID |  Item with author | Add author to item || POST /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/authors
| Users       | | *Remove author from item* | Collection (manage collection), item ID, author ID |  Item without author | Remove author from item || DELETE /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/authors/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1
| Users       | | *List authors for item* | Collection (manage collection), item ID |  List of authors | List of authors || GET /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/authors
| Users       | **Explore collection** | *Filter by tags* | Collection (manage collection), tag names (provided by user) |  List of materials | Filter by tags || GET /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos,all/?tags=tag1,tag2
| Users       | | *Filter by status* | Collection (manage collection), status (provided by user) |  List of materials | Filter by status || GET /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos,all/?status=borrowed
| Users       | | *Get materials by type* | Collection (manage collection), type (provided by user) |  List of materials | Get materials by type || GET /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos,all/
| Users       | | *Get all items* | Collection (manage collection) |  List of materials | Get all materials || GET /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/all/
| Users       | | *Look up items in collection* |  Collection (manage collection), free query (provided by user) |  List of materials across in collection | Look up items in collection || GET /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos,all/?free-query=text
| Users       | **Search items** | *Look up items* | Free query (provided by user) |  List of materials across all materials | Look up items || GET /books,videos/?free-query=text
| Users       | | *Look up items by author* | Author ID (provided by user) |  List of materials by author | List items by author || GET /books,videos/authors/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/
| Users       | | *Look up items by tag* | tag ID (provided by user) |  List of materials by type | Search items by tag || GET /books,videos/tags/1acdbf6f-05ac-45a7-9ddd-6f392e06079a
| Users       | **Import materials** | *External search with free query* | Free query (provided by user), service name (provided by user) |  Matching materials found on external service | Find items on external service || GET /services/google/?free-query=text
| Users       | | External retrieval by ID | ID (provided by user), service name (provided by user) |  Matching material found on external service | Read item from external service || GET /services/google/3305fa5a-f70a-4dd2-aebc-02b8b9a82bea
| Users       | **Manage quotes** | *Add quote* | Collection, item, quote | Created quote | Add quote from item || POST /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/quotes
| Users       |  | *Get quotes* | Collection, item | List of quotes | List quotes || GET /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/quotes
| Users       |  | *Delete quotes* | Collection, item, quote ID | Deleted quote | Delete quote || DELETE /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books,e-books,videos/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1/quotes/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1
| Users       | **Manage borrowed items** | *Borrow item* | Collection, item, free text for whom the item borrowed to | Borrowed item | Borrow item || PATCH /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1
| Users       |  | *Return borrowed item* | Collection, item | Returned item | Return item || PATCH /collections/1acdbf6f-05ac-45a7-9ddd-6f392e06079a/books/ee09dc1b-3b8c-467b-a4d0-b985f5622bc1
| Users       | **Manage authors** | *Add new author* | Author data (provided by user) | New author | Add new author || POST /authors
| Users       | | *Get author* | Author ID (provided by user) | Author details | Get author || GET /authors/1acdbf6f-05ac-45a7-9ddd-6f392e06079a
| Users       | | *Delete author* | Author ID (provided by user) | Deleted author | Delete author || DELETE /authors/1acdbf6f-05ac-45a7-9ddd-6f392e06079a
| Users       | | *Search authors* | Free query (provided by user) | List of matching authors | Search authors || GET /authors/?free-query=text
| Users       | **Manage tags** | Add new tag | Tag name (provided by user) | New tag | Add new tag || POST /tags
| Users       | | *Get tag* | Tag ID (provided by user) | Tag details | Get tag || GET /tags/1acdbf6f-05ac-45a7-9ddd-6f392e06079a
| Users       | | *Delete tag* | Tag ID (provided by user) | Deleted tag | Delete tag || DELETE /tags/1acdbf6f-05ac-45a7-9ddd-6f392e06079a
| Users       | | *Search tags* | Free query (provided by user) | List of matching tags | Search tags || GET /tags/?free-query=text
### Assumptions
* no authentication/authorization for time being
* Material statuses:
  * Registered
  * Currently in use (reading/watching)
  * Finished
  * Deleted
  * Borrowed (for print books)
* An item can belong to multiple collections by reference
  * There should be a method to list all collections the given item belongs to

- :white_check_mark: — the goal has been designed
- :dizzy: — the goal has been implemented
- :sweat: — working on it