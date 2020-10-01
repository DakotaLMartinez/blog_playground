# Getting started on a rails playground project

1. Get into the directory in your terminal where you want your project to be (using the `cd` command)
2. run `rails new blog_playground -T` to generate a new rails app without minitest (an alternative to rspec).
3. run `ls` to check that `blog_playground` is there after the `rails new` command completes.
4. run `code blog_playground` to open up the project in a separate VSCode window.
5. add all changes to git: `git add .`
6. make first commit: `git commit -m "initial commit"`
7. Create repository on github by visiting https://github.com/new 
8. Fill in the repository name (blog_playground in this case) and a description if you want, but leave the license, readme, and other checkboxes at the bottom unchecked. Create the repo and you should see blocks of code with instructions on getting started.
9. Click the clipboard by the second block of code under the heading Push an existing repository from the command line.
10. Return to VSCode terminal and paste in commands from GitHub.
11. Once previous step is complete, return to GitHub and refresh the page.
12. If all went well, you should see your code on GitHub in the browser.

## How to use Branches.

If I want to try out an idea, but I'm not sure I'm going to keep it long term. I can create a branch and make the change on that branch, that way I can safely try things without breaking something that I know works.

Commands to know:
```
git branch
```
shows a list of branches and also the one that we have currently checked out.
```
git checkout
```
This command allows you to checkout an existing branch. When you do this, you need to make sure that your working directory is clean. If you have changes that you haven't committed, you'll need to commit (or stash) them before you switch branches.
```
git checkout -b new_branch_name
```
This command will create and checkout a new branch. This does not require a commit beforehand. Any changes you have that aren't currently committed can be applied to the new branch after you create it with this command.

## Generators

### Resource
```
rails g resource coupon coupon_code:string store:string -s
```
This will create the model and the migration with the columns we specified. It also creates the controller file (and spec for it) the helper file (and spec for it). It will create the views path for the controller if it doesn't already exist and it will add resources to the routes for coupons and also create the asset files. 
### Model 
```
rails g model create_coupons coupon_code:string store:string -s
```
This will create both the model and the migration and set the columns we specified in the create_table block. This will also create a model spec (and fixtures depending on what test framework you're using) but -s will make sure you don't override anything that's already there.
### Controller
```
rails g controller coupons -s
```
Creates a controller, a views directory, an assetts file (scss and coffeescript depending on rails version and config), also creates a helper file and generally specs as well. If we add the -s flag, it will skip generating files that already exist and this is great for learn labs that already have specs because generators generally add specs as well, but we don't want that if we're doing a lab that already has specs.
### Migration
```
rails g migration create_coupons coupon_code:string store:string
```
this would create the migration in which you would call create_table and add the columns coupon_code and store.
This one doesn't create a model or any specs, just the migration

### Scaffold
Creates everything and actually fills in all of your controller and view logic so you have working RESTful routes for that resource. This is rarely used because it generally requires to remove and rework things to get what you actually want (it does more than you need/or different things than you need more often than not)

Also, you can reverse