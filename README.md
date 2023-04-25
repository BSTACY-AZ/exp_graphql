# exp_graphql
Using express server with GraphQL to perform CRUD operations

# Description
This was written as the result of an exercise within the MIT xPro Full Stack with MERN course, module 24. The concepts covered by this particular module were intended to incorporate graphQL queries to perform CRUD operations on a list of restaurants

# Languages
javaScript/GraphQL/Express

# Installation/Usage (requires Node.js version 14.x.x)
1) Extract all contents to a folder
2) from a terminal line enter "node.js indexRestSoln.js" and hit enter
3) Navigate to localhost:5500/GraphQL
4) Use any of the following queries from the GraphiQL interface: 

```
query getRestaurants {
  restaurants {
    id
    name
    description
    dishes{
      name
      price
    }
  }
}

query getRestaurant($iid:Int=1){
  restaurant(id:$iid){
    name
    description
    
  }
}

mutation setRestaurants{
  setrestaurant(input:{
    
    id:3,
    name: "Granite",
    description:"American"}){
    name
    description
  }
}

mutation deleteRestaurants($iid: Int = 3) {
  deleterestaurant(id: $iid) {
    ok
  }
}

mutation editRestaurants($idd: Int = 1, $name: String = "OLDO") {
  editrestaurant(id: $idd, name: $name) {
    name
    description
  }
}
```
# Roadmap
In the future I would like to update the code for this project to: 
1) Auto increment the id values. Initially Id values were not provided with the starter code so even after completing the coursework correctly any query leveraging an id would not execute correctly. I added id to the schema and each record accordingly but this is not an ideal solution. Each entry should ultimately have a unique id which is never re-used. 
