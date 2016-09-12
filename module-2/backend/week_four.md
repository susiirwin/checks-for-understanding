## Week Four Recap

### Instructions
Fork this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

* What is a cookie?

  information about the user stored in the browser by a website. they have expiration dates and will be stored until that date or at such time that a user manually deletes the cookies. IN a key/value pair.
  
* What’s the difference between a session and a cookie?
 
  a session is information about the user that is carried between page requests - like a more persistant cookie.

* What’s a flash and when do you want to use flashes?

  a flash is a message that is rendered on a webpage - these are awesome for giving the user hints/reasons why something does or does not work - such as an invlaid login.

* Why do people say “HTTP is stateless”?

  because no infomration is retained between requests - one request and one response only.

* What’s authentication? Explain.

  Authentication is the process of verifying that is a user is who they say they are (username and password)

* What’s the difference between authentication and authorization?

  authorization is when we make sure that an authenticated user only has access to the areas of site that he/she is allowed to see. you can have authentication without authorization, but not the other way around.

* What’s a before filter?

  a before filter (before_action) requires that a specified method run before other specificed methods in a Controller.

* How do we keep track of a user once they’ve logged in?

  we set the session id

* When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?

  we namepsace when we use roles and also to make URLs make more sense to our users. we nest resources when one resource relies on another in order to work.

* At a high level, what tools can you use to implement authorization? How would you use them?

  gem bcrypt - it is the go-to authorization gem in rails. it uses password_digest to hash a password for us and thus never stores a plain text password in our database. it means that a user model must have has_secure_password which then gives us more methods to use including .authenticate

* What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?

  an enum translates (for lack of a better word) a number into a string. we used this for our roles:
  
  ```enum role: %w[default admin]```
  
  basically if we now set a user role to 0, they will be a default user. a user role set to 1 makes that user an admin. 

* What are some strategies you can use to keep your views DRY?

  - partials for forms, error messages (flash messages), repeated code, etc...
  - helper_methods
  - using route paths
  - using our application layout whenever feasible (keep views clean)
