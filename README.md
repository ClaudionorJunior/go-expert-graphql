sqlite3 data.db
create table categories (id string, name string, description string);
create table courses (id string, name string, description string, category_id string);


http://localhost:8080/
go run github.com/99designs/gqlgen generate

mutation createCategory {
  createCategory(input: {name: "Tecnologia", description: "Cursos de tecnologia"}), {
    id
    name
    description
  }
}

mutation createCourse {
  createCourse(input: {name: "My Course", description: "The Course", categoryId: "4510aa84-6301-482d-9958-d53adb2c8159"}), {
    id
    name
    description
  }
}

query queryCategories {
  categories {
    id
    name
    description
  }
}

query queryCourses {
  courses {
    id
    name
    description
  }
}

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