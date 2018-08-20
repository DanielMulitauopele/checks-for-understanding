## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.

  * GET - Calls a specific resource, and displays it in the browser
  * POST - Creates a resource
  * PUT - Updates a resource
  * PATCH - Updates a resource
  * DESTROY - Destroys a resource

2. What is Sinatra?

  * Sinatra is a framework based in ruby, and makes it so that we don't need to write programs in full ruby. It helps us translate ruby to an html page so it is easier to see. According to my mentor, many consider it to be rails lite.

3. What is MVC?

  * Models, Views, Controllers

4. Why do we follow conventions when creating our actions/path names in our Sinatra routes?

  * Conventions are generally used to create a standard so that all programs written in Sinatra are readable to anyone who might look at the code.

5. What types of variables are accessible in our view templates without explicitly passing them?

  * Instance variables from the controller should be accessible without having to explicitly say where it came from. I don't think local variables can get there, but I'm not sure on that.

6. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?

  ```ruby
  get '/horses' do
    erb :index
  end
  ```
  * Right before the erb line, I'd write @count = 1. That should make it accessible in the view.

7. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?

  * My original thought was that local variables did not get passed through to our views, but this questions makes it seem
  like that is not the case. Perhaps as long as a local variable is created from the database object, then we're good
  to go. For example, if I write 'name = Horse.create(attributes)', then it might be allowed to get passed on to
  the index page. But I'm not sure on that.

8. What's the purpose of ERB?

  * ERB stands for embedded ruby, and lets the programmer use ruby as an input for html. It lets ruby and html talk to each other and be on the same page.

9. Why do I need a development AND test database?

  * A test database is necessary to make sure that our code is working as its supposed to. These are hypothetical
  instances and are kept separate from the real data. A development database is where we get to see the true functionality of our app. For other reasons more than that, I'm not sure.

10. What is CRUD and why is it important?

  * CRUD stands for Create, Read, Update, and Delete. It describes the actions that can be taken on a webpage.

11. What does HTTP stand for?

  * Hyper Text Transfer Protocol

12. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?

  * <%= content %> This lets you interpolate ruby, and print the value out to the screen
  * <% content %> This lets you interpolate ruby to do a function, but the value is not printed out

13. What's an ORM? What does it do?

  * ORM stands for Object Relational Mapper. ActiveRecord is an ORM, and lets our program interact with our database without having to write pure SQL. ActiveRecord also makes SQL easy to use in that it can translate whatever version of SQL we are using (MySQL, PostgreSQL, SQLite, etc.)

14. What's the most commonly used ORM in ruby (Sinatra & Rails)?

  * ActiveRecord

15. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.

  * Verb: GET Path: /restaurants See all restaurants (Read)
  * Verb: GET Path: /restaurants/:id This is to see a specific restaurant (Read)
  * Verb: GET Path: /restaurants/new This is to see the form that makes a new restaurant (Read)
  * Verb: POST Path: /index Create new restaurant in the db (Create)
  * Verb: GET Path: /restaurants/update Go to page that updates restaurant (Update)
  * Verb: PUT Path: /restaurants Update existing restaurant (Update)
  * Verb: DELETE Path: /restaurants Delete a specific restaurant from the database (Delete)

  * I got all this from reading an old student's CFU. I'm still fuzzy on a lot of it.

16. What's a migration?

  * A migration is any change that is made to a database, and includes the first migration which creates the database.

17. When you create a migration, does it automatically modify your database?

  * I don't think so. It is what lets you define what you want the database to look like, but you need to run db: migrate to actually modify the database.

18. How does a model relate to a database?

  * A model is what makes our data manipulatable, as it turns our data into an object, vs the raw data form its in in the database. A model lets us shape that data how we want.

19. What is the difference between `#new` and `#create`?

  * #new will create an object, but it will not make any changes to the database. #create will make a new object and also update the database with the new parameters that we've provided.

20. Given a table named `animals`, What is the SQL query that will return all info from that table?
    `id     name        number_of_legs
    -----   ------      --------------
      1     panda       4
      2     giraffe     4
      3     whale       0
      4     bird        2
    `

    * I think it looks like this:
    * SELECT * FROM animals

21. Using the same table, What is the SQL query that will return only the animals that has 4 legs?

    * SELECT * FROM animals WHERE number_of_legs = '4'

### Review Questions:  
22. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?

  * The following code would go in my seeds file, in the spec folder

  films = CSV.read('./data/films.csv')
  films.shift
  films.each do |film|
    Film.create(id: film[0],
                    title: film[1],
                    description: film[2],
                    created_at: film[3],
                    updated_at: film[4])
  end

23. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone']},
  brunch: {cost: $35, supplies: ['mimosa flutes']},
  antiquing: {cost: $200, supplies: ['list of antique stores']}
}
```
How would I add 'granola bar' to things you should have when hiking?

  * Hmmm maybe hiking = Activity.find_by(:hiking), then hiking.update(supplies: 'granola bar')? Not completely
  sure on that.

24. What are the 4 Principles of OOP? Give a one sentence explanation of each.

  * Encapsulation - Encapsulation is the mechanism of hiding of data implementation by restricting access to public methods
  * Abstraction - Abstract means a concept or an idea which is not associated with any particular instance.
  * Polymorphism - It means one name many forms. Most notably, super classes.
  * Inheritance - Inheritances expresses "is-a" and/or "has-a" relationship between two objects.


### Self Assessment:
Choose One: (erase the others)

* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:

* I feel overwhelmed by the content presented this week
