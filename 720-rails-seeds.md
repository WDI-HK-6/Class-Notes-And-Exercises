# Rails Seeds File

##What It Is
The seeds.rb file adds default data to your database. It is very useful because adding data manually into your database whenever you do a ```rake db:drop``` is very cumbersome.

###Simple Example

Go into  ```db/seeds.rb``` and add something like:
```ruby
# Adds a default user so you don't have to keep on re-registering if your database drops
User.create(:email => "none@none.com", :password => '12345678', :password_confirmation => "12345678")

Post.create(title: 'My Trip to Germany', content: 'lorem ipsum')
Post.create(title: 'Chicken Soup', content: 'lorem ipsum valar dorit')
Post.create(title: 'How to Repair a Motorcycle', content: 'lorem ipsum morgul dorit')
Post.create(title: 'Riding Horses', content: 'lorem ipsum ')
```

Note that the code in ```seeds.rb``` isn't magic. It's the exact same code that you would normally type to create new users and posts in your Rails app and Rails console.

***```seeds.rb``` can be run by doing ```rake db:seed``` in the command line (usually done after ```rake db:drop```.***

### Example with Relationships
```ruby
# creates default users
user1 = User.create(:email => "user1@none.com", :password => '12345678', :password_confirmation => "12345678")

user2 = User.create(:email => "user2@none.com", :password => '12345678', :password_confirmation => "12345678")

# creates default posts linked to a user_id
post1 = Post.create(title: 'My Trip to Germany', content: 'lorem ipsum', user_id: user1[:id])

post2 = Post.create(title: 'Chicken Soup', content: 'lorem ipsum valar dorit', user_id: user1[:id])

post3 = Post.create(title: 'How to Repair a Motorcycle', content: 'lorem ipsum morgul dorit', user_id: user2[:id])

post4 = Post.create(title: 'Riding Horses', content: 'lorem ipsum ', user_id: user2[:id])

# creates default comments linked to a post_id and user_id
Comment.create(content: "Great post.", post_id: post1[:id], user_id: user2[:id)

Comment.create(content: "I liked the other post better.", post_id: post2[:id], user_id: user2[:id)
```

### Example with Loops
```ruby
# creates 5 default users, posts, and comments.

5.times do |i|

  user = User.create(:email => "user#{i}@none.com", :password => '12345678', :password_confirmation => "12345678")
  
  post = Post.create(title: "Post ##{i}", content: "Content for post ##{i}.", user_id: user[:id])
  
  comment = Comment.create(content: "Content for post ##{i}.", post_id: post[:id], user_id: user[:id])
  
end
```