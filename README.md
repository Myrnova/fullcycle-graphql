# fullcycle-graphql

## Graphql
! means that is a required value
input helps we set data insertion as it is going to say what graphql may accept as parameters
query is selections we want to do
mutation is all mutations, when you are changing infos in a model, creating, deleting or updating
when you are querying a model so that graphql can resolve this model problem it is going to execute a resolver and when we want to inject our database to graphql we use that resolver that was generated as an empty struct and add our info there
A nested object is like a Matryoshka doll where one object placed inside another and you can choose to not open the next level — a perfect usecase to demonstrate the power of GraphQL.


category, err := r.CategoryDB.Create(input.Name, *input.Description) as description is not an required input it is not necessary to send a reference that is why we use the *

## Mutation
```
mutation CreateCategory {
  createCategory(input: {name: "Tecnologia", description: "Cursos de tecnologia"}) {
    id
    name
    description
  }
}
```



```
mutation CreateCourse {
  createCourse(input: {name: "FullCycle", description: "Curso de tecnologia fullcycle", categoryId: "idsadas"}) {
    id
    name
    description

  }
}
```

## Query
```
query GetCategories {
  categories {
    id
    name
    description
    courses {
      name
      desc
    }
  }
}
```

```
query GetCourses {
  courses {
    id
    name
    description  
    category {
      name
      description
    }
  }
}
```

