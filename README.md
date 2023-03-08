$ git checkout -b styling

git fetch
From github.com:ludingji/blog_application
   177b9d7..6716add  main       -> origin/main
git status
Your branch is behind 'origin/main' by 3 commits, and can be fast-forwarded.
git pull
$ git checkout -b add_blog_posts
Switched to a new branch 'add_blog_posts'

$ rails g scaffold post title body:text
$ rails db:migrate

$ rails c
Post.new
@post=Post.new(title: "hello World!", body:"This is my first post!")
@post.save
Post.create is the same as new

@post=Post.find(1)

@post=Post.first
@post=Post.last
@post=Post.last(2)
it will give the last two post created

Scaffold will create controller, 

rails c


rails db:seed

$ rails g migration add_views_to_posts views:integer
add_column :posts, :views, :integer, default: 0

rails g devise:install
       <p class="notice"><%= notice %></p>
       <p class="alert"><%= alert %></p>

$ rails g devise User
$ rails db:migrate

elsif not elseif

Devise 4.8.1 + Rails 7.0.0 | Undefined method 'user_url' #5439 
go to gem devise website check issue#5439


$ rails g migration add_user_to_posts user:belongs_to

rails g devise:views

rails g devise:controllers users

change routes

  devise_for :users, controllers:{
    sessions: 'users/sessions'
    registrations: 'users/registrations'
  }

  def configure_account_update_params
    devise_parameter_sanitizer.permit(:account_update, keys: [:name])
  end


  rails g controller users profile

  class ChangeViewsForUsers < ActiveRecord::Migration[7.0]
  def change
    change_column :users, :views, :integer, default: 0
  end
end