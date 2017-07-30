# Rails API Service

This is reproduction of lesson for creating Api Articles using
[Traversy Media - article](https://www.youtube.com/watch?v=QojnRc7SS9o)

Using it for learning how to do api's with rails.

## Development notes

1. create a new api app folder:
    `rails new myarticles --api`

2. setting up the mysql db
     1. lets run `rails-xamp`   (this starts an xamp container at xamp name over the rails overlay network)
     2. setup the `Gemfile` with `mysql2` gem
     3. setup a database for dev/test/pro called `myarticles`
     4. setup a user account called `myarticles/123456`
     5. update the `config/database.yml`
     6. test http://localhost:3000

3. setup myarticles model
   ```
     rails g model Article title:string body:text
     rails db:migrate
   ```
4. Setup database data
    1. update validators in `models/articles.rb`
    1. add faker gem to Gemfile
    1. bundle install
    1. update db/seeds.rb
    1. `rails db:seed`

5. lets create our first controller
    1. create file `app/controller/api/v1/articles_controller.rb`
    2. add `config/routes.rb` , check rails routes
    3. implement  - `Content-Type application/json`
       >  index - list all articles,  GET /articles
       >
       >  show - shows an article, GET /articles/:id
       >
       >  create - creates a new article, POST /articles {:title, :body}
       >
       >  destroy - removes an article, DELETE /articles/:id
       >
       >  update - updates an article, PATCH /articles/:id {:title, :body}
       >
