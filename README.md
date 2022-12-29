# Descrição do projeto:
Esse projeto faz parte do curso Go Expert da [FullCycle](https://fullcycle.com.br/). Foi desevolvido a partir dos aprendizados de como construir uma API com GraphQL.<br>
É uma API que possui um `querys` e `mutations` para `courses` e `categories`.
<br><br>
<img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/ClaudionorJunior/go-expert-graphql">

# Configurando o DB:
```sh
cd cmd/server && sqlite3 data.db
create table categories (id string, name string, description string);
create table courses (id string, name string, description string, category_id string);
```

# Rodando o projeto:
```sh
cd cmd/server && go run main.go
```

# Atualizando GraphQL
```sh
go run github.com/99designs/gqlgen generate
```

# Mutations e Querys possíveis 

```javscript
mutation createCategory {
  createCategory(input: {name: "Tecnologia", description: "Cursos de tecnologia"}), {
    id
    name
    description
  }
}
```

```javscript
mutation createCourse {
  createCourse(input: {name: "My Course", description: "The Course", categoryId: "4510aa84-6301-482d-9958-d53adb2c8159"}), {
    id
    name
    description
  }
}
```

```javscript
query queryCategories {
  categories {
    id
    name
    description
  }
}
```

```javscript
query queryCourses {
  courses {
    id
    name
    description
  }
}
```

```javscript
query queryCategoriesWithCourses {
  categories {
    id
    name
    courses {
      id
      name
    }
  }
}
```

```javscript
query queryCoursesWithCategories {
  courses {
    id
    name
     category {
      id
      name
      description
    }
  }
}
```

## Autor
<table>
  <tr>
    <th><img src="https://avatars.githubusercontent.com/u/82416762?v=4" width=60></th>
  </tr>
  <tr>
    <td><a href="https://github.com/ClaudionorJunior">Github</a></td>
  </tr>
  <tr>
    <td><a href="https://www.linkedin.com/in/claudionorsilva">Linkedin</a></td>
  </tr>
</table>
