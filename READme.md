# golang com graphQL

inicializar e criar pastas com:
https://gqlgen.com/

gqlgen libera uma interface para enviar requisições graphQL

para atualizar de acordo com o schema.
go run github.com/99designs/gqlgen generate 


exemplo de chamadas:

mutation createCategory {
  createCategory(input: {name:"musica", description:"Cursos de teste"}){
    id
    name
    description
  }
}

query queryCategories {
  categories{
    id
    name
    description
  }
}

query queryCategoriesWithCourses {
  categories{
    id
    name
    courses {
      id
      name
    }
  }
}

mutation createCourse {
  createCourse(input: {name: "Test msuica Cycle",description: "The baaest", categoryID: "b9349790-b5eb-4c3b-8236-74db1f3696d4"}){
    id
    description
    name
  }
}


query queryCourses {
  courses{
    id
    name
  }
}

query queryCoursesWithCategory {
  courses{
    name
    description
    category{
      name
    }
  }
}
