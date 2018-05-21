## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 3 Questions

1. What is the entry at the command line to create a new rails app?
- `rails new <project_name>`

2. What do Models generally inherit from in rails?
- ApplicationRecord

3. What do Controllers generally inherit from in a rails project?
- ApplicationController

4. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?
- In your routes.rb file add
  - `resources :horses, only: [:show]`

5. What rake task is useful when looking at routes, and what information does it give you?
- `rake routes` or `rake routes -c <specific_resource_name>`
- This would give you the Prefix, HTTP Verb, URI formatter, and Controller#Action for each resource route created.

6. What is an example of a route helper? When would you use them?
- A route helper is a method you can call to return a formatted URI. It's made up of a route prefix with `_path` appended to it. Ex. `merchants_path`, conventionally that would render the index page for a Merchants model.

7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?
- `_url` would return the entire URL, including the HTTP protocol domain and subdomain. `_path` just returns the URI starting after the domain.

8. What are strong params and why are they necessary?
- Strong params limit the allowed parameter key/value pairs 
9. What role does `form_for` play in helping us create our forms?
- It gives us methods to call on a form object that will parse a given object to create HTML form tags with appropriate attributes for us.

10. How does `form_for` know where to submit the user's input?
- `for_for` uses the given object to populate the action path and method of the HTML form tag with the correct resource. I believe it uses the POST method unless specified otherwise.

11. Create a form using a `form_for` helper to create a new `Horse`. 
```ruby
<%= form_for @horse do |f| >
  <%= f.label :name %>
  <%= f.text_field :name %>

  <%= f.submit %>
<% end %>
```

12. Why do we want to validate our models?
- We want to validate our models so we can ensure that we are getting the required information when new resources are created.

13. What are the steps of the DNS lookup?
- A DNS lookup goes as follows
  - A request comes from a client out to an ISP
  - Through the ISP the request reaches a Domain Hosting Service that has Domain lookup tables
  - The lookup tables match a domain name to an IP address and the request is sent off to the appropriate server.


### Review Questions
14. How would you call the method `prance` from within the method `move` on a `Horse` instance?
```ruby
  def move
    prance
  end
```
15. Given the following hash:

```ruby
furniture = {table: {height: 3, color: "red"}, purchased: true}
```
What is the different between how you would return true vs returning 3?  
To return true, you would just have to access the purchased key inside of the outermost `furniture` hash, like so: `furniture[:purchased]`. To access the value '3', you qould have to access the table hash nested inside of the furniture hash and then access the height key, like so: `furniture[:table][:height]`

16. What is inheritance?
- Inheritance generally refers to the way that certain objects or rules inherit from their ancestor objects and/or rules. For eaxmple, CSS Inheritance means that if a rule is defined for an object above another rul in that class, writing the second rule inherits all of the styling code from the first rule unless it specifically overrides it and both rules are applied to the objecct.

### Self Assessment:
Choose One:
* I was able to answer every question without relying on outside resources

Choose One:
* I feel confident about the content presented this week
