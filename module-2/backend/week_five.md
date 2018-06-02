### Week 5 Questions

Re-pull from this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!). 

Note: When you're done, submit a PR. 

### Week 5 Questions
1. How do we make flash messages display on a page?
* You first have to set the flash message in a controller action using something like `flash[:notice] = ...`. This is usually done before the redirect.

* You then have to ensure that the flash message if somehow work into your application layout ERB template. Either through a literal rendering of the state of the flash object or using an enumerable to list all types of flash messages.

2. Where is cart information/temporary information usually stored?
* In the session

3. What might be some reasons not to store a cart in our database? Are there any reasons why we would want to persist that information?
* If we would like to save that user's cart information after they have left their browser session, or if we want to acommodate users who browse in incognito mode.don't use cookies.

4. What is the purpose of the asset pipeline?
* To manage the delivery of static assets when a default stativ server like an NGINX or Apache, or something like a Content Delivery Network is not doing this for us. It's also helpful to make sure that we have the latest assets even if the browser has cached previous assets. This is done using asset fingerprints appended to the filename of the asset.

5. Why do we precompile our assets?
* We precompile our assets in order to prepare them with for efficient serving. Specifically all CSS and JS modules are pulled into one file, `application.css` and `application.js` respectively.

6. What do each of the following tags do?

```ruby 
<%= stylesheet_link_tag "application" %>
<%= javascript_include_tag "application" %>
<%= image_tag "rails.png" %>
```

- The `stylesheet` tag loads the precompiled `application.css` manifest that contains all of our modularized CSS into our template layout.

- The `javascript_include` tag loads the precompiled `application.js` manifest that contains all of our modularized JS into our template layout.

- The image tag (possibly, not 100% suer on this one) loads in a compiled image file that contains all of our image assets.

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?
- Clear and concise
- Detailed about necessary aspects of using the software, for example:
  - How to install it
  - How to use each piece of it's functionality
  - How to submit issues
  - How to contribute

8. What are the top four accessibility issues that we as developers should be aware of?
Looking at the lesson on the backend curriculum site, it identifies the following three types of accessiblity issues to be aware of. I'm not sure about the fourth:
* Visual
* Mobility
* Cognition

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?
- `before_save` is a callback. We might put this in our ApplicationController so that we can define some actions to take whenever saving an object(s) to the database.

10. Given the following object, how would we create a scope for all users who are active?

```ruby 
User.create(name: "Happy", active: true)
```

In our routes, we would nest some routes inside of the active scope (or we could namespace it, but that may be more than is needed):

```ruby
scope: active
  resources blog: only: [:show]
end
```

And then we would nest those controllers inside of a folder called `active`. The controller would probablt then look something like this.

```ruby
class Active::UsersController < ApplicationController
  # Methods here
end

=============

class Active::BlogController < ApplicationController
  def show
  end
end
```

11. What is the difference between a scope and a class method?
- A scope defines a set of classes that are nested inside of that scope, this could include class methods
- Class methods are a set of methods that are specific to a class, which is more specific than a scope and can be siblings of other classes in the same scope.


### Review Questions:  
12. Given the following hash:  

```ruby
{cart: {"17" => 4, "204" => 52, "29" => 22}}
```

  12a. How would you add item with id of 48 with a quantity of 4?
  ```ruby
  item_data = ["48", 4]
  given[:cart][item_data[0]] = item_data[1]
  ```

  12b. How would you increase the quantity of item 29?  
  ```ruby
  given[:cart]["29"] += 1
  ```

  12c. How would you find out how many items your user is thinking about purchasing?   
  ```ruby
  cart_total = given[:cart].values.sum
  ```
  
13. What is polymorphism? How does it relate to duck-typing? What are two ways you use this in everyday Rails applications?

14. How would you clean the string "(630) 854-5483" to "630.854.5483"?
```ruby
no_parens = given.gsub(/[\(\)]/, "")
no_dashes = no_parens.gsub(/[-]/, " ")
sanitized = no_dashes.split(" ").join(".")
```

### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week