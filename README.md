# Rock Paper Scissors

We are going to build a simple game. Users are allowed to choose Rock, Paper, or Scissors by visiting one of the following URLs:

 - [http://localhost:3000/rock](http://localhost:3000/rock)
 - [http://localhost:3000/paper](http://localhost:3000/paper)
 - [http://localhost:3000/scissors](http://localhost:3000/scissors)

And we will tell them whether they won or lost.

#### [Here is the target you will ultimately build.](https://rps-rcav-target.herokuapp.com)

## Project Specific Setup

1. Fork and clone as usual.
1. `cd` into the folder you downloaded.
1. `bundle install` (or `bundle` for short)
1. `rails server` (or `rails s` for short)
1. Navigate to [http://localhost:3000](http://localhost:3000) in Chrome — there's nothing there but the default Rails welcome screen!
1. **This is a brand new, untouched Rails application.** All we've done is run the command `rails new rps_rcav` to generate the basic structure of folders and files you see in your editor's sidebar, and we've added the instructions you're reading in this README.

   **You could generate a brand new Rails app yourself right now by doing the same thing:**

   1. Open a terminal window and `cd` to the folder where you store your code.
   1. `rails new your_own_app_name`
   1. `cd your_own_app_name`
   1. `rails s`

   That's it! You'd then see the same welcome screen at [http://localhost:3000](http://localhost:3000), and you would be ready to start building out your Rails app.

## Route → Controller → Action → View

This is currently a brand new Rails app, with absolutely no routes, controllers, etc.

Add support for [each](http://localhost:3000/rock) [of](http://localhost:3000/paper) [our](http://localhost:3000/scissors) three URLs one at a time. For each one,

 1. Connect the [RCAV dots](https://guides.firstdraft.com/rcav-flowchart.html) and display "Hi!" to prove that you did so. Make up whatever names you want for the controller and action.
 1. Now step back into the action and write some logic to determine whether the player won or lost. Put the computer move and the outcome into instance variables.
 1. In the view template, display the instance variables. Format it a little with some markup and some copy.

## Optional Challenges

Once you have completed the above for all three URLs,

 1. On each page, add links to get to the other two pages (so that our users don't have to keep typing into the address bar).
 1. We've already connected `bootstrap.css`, so you can just start using the [Bootstrap classes and components](http://getbootstrap.com/components/#btn-groups) in your view templates.
 1. You can also add any images that you like to the `public/` folder, and use them as the `src` for `<img>`s.

    For example, if you create a file called `public/rock_image.jpg`, you can use it in like this:

    ```html
    <img src="/rock_image.jpg">
    ```

    Notice that the file just get served directly from the root of the domain if you place it directly in the `public/` folder. You can also create subfolders to keep things organized, if you like.

 1. That said, [Font Awesome](http://fontawesome.io/icons/) has icons for rock, paper, and scissors. Find them and use them. Font Awesome is already connected this project, so you can just start adding [the icons](http://fontawesome.io/icons/).
 1. If you want to, you can also create another stylesheet for additional styles in the `public/` folder and link to that (for example, if you want to add our standard vertical spacers).
 1. You will find the `<head>` of _all_ of our view templates in the file `app/views/layouts/application.html.erb`, which is a wrapper or "layout" that surrounds every view template that we send to our users.

    If you go examine the `application.html.erb` file that we got out-of-the-box when we ran `rails new`, you'll see that it includes all of the usual HTML boilerplate -- `<!DOCTYPE>`, `<html>`, etc.

    Notice the line that says `<%= yield %>.` That is where the contents of our view templates get plugged in before the entire response gets sent to our users' browsers.

    This is a great way to DRY (Don't Repeat Yourself) up repetitive markup like navbars, footers, links to stylesheets, etc. It's one of _many_ advantages to using a dynamic framework like Rails over writing static HTML.
 1. Add a root URL such that visiting the bare domain, [http://localhost:3000](http://localhost:3000), leads to a landing page with some information about the game. (Hint: the first argument of the route will just be the plain slash, like so:

        get("/", { # etc ...
