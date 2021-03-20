# Ruby Gem 
The Rock That Would Become a Gem.  

This project, for some time, has been causing me angst.  It was a rock around my neck.  I had grown accustom to the work flow of the lessons and labs, and equally accustom to the ‘Ask a Question’ option; Let’s just say that I started to know the Learn coaches’ work schedules.   

This project was different.  It was just me.  I took (or taking, still not quite done) this serious.  I wanted to feel the weight of responsibility.  I started by watching and reading all the provided resources.  I read, and reread material, lessons and labs.  I watched Avi’s “Walk Through” video, taking notes the whole time.  I scribbled ideas in my notebook, and visited websites I was interested in scrapping.  I jotted down diagrams of the flow of my gem.  I made list of things to do.  I re-watched parts of Avi’s video, making even more detailed notes.  Then it occurred to me: I need to write some code.  

I started.  I pulled up an empty terminal and text editor.  Yikes!  It was all about baby-steps.  I typed into the command line, bundle gem famous_physicists_cli_app.  It didn’t take long before I deeply regretted such a long name, but with this file structure that looked so “project” like, I couldn’t look back now.  

My next step was to get my environment correctly formatted, and get the files talking to one another.  So, my task was to print out to the terminal “E=mc^2.”  I simply wanted to format my file structure so I could have the bin file speaking to the cli file, and I could print a simple, hard-coded statement.  This took two hours.  Oh, but the elation I experienced when I saw, “E=mc^2.” Like I said, baby-steps.  But this was an important step for me. Because I felt the power of momentum.  

I continued by following Avi’s suggestions, and stubbed out, in my cli class, my entire gem.  It printed out to the terminal beautifully, but, as Avi said, it was brain-dead.  This, however, provided me real structure.  The things I had to start working on became clear; I could begin to see potential classes and methods.

The basic idea for my gem was to create a resource where a user could see a list of the top physicists, and peruse through basic info and maybe a bio or profile.  So that was the big picture I had in mind and my cli was printing out this basic structure.   

Now that I had my cli up and running, and putting out to the terminal the basic structure of my gem, I began to build my scraper class.  I picked a website that was stable, conveniently formatted and accessible.  With my website picked, I wrote my first method for my scraper class which simply opened the website.  I then worked extensively to scrape and print out the list of physicists.  The website I was working with featured history’s twenty most famous physicists.  This is clearly a subjective list, but largely speaking, I agreed, so I continued.  I enjoyed the scrapping. I found it to be like a scavenger hunt, but I had to keep in mind the explicit instructions of the project.  I had to stay focus on the functionality of the gem, and not get lost in the scrapping.  

After some steady work, I got a handsome list to print out.  I used the each_with_index enumerator, producing a numbered list of physicists.  I must have printed that list out a dozen times.  But there was no time to break my arm patting myself on the back, I had a lot more methods to write.  Additionally, I had to break my code up into smaller methods.  Initially, I had one method opening the website, collecting the names, iterating over the newly populated array, and printing this out.  But I was happy that I had something up and running.  

I worked to divide those functionalities up into individual methods, ones that I could call on later.  Additionally, I created a method that scraped the necessary information.  Namely, I scraped the name, date of birth, date of death, what the physicist was most famous for and a brief profile.  Now, I could print all this information out, however, there lacked any real methods with defined responsibilities.  So, I worked to encapsulate smaller chunks of functionality into methods.  But the thing that I was ignoring was instantiating an object called a physicist which had all the attributes that I had worked so hard to scrape from the website.  

I also I had another problem: the index website provided a link for each physicist, and this is where all the meaningful data was scrapped from.  However, sixteen of the twenty links took you to a specific html format.  Consequently, this was easy to scrape from.  But there were four links that took you to an html format that was different than the other sixteen.  Now, I was faced with two obstacles.  First, I still had to work through the process of instantiating a new object called physicist, one in which had all the attributes, and second was figuring out a way for a method or methods to know which html formatting it should consider when scrapping the website.  So, again, I relied on baby-steps.  I needed to build a loop that would tell the program which scrapping code to use for which sub link.  While I was scrapping all the necessary attributes, I built a method that scraped these sub-links.  So, since I knew the sub-links that were problematic, I built a loop that enumerated over the array of sub-links, and assigned the appropriate scrapping code to the appropriate sub-link website.  But this too was long and ugly code.  

