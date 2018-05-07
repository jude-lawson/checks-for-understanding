## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!). 

Note: When you're done, submit a PR. 

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.
* GET - Requests a resource fron a server.
* POST - Sends a new resource to a server
* PUT - Updates part of a resource
* DELETE - Removes a resource
* PATCH - Updates part of a resource

2. What is Sinatra?
Sinatra is a web framework used for creating MVC web applications. It contains it's own server and routing logic/methods.

4. What is MVC?
MVC is the process by which modern web applications are developed. It stands for Model, View, and Controller.

5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
So that we can keep our paths defined to a standard, in this case RESTful standard. This allows us to easily organize and communicate our code.

6. What types of variables are accessible in our view templates without explicitly passing them?
Instance variables.

7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?
  
  ```ruby
  get '/horses' do
    erb :index
  end
  ```

   ```ruby
  get '/horses' do
    @count = 1
    erb :index
  end
  ```


8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?
 ```ruby
  get '/horses' do
    erb :index, locals: {name: 'Mr. Ed'}
  end
  ```
9. What's the purpose of ERB?
ERB (Embedded Ruby) is a templating language that allows us to dry up our HTML code as well as execute Ruby blocks of code/variables in our HTML views.

10. Why do I need a development AND test database?
The Test database is regulary cleared between tests, so to keep tests running with the same data, we need a databse that we can clear out and reuse for each test without affecting our actual development data.

11. What is CRUD and why is it important?
CRUD stands for Create, Read, Update, Delete. These functions are the basic functions for manipulating data in web applications.

12. What does HTTP stand for?
HyperText Transfer Protocol

13. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
We can utilize tags like <% RUBY HERE %> or like the <%= RUBY HERE %>. The former executes Ruby code but does not return values to the HTML, the latter executes the code and returns values to our HTML.

14. What's an ORM?
Object Relational Mapping. This is a method by which we could setup our data to work with our Ruby objects/methods.

15. What's the most commonly used ORM in ruby (Sinatra & Rails)?
ActiveRecord

16. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
GET /restaurants - gets all restaurants
GET /restaurant/:id - gets a specific restaurant
POST /restaurant/:id - creates a new restaurant
PUT /restaurants/:id - edits a new restaurant
DELETE /restaurants/:id - removes a restaurant from the database


17. What's a migration?
A migration is a set of logic the formats part of a database, such as creating a new table or adding a column to the table.

18. When you create a migration, does it automatically modify your database?
No, it has to be run.

19. How does a model relate to a database?
A model interacts directly with the data in the database and sends that processed information back to the controller.

20. What is the difference between `#new` and `#create`?
`#new` creates a new object, but does not save it to the databse. `#create` does both.

### Review Questions:  
21. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?
* Create a migration to create a films table with columns for id, title, and description.
* Read in the CSV file as a hash, and then enumerate through each film using enumerable like the one below:
```ruby
films.each do |film|
  Film.create(id: film[:id],
              title: film[:title],
              description: film[:description])
end
```
22. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone'],
  brunch: {cost: $35, supplies: ['mimosa flutes'],
  antiquing: {cost: $200, supplies: ['list of antique stores'] 
}
```
How would I add 'granola bar' to things you should have when hiking?

```ruby
activities[:hiking][:supplies] << 'granola bar'
```
23. What are the 4 Principles of OOP? Give a one sentence explanation of each.


### Self Assessment:
Choose One:
* I was able to answer every question without relying on outside resources (with the exception of the few questions left unanswered toward the end)

Choose One:
* I feel confident about the content presented this week
