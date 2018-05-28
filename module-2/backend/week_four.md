## Week Four Recap

### Instructions
Fork or re-pull this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 4 Questions

1. What is a cookie?
* A cookie is a small piece of data used by the browser to pass some information about a user's browsing. Normally, it is used to identify/restore a user's session.

2. What’s the difference between a session and a cookie?
* A session has specific information about a user's time on a certain site and can store much more information. A cookie is much smaller and is usually only used as an identifier of the user.

3. What’s a flash and when do you want to use flashes?
* Flashes are messages that appear on a page after the user takes some action. They are not always present and traditionally appear at the top of a page, under the navigation bar.

4. Why do people say “HTTP is stateless”?
* People say HTTP is stateless because an HTTP request/response cycle is ephemeral. It does not retain information about the user.

5. What’s authentication? Explain.
* Authentication is the process of establishing who a user is. Usually via login credentials or a session's user_id key.

6. What’s the difference between authentication and authorization?
While authentication identifies who the user is (who are they), authorization determines what level of access a user has (what the user can do).

7. What’s a before filter?
* A before filter requires that a user have a certain level of authorization before an authorization can be run.

8. How do we keep track of a user once they’ve logged in?
Via the session. We store a user_id in a session an can determine the user's identification as long as that session and user_id information persists.

9. When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?
* You want to namespace a resource when you want to restrict access to page's to a certain authorization leve or tailor that page to a certain user role's needs.
* You want to nest a resource when one resource is dependent on another.
* The difference between these two approaches is that namespacing usually places a resource under the section of a user's identification, whereas nesting a resource places one resource as part of another resource.

10. At a high level, what tools can you use to implement authorization? How would you use them?
* bcrypt - a gem for one-way hasing passwords
* the password_digest column type in postgresql - automatically utilizes bcrypt to hash incoming password strings
* the `.authenticate` method that can be called on a `user` object and passed the user's password as an argument to authenticate the user.

11. What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?
* An enum is a a way for the developer to manage model roles. It gives us an easy way to translate inetgers (from the database `role` column) in to semantic role names like `owner` or `admin`.

12. What are some strategies you can use to keep your views DRY?
* Creating helper methods like current_user, current_<role_name_here>? in ApplicationController that can be called in the views.
* Using ActiveRecord to query the database for the majority of information needed from the database and using that returned ActiveRecord object in the view.


### Reviews Questions 
13. Given the following array of hashes, how would I print an alphabetical list of holidays?
```ruby
[
 {holiday: {name: "St Patrick's Day", supplies: ["Corned Beef and Cabbage"]},
 {holiday: {name: "Halloween", supplies: ["Candy", "Costume"]},
 {holiday: {name: "Hanukkah", supplies: ["Menorah"]}
]
```  
14. How would you clean incoming data to ensure "$300" or "300.00" is stored as 300?
given.map.sort_by { |holiday| holiday.name }


### Self Assessment:
Choose One:
* I was able to answer every question without relying on outside resources

Choose One:
* I feel comfortable with the content presented this week