But I had something up and running, and I could print out, now, all the information I want the user to have access to.  Mind you, I have not made one object called a physicist yet.  My job now was to take the functionality of the loop that allows me to access the appropriate data, and tweak it so I can use it to instantiate an object with all those attributes.  However, the problem I found was that in the same method I needed to access two different sources for data.  It may be a bit of brute force, and definitely worthy of a longer look and refactoring, but I went with a loop that each time called for that particular link to be opened.  It is messy, verbose and expensive, but it worked like a charm.  I could now instantiate an object called ‘physicist,’ and have access to all those attributes I so badly needed.  

I made something.  Something that nobody else knew anything about.  Whether I was sharing it with my wife, friends or mentor, I was the one who knew everything there was to know about it.  I’m not sure I have ever experienced this sort of creative power.  I went to bed thinking about the code, the functionality and the users experience.  It also has caused me to begin to think much, much more about other potential projects, perhaps, regarding education, music (I’m a guitar player), exercise and maybe, meditation.  This project, that started as a rock around my neck, after some polishing, had finally become a gem. 

# Sinatra 

Where Hackers Hike: My  Sinatra App

While I worked my way through the Sinatra curriculum, I found that I needed a way to completely remove myself from code.  I found a long, scenic hike was the best rememdy to recharge my programing battery.  Now, I  have some favorite hikes that I like to share with friends, and I was wondering where other hackers may like to hike.  With that question, an app was born.  

