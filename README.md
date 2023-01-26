# Routing system in SSL3.IO
Documentation for SSL3.IO routing system

## What is a route

A route is the part of the link (or url) that explain where we want to go when we browse something with a web browser. For example, when we go to `https://ssl3.io/hello`, we want to browse `/hello`. If the route exists, or the file exists (like `https://ssl3.io/dashboard.html`), the server we connect to will send us the data corresponding to this route.

## Parameters

Sometime, we need dynamics route, for example to show a different product or blog post, without creating thousands of routes. In this case, we will use a `parameter` character in our url. With SSL3.IO, a parameter starts with `:`.

For example: `/product/:id`

In this case, all the urls like `/product/1` or `/product/shoes` will call this route. In your lambda function, you will be able to access the `id` parameter with:

```js
req.param.id
```

In the case this parameter is not required, you can add a `?` after the parameter name. Like this, the url `/product` could be used to show all the products.

For example: `/product/:id?`

## Wildcards

A wildcard is used to catch all characters in an URL. The difference with a parameter is that it won't load a `param` property.

For example: `/blog/*`

This route will catch all urls starting by `/blog/`. So, `/blog/1` or `/blog/123/456/hello` will call this route.
