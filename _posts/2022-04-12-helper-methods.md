---
layout: post
title: Helper Methods
---

Last quarter I took Application Development I, which provided a foundation to the building blocks of rails applications. In Application Development II, we are augmenting these foundational elements with more advanced techniques for code refactoring, improvements to user experience, and security enhancements. This week we focused on refactoring with rails helper methods - widely used shortcuts that cut down excess code and improve readability. 

*Here are a few of my key takeaways:*

#### **1) Refactoring Routes**
Initially, we learned to write out our routes the long way, e.g.:

```ruby
get("/", { :controller => "movies", action, "index"} )
```

This can be significantly cut down! First, we can shorten the entire line of code to:
```ruby
get "/" => "movies#index"
```

Since the convention is `{ :controller => x, :action => y }`, rails assumes our desired output given this octothorpe syntax.

Now, since this is the root route (the landing page with no URL extension), we can shorten this specific route to:
````ruby
root "movies#index"
````

So much simpler!

We can make it even easier to call our routes thorughout our files by passing our own path and url route methods. To create one of these methods, simply add the name after the route designation: 
```ruby
get "/directors" => "directors#index", as: :directors 
```

Just like that, we've defined the `:directors` method to register a url or a route path depending on how we call it. We'll get more into that in the next section.

#### **2) Link_to and form_with**
Some helper methods are used to produce actual HTML elements. With a simple call to one of these methods, lines or blocks of ugly code can be automatically produced on the backend in the rendered page. The first examplee is `link_to`.

In HTML, if we wanted to render a link, we'd type something like this:
````ruby
<a href="/directors">Directors</a>
````

Here's how we can use `link_to` to simplify this:
````ruby
<%= link_to directors_path %>
````

Notice we called `directors_path`. This was a method that we created earlier when we added `as: :directors` to the route method. This improves readability, but perhaps more importantly it creates substantially more flexibility to modify our app. For example, if we wanted to change the `/directors' url to '/all', we could simply change the route file, and wouldn't need to go through our files to change every call to the route. Major time saver!