The idea for this app, HackerHIkes, was very simple, you can find a linke  [here](https://github.com/JimHotchkiss/sinatra-fwitter-group-project-v-000).  I wanted the user to be able to: 

1. Signup to the app
2. See a list of all the hikes
3. Create their own hike 
4. Edit or delete one of their hike

In order to get this basic CRUD (Create, Read, Update and Delete) functionality working, I used an MVC model.  Here work and responsibilities are divided up into *Models, Views and Controllers.* The models is where the logic lives, these are classes, in this case `User`, `Hike` and `Difficulty.` The views is what the user sees, this is the webpage.  The controller is how the programmer mediates between these two models and the views.  The controller determines whether to render an html page, instantiate objects from users inputs, or edit or delete existing objects.  To get these seperations of responsibilities correctly interacting, I first had to establish a logical, and working database that would link database tables to my classes.  

To connect my database to my models, I used ActiveRecord.  This provides the powerful functinality of saving, or persiting, objects created from the models.  For instance, when a user signsup, the information they provided is used to instantiate a new user.  ActiveRecord links this newly created object to the appropriate database table.  Now that information, the object and its attributes, is stored, and lies in wait for a controller action to call on it.  Another powerful part of ActiveRecord is how it assosiates, or relates, datatables to one another.  Objects can `belongs_to` another object, or an object can `has_many` of another object, and even other associations.  As you can imagine, in this app, HackersHikes, and in most other apps, objects are related to one another. 

For instance, in HackersHike, there are three models, 'User,' 'Hike' and 'Difficulty,' and these models are all related to one another.  A user will have many (`has_many`) hikes; a hike will belong to (`belongs_to`) a user and difficulty; conversely, a user `has_many`hikes; while a difficulty `has_many` hikes.  It is these relationships, that allowed me to be able to ask the users about their hikes, or a hike about its user or difficulties about its hikes.  Now, in my experience, the database is both where I begin  when I begin to think about the functionality of my app, and this is the part of the process that requires a lot of attention.  After some trial and error, and many, many rakes of the console, I ended up with a schema (the structure of my database tables) like this. 

```
ActiveRecord::Schema.define(version: 20170824223456) do

  create_table "difficulties", force: :cascade do |t|
    t.string "rank"
  end

  create_table "hikes", force: :cascade do |t|
    t.string "name"
    t.string "location"
    t.string "description"
    t.integer "user_id"
    t.integer "difficulty_id"
  end

  create_table "users", force: :cascade do |t|
    t.string "username"
    t.string "email"
    t.string "password_digest"
  end

end

```

The key to getting your database tables set up correctly is playig with data.  Jump into your console and play around with instantiating objects, correctly associating your objects and confirming that those associations hold up to scrutiny.  Once I felt confidate that I had a working database table that was appropriately linked to my models, I began to build out my CRUD acions.  

The first thing I worked on, once I was able to render an index page, was creating a user.  To do this there was a couple things I had to do.  I first had to render a signup page that provided a form for the user to input their data.  Prior to rendering this page, I had to confirm that the user wasn't already logged in.  This is funtionality that was used many times through out the application.  Consequently, I built out a helper-method.  Once the user submited the form, the params must be checked for completenes, if this conditional is met, an object of the user is then instantiated and the newly created user is signed in by assigning them a sessions has.  The user is then redirected to a list of hikes.  This is what that controller action looks like. 

```
  post '/signup' do
    if params[:username] == "" || params[:email] == "" || params[:password] == ""
      redirect '/users/signup'
    else
      @user = User.create(username: params[:username], email: params[:email], password: params[:password])
      session[:user_id] = @user[:id]
      redirect '/hikes'
    end
  end
```

Once a user has signedup, the user can then scroll through hikes that other users have posted.  Additionally, if the user wants to contribute their own hike they can create their own hike.  First, much like signing up, the it must first be confirmed that the user is logged in, this is where that helper method came in handy.  Then a page is rendered for the user that includes a form for the user to input  the data of the hike they would like to create.  This data is sent to the action that creates a hike.  The users input is first checked for completeness.  If the input is complete, an object of the hike is instantiated.  Here, the newly instantiated hike is associated to the user creating the hike (this is where correctly constructed data tables is very important).  Lastly, the object and its attributes are saved, and a page is rendered that shows the user their newly created hike.  This is what that controller action looks like.

```
post '/hikes/new' do
    if params[:hike][:name] == "" || params[:hike][:location] == "" || params[:hike][:description] == ""

      flash[:message] = "Please, do not leave form incomplete."

      redirect '/hikes/new'
    end

      @hike = Hike.create(params[:hike])
      @hike.user_id = session[:user_id]
      @hike.save
      @hikes = Hike.all

      redirect :"/hikes/#{@hike.slug}"
  end
```

Now that a user has signed up, created a hike, they can also update or even delete that hike.  In order to do this, I had to include some logic that prevented a user from editting or deleting a hike that was not theirs, in addition to checking that the content that the user was submitting was complete (like the orginal creation of the hike).  This was accomplished by comparing the users sessions hash with the hikes users_id (again, this is where smartly constructed database tables are wildly important).  Authenticating a user was done with this line of code.  

```
@hike.user_id = session[:user_id]
```

This was a wonderful experience.  I had some wonderful hicups with github, where I had to start over THREE TIMES, that in the end prove to be wonderful learning experiences.  I found, that when creating a database table, even one that is as simple as the one I created, it is best make a diagram of what you intend to create, write out each object, by name, draw a line or lines connecting each object to one another, and then verbally, to yourself or someone bored enough to listen to you, the exact schematics of your design.  Ask youself of the intended outcome, and constantly throughout the development, make sure that that functionality is there and robust.  Once I felt I was done, I asked my wife to open the app, create a user, browse the listed hikes, create a hike and finally, edit or delete a hike.  This uncovered some gaps, not in the functionality, but rather the interface.  For instance, I had not built a message to notify a user if they were trying to edit or delete a hike that was not theirs.  And while watching my wife move through the functionality of the app, it was very suddenlty clear that she was completely confused on why she now seeing the page she was, and what exactly to do next.  A few lines a code, and a couple pushes to github, that functionality became far more intuitive.  

My affinity for coding has turned to a genuine love.  

# Rails - General Topic

The Complexity of Nested Forms 
**The Big Picture**

In this lab, we are working with two models.  Namely, we are working with a `Post` and a `Tag`.  There are other models but we are focusing on these two.  We are looking at, exploiting, the association between these two models.  So, in our app, a `user`can create a new `post`, and they can add any number of `tags` they would like from a list of provided `tags`.  We want to create the functionality on our `post` form to allow the user to create a new `tag`.  This is reasonable enough.  The difficulty comes when we need to both instantiate a new `tag` and associate that `tag` with the newly instanatiated `post`.  To do this we must look at * nested forms.*  

**The Frame Work**

In our application, our Post model `has_many` `tags, :through`, and our `Tag` model `has_many` `posts, :through` the `post_tags` table.  This association is provided by a joins-table, `post_tags`.  We join these two models by connecting them through the `post_tags` joins-table.  

```
class Post < ActiveRecord::Base
  has_many :post_tags
  has_many :tags, :through => :post_tags
```

```
class Tag < ActiveRecord::Base
  has_many :post_tags
  has_many :posts, :through => :post_tags
```

What this does, out of the box, is allows us to ask a `@post` how many `tags` it has, with `@post.tags`.  Ultimately, what we want to be able to do is to nest the `tag` attribute `name` with our `post` on our `post` form page so it looks like, `@post[:tag][:name]`.  Rails will do a lot of heavy lifting for use, to accoplish this.  

**The Role of Rails**

At this point, we have our associations wired up: we have our datatables, with the appropriate joins-table; we have our models with the necessary `has_many` relationships.  We now need to add some functionality to our `post` form.  Rails has a powerful metho, `accepts_nested_attributes_for`, which provides us the ability to nest data structures in our `post` form.  We add this method to our `Post`model, and allow to accept the attributes of `tags`.  

```
class Post < ActiveRecord::Base
  has_many :post_tags
  has_many :tags, :through => :post_tags
	
	accepts_nested_attributes_for :tags
```

Now we can go to our form page, and write the functionality that will allow us to enter a new `tag`, and associated with the newly instantiated `post`.  We start with a form_for, passing it the instance variable `@post`.  This instance variable, `@post`, is made in the `posts#new`action, and provides rails with an object to work with.  

```
<%= form_for(@post) do |f| %>
```

For the `post`, we pass the variable `f` the rails' method `.label` and `.text_field`.  This provides the html to allow the user to enter a the content of their post.  We wrap this in a <fieldset>.  

```
<fieldset>
    <%= f.label :name %><br>
    <%= f.text_field :name %><br>
    <%= f.label :content %><br>
    <%= f.text_area :content %><br>
  </fieldset>
```

Additionally, we can provide a list of checkboxes for the user to pick the tag or tags they would like to associate with their `post`.  We can do this using the rails' method `.collection_check_boxes`.  

```
    <%= f.collection_check_boxes :tag_ids, Tag.all, :id, :name %>
```

But what we want to do is add a new `tag` with its attributes.  This is where the functionality of `accepts_nested_attributes_for`is put on full display.  We call the rails' method `.fields_for`, and pass it two arguements.  The first is the parent object, in this case, our `@post`.  This is done with the variable `f`.  Then we pass it the variable `:tags`.  

```
<%= f.fields_for :tags do |tag_forms| %>
      <%= tag_forms.label :name %>
      <%= tag_forms.text_field :name %>
    <% end %>
```

Now, the variable `tag_forms` gives us access to a ActionView::Helpers::FormBuilder.  This builder method gives us access to two objects: `post` and `tag`.  And, this is where the magic happens, it nests for us the attributes of our newly formed `tag`, and associates it with our newly instantiated `post`.  Here is the html that `tag_forms` produces.  

```
#<input type="text" name="post[tags_attributes][0][name]" id="post_tags_attributes_0_name">"
```

There's a few things that I did that perhaps you can learn from.  

**Remember to...**

When I began this lab, I started with the database.  Next, I made sure the models were correctly associated, and then I began to work on the `post` form.  After some review, I was able to build the `fields_for`that I wanted.  However, when I updated the browser, I got nothing!  The code didn't break, it just didn't render the output that I wanted.  After more review, I was reminded that, like the `@post` in the `posts#new`controller action, I needed to start the building process for `tags`.  I used the rails method `build`, which is a method like `new`, but `build`is smart enough to set the foreigh key.  So, once I updated my `posts#new`controller action, everything worked beautifully.  


```
def new
    @post = Post.new
    @post.tags.build
  end
```

Okay, now the new data is passed to the `posts#create`controller action, and however, when I look at the `post_params`, I am unable to find my nested data.  I needed to update my strong params, `post_params`, to be able to instantiate a new `tag`and its attributes.  I updated my `post_params` with `:tags_attributes =>[:name]`.  

```
def post_params
      params.require(:post).permit(:name, :content, :tags_attributes =>[:name], :tag_ids => [])
    end
```

After this last addition, I was able to instantiate both a new blog post with a new tag and its attribute(s).  

**Conclusion**

I have been enjoying learning Rails.  The power and functionality that is at your finger tips is wonderful.  However, sometimes, you have to look under the hood, in order to make sense of all the moving parts.  What seemingly in straight forward functionality you are trying to initiate, becomes very abstract with Rails doing much of the heavy lifting.  It is important to go back, and review the underlying methods provided to us through Rails. 

# Coding - General Topic 

Climb High Sleep Low: Coding and Climbing
![](https://i.imgur.com/M7gltRg.jpg)

I've never climbed a mountain.  Sure, I've taken long hikes that have left me tired and sore, but never have I scaled the face of a mountain or 'pushed for the summit.'  I just simply haven't.  I am, however, learning to code.    

Shortly after my CLI gem project, my first big project, my wife and I took a trip with some friends to Yosemite National Park.  I'm in my forties and I've never been.  Both my wife and I were very excited about the trip.  We love the outdoors, and one of our favorite pass times is hiking.  In addition to the beautiful vistas and the feel of nature, I thought it would be a good idea to  take a few days off of coding, recharge my battery.  

Getting to Yosemite, from the Bay Area, wasn't at all easy, but so worth the effort.  Our hosts, family friends, were wonderful, and took great joy in showing us 'their' Yosemite.  On are second day, we completed a long and strenuous hike.  It was one of the best hikes I had ever experienced.  It was after dinner, the table filled to the edges with food smeared plates, serving dishes and glasses, and we sat with our stomachs full, our legs sore and our feet pink with blisters.  Then the stories started 

Judy, one of our gracious hosts, began to tell a wonderful story about when she climbed Mt. Kilimanjaro.  It was told with dramatic description about the strains put on the body from the altitude.  She spoke, with detail that only someone who has experienced it could share, about the agony and pain of each step.  I gazed at her from across the dinner table, and wondered how I could iterate through nested hashes to pick out the values that were not integers.  I caught  myself in this day dream, and after admonishing myself for being a nerd, I re-engaged with the story.  I asked, 'how does a person prepare their body for that kind of altitude?'  Judy said that one thing they did was 'climb high and sleep low.'  This is where the climbers will climb during the day, letting their bodies feel the strain of the altitude, and then they climb back down to camp to sleep, allowing their bodies to recover.  The climbers will do this kind of 'leap frog,' to allow their bodies to acclimate to the altitude.  So, of course this story has me thinking about learing code. 

I have now finished my Sinatra project, and I am more than half way through Rails.  It is tough.  The material, at times, seems disparate, and I find myself having to go back into my notes, or visit old labs, to remind myself how to do something.  Things that I think I should know, at this point.  I recently finished refactoring with helpers and models.  This, for me, was a deep dive back into layouts and partials.  The notions are simple enough, but the execution of these concepts, especially when it involves several views, controllers and models, can leave me questioning my ability to become a skillful developer.  I really get down.  But you keep climbing, and trust that this is the 'pain' in growing-pains. 

Like a climber acclimating to the increasing altitude,  the curriculum keeps you looping back from the edges of your ability.  Your understanding is pushed into harder territory, and then doubles back into areas you have more confidence with.  Then, once again, you are pushed to the boundries of your understanding. You notice that the material you are comfortable with continues to grow and grow.  You are breezing through things that you, just recently, were struggling to complete, and you really feel like you're getting it.  That feels good.  But then you are pushed, once again, into ideas that stretch your confidence thin.  

Now, I've never climbed a mountain, but I am learning to code.  And I can tell you, the best way to learn code is to climb high and sleep low

# Rails - Portfolio

My Rails Portfolio Project
<iframe src="https://giphy.com/embed/CDH0spsSaqQUg" width="480" height="192" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/pulp-fiction-funny-CDH0spsSaqQUg"></a></p>


> *Me, I can't usually get them 'cause my girlfriend's a vegetarian, which pretty much makes me a vegetarian. I do love the taste of a good burger.*                   - Jules Winfield



Often my wife and are trying to decide on something to cook, and with her being a vegan, our choices seem to be inherently limited.  This made me consider building a recipe organizer app for vegans.  The functionality is straight forward enough.  A user can browse recipes,  search recipes by ingredients, contribute a recipe and leave a comment on a recipe.

## Users and Authentication

I started things by entering, rails new simply_vegan_app, in my terminal, and that Rails magic did not disappoint.  I started by getting the User up and running.  With `rails g resource User`, I stubbed out  the necessary migration, model, routes and controller for a user.  I built out the necessary user signup form, and controller action neseccary to instantiate a user.  I then moved on to authentication.  I utilized the gem 'bcrypt', with the macro `has_secure_password`.  This gave me acess to useful authentication methods, like `authenticate` and `password_confirmation`.  We were required to use Omniauth to login by a third-party provider, like Facebook, Twitter or Github.  Omniauth is gem that provides a secure way for you to authenticate a user.  Omniauth initiates a kind of 'hand-shake', where the the provider, Github, in this case, responds to a GET request by sending a token back to the browser.  The browser then sends the token back to the provider, proving they are who they say they are.  The provider then sends a hash of the user's data.  In order to correctly extract this data, we need to grab the hash, and put it in a variable.

We first setup an if-statement, to confirm whether the user is authenticating from a third party.  If so, we have access to our user's data, and set it to a variable.

```
if auth_hash = request.env['omniauth.auth']
```

Once we have access to this data, we can build a method that searches our data base to either find or create a user.

```
def self.find_or_create_by_omniauth(auth_hash)
    self.where(username: auth_hash['info']['name']).first_or_create do |user|
      user.password = SecureRandom.hex
      user.save
    end
  end 
```

Finally, we log the user in by using the SessionHelper method, `log_in`.  If not, we find our user, using our find_by method, and authenticate their password by using the authentication method. 

## Associating Objects

But perhaps the crux of this project is the associations between objects.  In order to unlock the power of Activerecord, a builder needs to make sure the objects they are working with are appropriately wired up.  In this case, I had a recipe model.  Recipes have to have ingredients.  But ingredient is its own model.  So, what I'd like to do is to take a `recipe`object, and be able to ask it about its ingredients, like `recipe.ingredients`.  I want this to return to me an array of ingredients specific to that recipe.  We want the user to be able to provide the recipe's title, instructions for the recipe, but these are direct attributes of the recipe.  Additionally, we want to user to be able to select ingredients, already instantiated by other users, or provide their own.  However, an ingredient is an object.  We need to relate these two objects, recipe and ingredient, by using nested forms.   

I'm using form_for to build out the recipe form.  We have an option for the user to selected from already existing ingredients.


```
<%= f.collection_check_boxes :ingredient_ids, Ingredient.all, :id, :name %><br></br>
```

However, we'd also like the user to be able to add their own ingredient.

```
<%= f.fields_for :ingredients, @recipe.ingredients.build do |ingredients_fields|%>
  <%= ingredients_fields.text_field :name %>
<% end %>
```

Here I'm using the fields_for, which is a FormBuilder object that associates the input with an existing object, in this case, `@recipe` to our `:ingredient` arguement.  Here, we are able to use the power of our associated objects.  Namely, we have `@recipe.ingredients.build`. This returns an array of ingredients.  The fields_for will now associated the input with the `@recipe` object.    

We have the input we need, and the necessary associations at the form level, but our recipe model does not have an ingredient attribute.  We must include this association in our strong params, allowing a @recipe to be instantiated with and newly created ingredient.  

```
def recipe_params
    params.require(:recipe).permit(:title, :instructions, ingredient_ids:[], ingredients_attributes: [:name])
  end
```

Here, we are 'whitelisting' the params we want permited.  Note, the `ingredients_attributes: [:name]`.  This is a setter method that takes the user's input, searches the data base, and either finds and returns that object, or creates a new ingredient object.  

```
def ingredients_attributes=(ingredient_attributes)
    ingredient_attributes.values.each do |ingredient_attribute|
      if !ingredient_attribute[:name].blank?
        ingredient = Ingredient.find_or_create_by(ingredient_attribute)
        self.ingredients << ingredient
      end
    end
  end
```

Here, we are taking the user's input, interating over the array, assuring there is not blank input.  Then it will search ingredients, and either find or create that ingredient.  Then the ingredient object will be shoveled into our @recipe.ingredients array.  

## Nested Resources

Another important feature of this app is for the user to be able to comment on a particular recipe.  This means that the user will navigate to a recipe url, `/recipes/recipe_id`, and then to create a new comment, `/comments/new` associated with that recipe.  In order to do this, we need to use nested resources.  

```
resources :recipes, only: [:show] do
    resources :comments, only: [:new]
  end
```

By nesting these resources, we are now able to use the url path of `/recipes/recipe_id/comments/new`.  This assure that each comment that is instantiated is properly associated with the correct recipe. 

Additionally, to add another level of functionality and convenience for the user, I decided to build a class level scope method.  This allows for more precision when searching and retrieving objects.  I wanted the comments to present the most recent comments first.  

```
  scope :most_recent, -> (limit) { order("created_at desc").limit(limit) }
```

This created a method, called `:most_recent`, which uses the provided method of `created_at`, and returns an array of objects, our comments, in this case, that are ordered from newest to oldest.  We, again, are taking advantage of the power of  Activerecord's associations.  Here, a comment belongs_to a recipe, and a recipe has_many comments.  This allows us to ask a recipe about its comments, like `@recipe.comments`.  This will return for us an array of those recipe's comments.  Our scope method takes an argument of 'limit'.  To address the 'limit', I simply used the count of each array.  

```
@recipe_comments = find_recipe.comments.most_recent(@recipe.comments.count)
```


## Final Thoughts

I really enjoyed this process.  There were times of enormous frustration.  For instance, I had moved away from authentication, and was working on views and forms.  My signup, login and logout had been working perfectly, and just before a signed off for the day, a double checked all the app's functionality.  Nothing worked.  I kept getting an error regarding  CSRF token authenticity.  Login links were dead, or just breaking the code.  I Googled the question, and got many explenations and suggestions that I didn't understand.  I reached out to the Slack community, and was immediately pointed toward accessible resources.  In my attempt to use link_to for a delete button, I added some JavaScript.  This, I learned, caused me to loose my authentication token.  Then I came across the prettiest, little line a code, `<%= csrf_meta_tags %>`.  This, effectively, acts as a hidden field, but allows JavaScript easy access to the authentication token.  

I'm always amazed at how challenging and rewarding programing can be.  There are times I feels as if I'm struggling with everything, and it isn't until I reflect on the process that I see just how much I know and how far I have come.  It  is definately hills and valleys, ebbs and flows (please pick you metaphore), please read my blog "Climb High, Sleep Low: Coding and Climbing.  

I'm already thinking about other project, big and small, can't wait. 

# Javascript - Project 

I Promise() to CallBack()

I hated JavaScript when I first started learning it. It felt clumsy and arbitray. You had weird sounding things like Promises and Callback functions. However, despite all its weird parts, when I first  loaded some JSON data onto the DOM, using Javascript, my feelings for ever were changed. 

This project's objective is to take an existing Rails application, and incorporate Javascript. Namely, we are tasked with loading data, from our database, asyncrously onto the DOM. This means the page does not have to refresh, giving the user a better experience. The first step in achieving this is to convert your data to JSON. 

# Meet My Friend JSON
JSON, or Java Script Object Notation, is a method of formating data so it can be transferred from server to web applications. For its fancy, and fun to say, name, JSON is simply an object of strings. 

```
{
id: 1,
title: "Pappardelle alla Bolognese",
description: "Thick slices of French toast bread, brown sugar, half-and-half and vanilla, topped with powdered sugar. With two eggs served any style, and your choice of smoked bacon or smoked ham.",
instructions: "Smoked salmon, poached eggs, diced red onions and Hollandaise sauce on an English muffin. With a side of roasted potatoes.",
category: {
id: 3,
name: "Dinner"
}
```


This is JSON data. Once our data is converted to JSON, it makes it very easy to work with. There are several ways to get our data formated into JSON. For my application, I used the Rails gem Active Model Serializer. 

# Serializer()
It's easy to get the serializer gem up and working for us. We first need to install the gem in our gem file, and run `bundle install` in our console. 

```
gem 'active_model_serializers', '~> 0.10.2'
```

Now that we have serializer installed, and need to tell it which models we want it to work on. In the case of my application, we want to serialize the Recipe model and the Category model. We establihsed the necessary files by using rails generator. 

```
rails generator serializer recipe
```

and 

```
rails generator serializer category
```

This will generate a folder structure of `app/serializer`, with the two files inside the `serializer` folder, and  the serializer gem knows to look in the serializer folder. Inside these files we can choose which attributes we want serialized, and established relationships between the models. For instance, in my recipe app, recipes `belong_to` a category, and a category `has_many` recipes. 

```
class RecipeSerializer < ActiveModel::Serializer
  attributes :id, :title, :description, :instructions

  belongs_to :category
end
```

```
class CategorySerializer < ActiveModel::Serializer
  attributes :id, :name

  has_many :recipes
end
```

We establish these relationships so our data is easy to access and manipulate, once in JSON. Once we have our serializer up and running, we now use Javascipt to access and control the data. 

# JavaScript
With our data neatly formatted into objects of strings, we now need to use Javascript, or Jquery, to make a request for that data. For instance, we'll want to load all of our recipes on an index page. We know how to do this through Rails, but doing it through Javascript is a little different. To begin this, we will listen for a 'click.'

```
$('#recipe-index).on('click', (event) => {
}
```

This code targets the element with an id of 'recipe-index', using a jquery selector, and then says that `.on` a 'click' a function is going to run. This is represented by the `event`. So we can use this `event` to control things. For instance, we don't want the data to be loaded through Rails, which will load another view, refreshing the browser. We want to stop that by calling `.preventDefault()` on the 'click' `event`. We've effectively high-jacked the entire process, and now Javascript is driving. 

```
$('#recipe-index').on('click', (event) => {
    event.preventDefault();
```

We are now ready to `fetch()` our data.

# Fetch()

We now want to make an API request using `fetch()`. The fetch API allows us to access and make changes to data asychronously. We call `fetch()`, and pass in an url. 

```
fetch('/recipes.json')
```

The fetch returns a Promise.  Promise is either resolved or rejected. If the Promise is resolved, meaning we get data back from our fetch request, we can then call .then(). This will return a response. However, we must convert our response into useful JSON, and we do this by calling `.json()` on our response.  Once we've converted our response to JSON, we'll then call another promise. This promise will return the properly formatted data. 

`fetch('/recipes.json')
    .then(response => response.json())
    .then(recipes => {}`

Reading this code, as if it were a sentence, it would sound like this:

We request data from a url, using fetch(). This returns a promise, and if the promise is successful, returns a response. We convert this response to JSON, and 
then we call another promise that will return JSON data. 

From here we can then format and display our data. But we also want to make an Object Model. So each time we want to display a recipe, we pass our data into this Object Model. 

``
function Recipe(recipe) {
  this.id = recipe.id
  this.title = recipe.title
  this.description = recipe.description
  this.instructions = recipe.instructions
  this.category = recipe.category
}
``

With an object model, we can create prototype function, that we can call on our Object Model. This affords us functionality and versatility with our code. 

``
Recipe.prototype.formatIndex = function(){
  let recipeHTML = `
    <div class = "indexJSON">
      <p><a href = "/recipes/${this.id}" data-id="${this.id}" class = "recipe-link">${this.title}</a></p>
      <p>${this.description}</p>
    </div>`
  return recipeHTML
}
``

# Conclusion
Javascript, for me, is when coding went for intersting and challenging to really, REALLY fun. You begin to see the power of programming. This inpired a lot of create thoughts on what I could do with data, how I could improve existing applications, and future. I'm exciting to keep digging into Javascript, and learning as much as I can. And I'm looking forward to diving into React. 
