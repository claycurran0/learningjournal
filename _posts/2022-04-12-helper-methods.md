---
layout: post
title: Helper Methods
---

Last quarter I took Application Development I, which provided a foundation to the building blocks of rails applications. In Application Development II, we are augmenting these foundational elements with more advanced techniques for code refactoring, improvements to user experience, and security enhancements. This week we focused on refactoring with rails helper methods - widely used shortcuts that cut down excess code and improve code readability. 

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

Now, since this is the root route (the landing page with no URL extentions), we can shorten this specific route to:
````ruby
root "movies#index"
````

So much simpler!

#### **2) Link_to and form_width**




