# Using fetch - DELETE

## Learning Goals

- Explain how to remove data from the backend using DELETE

## Introduction

The final piece of our CRUD actions - DELETE. With this last piece of knowledge,
we'll be able to set up Frontends that can initiate any kind of `fetch` request
to our server - Creating data with `POST`, Reading data with `GET`, Updating
data with `PATCH`, and now, finally, Deleting data with `DELETE`.

## Configuring a DELETE Request

Configuring a `DELETE` request is actually similar to configuring a `POST` and
`PATCH` request. Because `fetch` executes a `GET` request by default, we need to
pass in an extra configuration object to `fetch` to tell it to initiate a
`DELETE` request.

However, _unlike_ a `POST` and `PATCH` request, a `DELETE` request only requires
one piece of information in its configuration object - the `method`:

```JavaScript
const deleteObj = {
    method: "DELETE"
};
```

Like a `PATCH` request, we also have to include a specific `Id` within the URL,
to tell the server which resource we want deleted.

With our `DELETE` configuration object and our URL pointing the server toward
the correct resource, a `DELETE` request might look something like this:

```JavaScript
fetch(`http://localhost:3000/data/${id}`, deleteObj);
```

## Handling a DELETE Response

Unlike `GET`, `POST`, and `PATCH`, a `DELETE` request will _not_ send back any
data from the server once it's completed. The server will still send a response,
but it won't include any data from our database.

Because of this, we'll only need a single `.then` statement following a `DELETE`
request, which we can use to run whatever code we want to execute once the
`DELETE` request has completed.

As with the other HTTP Methods, we'll also want to make sure we incorporate
error handling via `.catch`.

```JavaScript
fetch(`http://localhost:3000/data/${id}`, deleteObj)
    .then(() =>{
        // add code to run once DELETE request is finished
    })
    .catch(error =>{
        console.error(error)
    });
```

## Conclusion

And that's it! You now have the ability to initiate full CRUD from the Frontend!

Now that you've covered JavaScript Fundamentals, DOM Manipulation, Event
Handling, and Communication with the Server, you're ready to start building
fully functional websites.

The next step is to start connecting all of these tools and concepts together.
We'll start workking through that together in the coming sections.

## Resources

- [MDN Fetch
  Documentation](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)
