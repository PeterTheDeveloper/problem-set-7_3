# Unit 7 Problem Set #3
## Schema Design and Building RESTful APIs

### Directions
1. Fork and clone this lab.
2. Answer the following questions directly in this README. Be sure that your answers are well-formatted. 
3. For the final question (build a to-do list), create all of your necessary app files in this directory. (I have included GitHub's standard Node.js `.gitignore` template so that you don't end up pushing `node_modules` to GitHub. 

## 

0. **What are the four types of HTTP requests that correspond to _creating_, _reading_, _updating_, and _deleting_ resources? Why is it important to use these  different types of requests?**
<br>

The four types of HTTP requests are POST, GET, PUT, and DELETE, respectivey. It is important for us to use these different types of requests because this is how we interact with
our application. It allows us to create a stateful application for the user. This means we save user data from a previous session or request and reuse/interact with it later
on in the application. If our users POST's data to our server, they should be able to retrieve ot GET it back from the server. Just as likely, they may want to update/PUT new
data into our servers, or DELETE it entirely.

1. **You've recently learned about an API for a cat sitting company. The API is fully RESTful for a resource called `cats`. You also happen to know that their database is running Postgresql on the backend. What are the five types of requests the API will respond to? Based on the description, list the HTTP method, the path, and what SQL the request will fire.**

| http method  |  path |  sql | description |
|---|---|---|---|
| POST | /add-cat | ```sql INSERT INTO cats (name, weight, color) VALUES ($1, $2, $3); ``` | Creating a cat |
| GET | /get-cats | ```sql SELECT * FROM cats; ``` | Retrieving all the cats |
| GET | /get-cat/:id | ```sql SELECT * FROM cats WHERE id = $1; ``` | Retriving a specific cat |
| PUT | /update-cat/:id | ```sql UPDATE cats SET (name, weight, color) = ($2, $3, $4) WHERE id = $1 ``` | Updating a specific cat |
| DELETE | /delete-cat/:id | ```sql DELETE FROM cats WHERE id = $1``` | Deleting a cat |

<br>

2. **You're working on a blogging application and doing some debugging. You see in the logs that the following SQL has fired:**

   ```sql
   SELECT * FROM articles WHERE id = 9;
   ```
   
   **Given that the application is RESTful, what HTTP method and request would you expect to have been made to fire that SQL?**
<br>

The HTTP method that would fire would be a GET request to the server. This will access our database and turn the data from the table where the id = 9.

3. **You've been hired to do some work for Discogs, an application to help users track a vinyl record collection. A `Collection` has many `Albums`, and an `Album` has many collections via a join table called `Ownership`. You've been asked to build a feature that allows to remove an album from their collection. What HTTP Method/URL/controller action would you use to implement this feature?**
<br>



4. **Choose your favorite web application. What's an example of a one-to-many and many-to-many relationship that might exist within the app?**
<br>

5. **Build a full CRUD, RESTful API using Express for a Todo List. A TodoList should have many items and belong to a user. Each endpoint should respond with the appropriate JSON response. Our API should support:**
   * **An index route to see a list of todos.**
   * **A show route to see details about an individual todo item.**
   * **The ability to update a todo (i.e. mark complete)**
   * **Delete a todo item**
   * **Create a Todo list item**

   **Deploy Your Project to Heroku and include a link here:**
