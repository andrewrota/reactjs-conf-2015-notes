**graphQL** is the method for defining the data your component needs...the 'response shape'.  Can be used with or without react.

You can exactly predict what will come back in the response from the query.

Cursors allow us to efficiently paginate.

Colocation of data queries with rendering logic. Rather than having data passed through multiple layers, you want the data to be defined in the component itself.

Parent component asks children for the data they need, combine them in one query, and make the request to the server in one go.

    ${ProfilePic.getQuery('user')}

If someone changes a child component to fetch a little more data, the parent component doesn't need to be updated.

**Lifecycle**

Parent query is made up of the queries from its children.  Flatten the queries and dedupe them.  Server responds with data shape that's requested.  Take that data and put it in a general store that is a central source of truth for data from graphQL.  Data is stored in the generic store for all the graphQL data.  Now you can render the views with this data.

Static View --> Query --> Server --> Data --> Store --> Views

Makes it harder to make mistakes like overfetching and underfetching.

**Relay**: React application framework that's the next evolution of flux.  Rather than having components pass data to their children, the components declare the data they need and have it be satisfied automatically by Relay.