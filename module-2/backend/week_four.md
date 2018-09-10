## Week Four Recap

### Instructions
Fork or re-pull this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 4 Questions

1. What is a cookie?

  * A cookie is a client-side piece of information that communicates to the server and lets the server know who the user is. By using cookies, a user's information can be accessible despite numerous requests. In essence, it allows the user to hold the website in a specific "state".

2. What’s the difference between a session and a cookie?

  * A session is a piece of data that is similar to a cookie, except its on the server side of the things. When a user signs in, they begin a session, that is only accessible through their personal cookie. The session carries information despite receiving numerous requests. This happens in a cart for example. A user can access different parts of the website, but their items in the cart will be the same. Once a user closes their browser, or the time on the session expires, the session ends.

3. What’s a flash and when do you want to use flashes?

  * I don't know all the details of flashes, but they are like little pop up messages than can be used to communicate that a specific action has been performed. You'd use them when you want a user to see that something has happened without needing to go to a completely new page. Like "You've add this item to your cart!"

4. Why do people say “HTTP is stateless”?

  * Because every request starts fresh. There is no memory or state tied to it, every request acts like its the first one. This is why we have cookies/sessions, so that information can get carried from request to request.

5. What’s authentication? Explain.

  * Authentication is the process by which a user is allowed to access certain data by entering in a username and a password. By putting in this confidential information, a user's identity is authenticated, allowing them to access whatever information that registered user has access to.

6. What’s the difference between authentication and authorization?

  * Based on the website, most users can go through the authentication process. They register for the site using their personal information, and every time they log in with that username/password information, their identity is authenticated. Authorization is the sectioning off of information based on types of user. Whereas a user can be authenticated when they visit a site, the fact that their identity has been verified does not mean they have access to everything in the site (unless it's set up that way.). They don't have the authority to access certain parts. An admin however, can sign in, have their identity as 'admin' be authenticated, and then receive access to the information on the site that an admin has the authority to view. While most users can be authenticated, not all users have the authority to view everything.

7. What’s a before filter?

  * This is something we'd use in our application controller, for example, that tells a controller to perform an action before anything else on the page. In our project, we use one to call the method "set cart". This lets information get passed to any controller globally before anything else is done on the page.

8. How do we keep track of a user once they’ve logged in?

  * Once they log in, a session is created and a cookie is issued (?). The user, with their cookie, is in constant communication with the session, allowing the session to carry the user's information from page to page. This overrides the normally stateless environment. Other than that, I'm a little foggy.   

9. When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?

  * Namespacing would mostly be used when differentiating authorization between users. This allows the admin to see all the pages a regular user can see, as well as the pages that users can see. Since they have separate controllers and functionality, namespacing allows the page to not have duplicate pathways, so that the admin route to an index page is not different from the regular user, just the pages that a user does not have access to. Nesting a resource communicates more about the relationships between the tables than it does about a user or an admin. You want to nest a resource when a table belongs to another table in the relationship. Nesting resources and namespacing cover different things.

10. At a high level, what tools can you use to implement authorization? How would you use them?

  * You would use namespacing, to separate the pathways that an admin/user takes to see certain information, and to restrict certain pathways to users. In the Application Controller, you'd also set global methods that can be access from anywhere in the program. This lets the program know that the current user is an admin or not.

11. What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?

  * I'll need a refresher on this.

12. What are some strategies you can use to keep your views DRY?

  * Use the application file in the layouts folder, so you don't need to repeat code on every single page. Keep classes uniform so you don't have multiple classes that do the same thing.


### Reviews Questions
13. Given the following array of hashes, how would I print an alphabetical list of holidays?
```ruby
[
 {holiday: {name: "St Patrick's Day", supplies: ["Corned Beef and Cabbage"]}},
 {holiday: {name: "Halloween", supplies: ["Candy", "Costume"]}},
 {holiday: {name: "Hanukkah", supplies: ["Menorah"]}}
]

sorted = array.sort_by do |holiday|
  holiday[:holiday][:name]
end

```  
14. How would you clean incoming data to ensure "$300" or "300.00" is stored as 300?

  * I would use .to_i for the second value. Not sure about the first. I'm sure we could do something that would strip the $ sign, but not sure about that.


### Self Assessment:
Choose One:

* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:

* I feel comfortable with the content presented this week
