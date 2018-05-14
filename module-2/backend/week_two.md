## Week Two - Module 2 Recap

Fork or re-pull this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!). 

Note: When you're done, submit a PR.


### Week 2 Questions

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
ActiveRecord is an ORM or Object Relational Mapper. It is a toolset that allows you to interact with a database (create, modify, and query) using Ruby objects, rather than executing raw SQL.

2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?
Some methods you could call are
* Team.create (creates a new Team object and saves it to the database)
* team.update(params) (updates specific attributes of a specified team object)
* Team.destroy (removes a specified team object from the database)
* Team.select (allows you to to query the Team table in the database)

The Team class is inheriting methods from the ActiveRecord superclass, this brings in all of (or in this case, the Base sections) methods into the Team class.

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?
`Team.find(4)`

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?
Team.find(4).owner

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.
* A student would belong to a teacher
* Teachers would have many students

6. Define foreign key, primary key, and schema.
On the Students table, there would be a foreign_key of `teacher_id`, the primary_key would be `student_id`


7. Describe the relationship between a foreign key on one table and a primary key on another table.
* A foreign_key points to a primary_key on another table.

8. What are the parts of an HTTP response?
An HTTP response contains a HTTP Versions, path, and status_code on the same first line, then...
Optional Headers, then...
The body of the response. Usually HTML.


### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
2. Name your three favorite ActiveRecord rake tasks and describe what they do.
3. What two columns does `t.timestamps null: false` create in our database?
4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
6. Give an example of when you might want to store information besides ids on a join table.
7. Describe and diagram the relationship between patients and doctors.
8. Describe and diagram the relationship between museums and original_paintings.
9. What could you see in your code that would make you think you might want to create a partial?

### Self Assessment:
Choose One:
* I was able to answer every question without relying on outside resources
* I was able to answer most questions independently, but utilized outside resources for a few
* I was able to answer a few questions independently, but relied heavily on outside resources 

Choose One:
* I feel confident about the content presented this week
* I feel comfortable with the content presented this week
* I feel overwhelmed by the content presented this week
* I feel quite lost by the content presented this week
