## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 3 Questions

1. What is the entry at the command line to create a new rails app?

  * rails new app_name

2. What do Models generally inherit from in rails?

  * ApplicationRecord

3. What do Controllers generally inherit from in a rails project?

  * ApplicationController

4. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?  

  * resources :horses, only: [:show]

5. What rake task is useful when looking at routes, and what information does it give you?  

  * rake routes, it shows you the prefixes for every route available, as well as the uri path and the controller#action involved

6. What is an example of a route helper? When would you use them?

  * horses_path is an example of a route helper. It would substitute '/horses', and is used in almost all cases over the specific uri.

7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?

  * This is what I found from stackoverflow, although I'm not completely clear on the difference. _ path are for views because ahrefs are implicitly linked to the current URL. So it’d be a waste of bytes to repeat it over and over. In the controller, though, _ url is needed for redirect_to because the HTTP specification mandates that the Location: header in 3xx redirects is a complete URL.

8. What are strong params and why are they necessary?

  * Strong params are the params used when creating an object that we're adding to our database. They're necessary because of security risks. Whenever we have a form that lets the user put in data, we want to make sure that it's restricted to the type of data that we want, and that it ignores the rest. Strong params ensure this happens.

9. What role does `form_for` play in helping us create our forms?

  * It allows us to specify for which database the form is adding or changing information, and make the process of creating a form much easier than writing it in pure html.

10. How does `form_for` know where to submit the user's input?

  * the form takes an argument, often an instance of an object that is associated to a specific table. It uses that object to correspond to the correct row in the correct table.

11. Create a form using a `form_for` helper to create a new `Horse`.

  * <%= form_for @horse do |f| %>
      <%= f.label :name %>
      <%= f.text_field :name %>
      <%= f.label :breed %>
      <%= f.text_field :breed %>
      <%= f.label :age %>
      <%= f.number_field :age %>
      <%= f.submit%>
    <%= end %>

12. Why do we want to validate our models?

  * So that they behave according to the confines of the attributes their table has set for them. If a table for horses has a name, breed, and age, we want to make sure that every horse model associated with the database reflects those characteristics.

13. What are the steps of the DNS lookup?

  * Client > Browser > Name Server > Root > Top Level Domain Server > Authoritative Name Server

### Review Questions
14. Within a feature test and given the following HTML, write the code necessary to target the following section and check the person's name?

  `<section id="personal-info">
    <h3><%= @person.name%></h3>
   </section>
  `

  * within('#personal-info') do
      expect(page).to have_content(person.name)
    end

15. How would you call the method `prance` from within the method `move` on a `Horse` instance?

  * horse.move.prance

16. Given the following hash:

```ruby
furniture = {table: {height: 3, color: "red"}, purchased: true}
```
What is the different between how you would return true vs returning 3?  

  * furniture.purchased = true
  * furniture.table.height = 3

17. What is inheritance?

  * Inheritance is when a model or a controller receives certain attributes from a parent model or class. The inheriting model or controller is of the same type of class as the parent, and can certain methods without those methods needing to be defined. In code, it would look like this: Model < ApplicationRecord, Controller < ApplicationController

### Self Assessment:
Choose One:

* I was able to answer most questions independently, but utilized outside resources for a few


Choose One:

* I feel comfortable with the content presented this week
