### Week 5 Questions

Re-pull from this repository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 5 Questions
1. How do we make flash messages display on a page?

  * flash[:message] = "This is the message that you want to display in your flash notice". That is how you would set the flash message, and then you can call it wherever you like.

2. Where is cart information/temporary information usually stored?

  * In a session.

3. What might be some reasons not to store a cart in our database? Are there any reasons why we would want to persist that information?

  * Sometimes people will add or remove items from the cart, and then not do anything with that cart. It forces the
  database to do a lot of work, and can slow down the application for items that aren't even being purchased. By keeping that data in a session, it removes the strain on the database.

4. What is the purpose of the asset pipeline?

  * It helps "squish" the information that is requested from the site, so that there are not multiple requests. Our assets are able to called all at once.

5. Why do we precompile our assets?

  * To save processing power, we make only request for css instead of many. Instead of 10 css files, we'll only have one that is squished together. Same with other types of files, like javascript.

6. What do each of the following tags do?

```ruby
<%= stylesheet_link_tag "application" %>

  * This tag links our css from the application css file.

<%= javascript_include_tag "application" %>

  * This tag links our javascript scripts from the application javascript file.

<%= image_tag "rails.png" %>

  * This links an image called rails.png
%>
```

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?

  * A great README will have everything necessary for the user to be successful. It might have a description of what the program does, a description on how to download it, a description of some know issues that have occurred with the software, as well as screenshots of code that help guide the user through it. In general, good README's are readable and to the point. Updating the README for the project can be helpful in that it sets the standard for what the software should look like. While it is not Description Driven Development, it holds a loose vision of what the software is trying to accomplish. That can be helpful in guiding the team operates.

8. What are the top four accessibility issues that we as developers should be aware of?

  * Navigation, Text, Images, Forms? Not sure on this

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?

  * It's an example of a callback, I think. It's a before action, and we can use it to force the class to do a specific action before the rest of it runs. We'd wanna use a before save whenever we're about to create or update something.

10. Given the following object, how would we create a scope for all users who are active?

```ruby
User.create(name: "Happy", active: true)
scope :all_active, {where(active: true)}
```
  * I have no clue what this is. Did we talk about this in class?

11. What is the difference between a scope and a class method?

  * Apparently in the community there is little difference between the two. Scopes are easier to chain?


### Review Questions:  
12. Given the following hash:  

```ruby
{cart: {"17" => 4, "204" => 52, "29" => 22}}
```

  12a. How would you add item with id of 48 with a quantity of 4?  
    * cart["48"] = 4
  12b. How would you increase the quantity of item 29?  
    * cart["29"] = cart["29"] + num
  12c. How would you find out how many items your user is thinking about purchasing?   
    * cart.values.sum

13. What is polymorphism? How does it relate to duck-typing? What are two ways you use this in everyday Rails applications?  

  * As far as I can recall, polymorphism is the ability for different forms to arise from a similar base? Like you can have a shape class, but differing types of shapes can arise out of it, like a triangle vs. a square. Duck typing is the idea that if it walks like a duck, talks like a duck, then it must be a duck. In the same way, there are characteristics of a shapes that are similar, that quantify whether something "is" a shape, vs something else. But since it's polymorphic, it can still be different from another shape. We use this when we have classes like users and admins, because they are built the same but function differently. Or when certain classes inherit from other ones? Not completely sure on all this.

14. How would you clean the string "(630) 854-5483" to "630.854.5483"?  

  * string.gsub!(/()-/, ".") <--- I know that's wrong, but I'm not sure how to remove parens or empty spaces.


### Self Assessment:
Choose One:

  * I was able to answer most questions independently, but utilized outside resources for a few


Choose One:

  * I feel comfortable with the content presented this week
