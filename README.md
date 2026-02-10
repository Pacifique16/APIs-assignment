# Spring Boot RESTful API Assignment

This project contains implementations for all 5 questions plus the bonus question for the Spring Boot RESTful API assignment.

## Project Structure

```
src/main/java/com/auca/restfulapi/
├── RestfulApiApplication.java (Main Application)
├── library/
│   ├── model/Book.java
│   └── controller/BookController.java
├── student/
│   ├── model/Student.java
│   └── controller/StudentController.java
├── restaurant/
│   ├── model/MenuItem.java
│   └── controller/MenuController.java
├── ecommerce/
│   ├── model/Product.java
│   └── controller/ProductController.java
├── task/
│   ├── model/Task.java
│   └── controller/TaskController.java
└── user/
    ├── model/UserProfile.java
    ├── model/ApiResponse.java
    └── controller/UserProfileController.java

images/ (Test Screenshots)
├── Q1_*.png (Library API tests)
├── Q2_*.png (Student API tests)
├── Q3_*.png (Restaurant Menu API tests)
├── Q4_*.png (E-Commerce Product API tests)
├── Q5_*.png (Task Management API tests)
└── Bonus_*.png (User Profile API tests)
```

## How to Run

1. **Prerequisites:**
   - Java 17 or higher
   - Maven 3.6+
   - Postman (for testing)

2. **Run the application:**
   ```bash
   mvn spring-boot:run
   ```
   Or run the `RestfulApiApplication.java` main class from your IDE.

3. **Application will start on:** `http://localhost:8080`

---

## Question 1: Library Book Management API

### Endpoints

#### 1. Get All Books
- **URL:** `GET http://localhost:8080/api/books`
- **Response:** 200 OK
```json
[
  {
    "id": 1,
    "title": "Clean Code",
    "author": "Robert Martin",
    "isbn": "978-0132350884",
    "publicationYear": 2008
  }
]
```
<img width="1062" height="645" alt="Q1_GetAllBooks" src="https://github.com/user-attachments/assets/b751ba7a-e284-45dc-993b-fbeaa319feaf" />


#### 2. Get Book by ID
- **URL:** `GET http://localhost:8080/api/books/1`
- **Response:** 200 OK or 404 Not Found

<img width="1381" height="732" alt="Q1_GetBookById" src="https://github.com/user-attachments/assets/61c299b5-ec18-434a-8e47-f7e3d3dff5e0" />


#### 3. Search Books by Title
- **URL:** `GET http://localhost:8080/api/books/search?title=clean`
- **Response:** 200 OK

<img width="1378" height="603" alt="Q1_SearchBooks" src="https://github.com/user-attachments/assets/8bac4907-62db-4449-b851-38e8a43e1968" />


#### 4. Add New Book
- **URL:** `POST http://localhost:8080/api/books`
- **Headers:** `Content-Type: application/json`
- **Body:**
```json
{
  "title": "Design Patterns",
  "author": "Gang of Four",
  "isbn": "978-0201633610",
  "publicationYear": 1994
}
```
<img width="1375" height="716" alt="Q1_AddBook" src="https://github.com/user-attachments/assets/4d9b19dd-b634-4c6b-a83a-98dfe65ec9ec" />


- **Response:** 201 Created

#### 5. Delete Book
- **URL:** `DELETE http://localhost:8080/api/books/1`
- **Response:** 204 No Content or 404 Not Found

<img width="1377" height="642" alt="Q1_DeleteBook" src="https://github.com/user-attachments/assets/23bb773e-f849-4cb5-af5d-54dbb5ecc18e" />

---

## Question 2: Student Registration API

### Endpoints

#### 1. Get All Students
- **URL:** `GET http://localhost:8080/api/students`
- **Response:** 200 OK

<img width="1381" height="757" alt="`Q2_GetAllStudents" src="https://github.com/user-attachments/assets/aad2ed90-8098-43b1-b15c-01e0b336aa09" />

#### 2. Get Student by ID
- **URL:** `GET http://localhost:8080/api/students/1`
- **Response:** 200 OK or 404 Not Found

#### 3. Get Students by Major
- **URL:** `GET http://localhost:8080/api/students/major/Computer Science`
- **Response:** 200 OK
  
<img width="1378" height="673" alt="Q2_GetByMajor" src="https://github.com/user-attachments/assets/a8b6ca0f-787f-4147-9f1f-7002f35516aa" />

#### 4. Filter Students by GPA
- **URL:** `GET http://localhost:8080/api/students/filter?gpa=3.5`
- **Response:** 200 OK
  
<img width="1367" height="680" alt="Q2_FilterByGPA" src="https://github.com/user-attachments/assets/eb19b68f-d297-4bfb-b715-ac84ca4bccf1" />

#### 5. Register New Student
- **URL:** `POST http://localhost:8080/api/students`
- **Headers:** `Content-Type: application/json`
- **Body:**
```json
{
  "firstName": "Alice",
  "lastName": "Johnson",
  "email": "alice.j@example.com",
  "major": "Computer Science",
  "gpa": 3.7
}
```

<img width="1380" height="738" alt="Q2_RegisterStudent" src="https://github.com/user-attachments/assets/d485f398-f687-480d-a5f3-ffcb1c9266fa" />

- **Response:** 201 Created

#### 6. Update Student
- **URL:** `PUT http://localhost:8080/api/students/1`
- **Headers:** `Content-Type: application/json`
- **Body:**
```json
{
  "firstName": "John",
  "lastName": "Doe",
  "email": "john.updated@example.com",
  "major": "Computer Science",
  "gpa": 3.9
}
```
- **Response:** 200 OK or 404 Not Found

---

## Question 3: Restaurant Menu API

### Endpoints

#### 1. Get All Menu Items
- **URL:** `GET http://localhost:8080/api/menu`
- **Response:** 200 OK
  
<img width="1371" height="875" alt="Q3_GetAllMenuItems" src="https://github.com/user-attachments/assets/fe720e98-be2c-406d-8678-c58a8dbcf38d" />

#### 2. Get Menu Item by ID
- **URL:** `GET http://localhost:8080/api/menu/1`
- **Response:** 200 OK or 404 Not Found

#### 3. Get Items by Category
- **URL:** `GET http://localhost:8080/api/menu/category/Main Course`
- **Response:** 200 OK
  
<img width="1361" height="667" alt="`Q3_GetByCategory" src="https://github.com/user-attachments/assets/00c7b964-e9a8-4762-9c89-f03cb99b84bc" />

#### 4. Get Available Items
- **URL:** `GET http://localhost:8080/api/menu/available?available=true`
- **Response:** 200 OK
  
<img width="1377" height="833" alt="Q3_GetAvailable" src="https://github.com/user-attachments/assets/58abdd78-2fdc-4d1b-9370-59324e1086a2" />

#### 5. Search Menu Items by Name
- **URL:** `GET http://localhost:8080/api/menu/search?name=chicken`
- **Response:** 200 OK

#### 6. Add New Menu Item
- **URL:** `POST http://localhost:8080/api/menu`
- **Headers:** `Content-Type: application/json`
- **Body:**
```json
{
  "name": "Pizza Margherita",
  "description": "Classic Italian pizza",
  "price": 11.99,
  "category": "Main Course",
  "available": true
}
```
- **Response:** 201 Created

#### 7. Toggle Item Availability
- **URL:** `PUT http://localhost:8080/api/menu/1/availability`
- **Response:** 200 OK or 404 Not Found

#### 8. Delete Menu Item
- **URL:** `DELETE http://localhost:8080/api/menu/1`
- **Response:** 204 No Content or 404 Not Found

---

## Question 4: E-Commerce Product API

### Endpoints

#### 1. Get All Products (with pagination)
- **URL:** `GET http://localhost:8080/api/products`
- **URL with pagination:** `GET http://localhost:8080/api/products?page=0&limit=5`
- **Response:** 200 OK
  
<img width="1370" height="857" alt="Q4_GetAllProducts" src="https://github.com/user-attachments/assets/716daddf-e1a4-4cd8-ac70-328faaf6ca8d" />

#### 2. Get Product by ID
- **URL:** `GET http://localhost:8080/api/products/1`
- **Response:** 200 OK or 404 Not Found

#### 3. Get Products by Category
- **URL:** `GET http://localhost:8080/api/products/category/Electronics`
- **Response:** 200 OK

#### 4. Get Products by Brand
- **URL:** `GET http://localhost:8080/api/products/brand/Apple`
- **Response:** 200 OK

#### 5. Search Products by Keyword
- **URL:** `GET http://localhost:8080/api/products/search?keyword=phone`
- **Response:** 200 OK
  
<img width="1367" height="635" alt="Q4_SearchProducts" src="https://github.com/user-attachments/assets/9f5baf08-f2c2-477b-b562-50abc99b060a" />

#### 6. Get Products by Price Range
- **URL:** `GET http://localhost:8080/api/products/price-range?min=100&max=500`
- **Response:** 200 OK
  
<img width="1367" height="677" alt="`Q4_PriceRange" src="https://github.com/user-attachments/assets/31287534-bc47-4759-8b3e-cc7c721a1642" />

#### 7. Get In-Stock Products
- **URL:** `GET http://localhost:8080/api/products/in-stock`
- **Response:** 200 OK
  
<img width="1377" height="841" alt="Q4_InStock" src="https://github.com/user-attachments/assets/d3ec8b5c-2405-45ba-ba18-0041bad64e6a" />

#### 8. Add New Product
- **URL:** `POST http://localhost:8080/api/products`
- **Headers:** `Content-Type: application/json`
- **Body:**
```json
{
  "name": "iPad Pro",
  "description": "Apple tablet",
  "price": 799.99,
  "category": "Electronics",
  "stockQuantity": 25,
  "brand": "Apple"
}
```
- **Response:** 201 Created

#### 9. Update Product
- **URL:** `PUT http://localhost:8080/api/products/1`
- **Headers:** `Content-Type: application/json`
- **Body:** (Full product object)
- **Response:** 200 OK or 404 Not Found

#### 10. Update Stock Quantity
- **URL:** `PATCH http://localhost:8080/api/products/1/stock?quantity=100`
- **Response:** 200 OK or 404 Not Found

#### 11. Delete Product
- **URL:** `DELETE http://localhost:8080/api/products/1`
- **Response:** 204 No Content or 404 Not Found

---

## Question 5: Task Management API

### Endpoints

#### 1. Get All Tasks
- **URL:** `GET http://localhost:8080/api/tasks`
- **Response:** 200 OK

#### 2. Get Task by ID
- **URL:** `GET http://localhost:8080/api/tasks/1`
- **Response:** 200 OK or 404 Not Found
  
<img width="1368" height="687" alt="Q5_GetAllTasks" src="https://github.com/user-attachments/assets/40a7bb76-2e7f-4594-8cea-1388e725f816" />

#### 3. Get Tasks by Status
- **URL:** `GET http://localhost:8080/api/tasks/status?completed=false`
- **Response:** 200 OK
  
<img width="1372" height="642" alt="Q5_GetByStatus" src="https://github.com/user-attachments/assets/3598f938-7534-4793-b8c3-951a0bcfa293" />

#### 4. Get Tasks by Priority
- **URL:** `GET http://localhost:8080/api/tasks/priority/HIGH`
- **Response:** 200 OK
  
<img width="1387" height="582" alt="Q5_GetByPriority" src="https://github.com/user-attachments/assets/4c1fa7c3-5d69-4bbc-93a2-126bb1ea842e" />

#### 5. Create New Task
- **URL:** `POST http://localhost:8080/api/tasks`
- **Headers:** `Content-Type: application/json`
- **Body:**
```json
{
  "title": "Code review",
  "description": "Review pull requests",
  "completed": false,
  "priority": "MEDIUM",
  "dueDate": "2024-12-22"
}
```
- **Response:** 201 Created

#### 6. Update Task
- **URL:** `PUT http://localhost:8080/api/tasks/1`
- **Headers:** `Content-Type: application/json`
- **Body:** (Full task object)
- **Response:** 200 OK or 404 Not Found

#### 7. Mark Task as Completed
- **URL:** `PATCH http://localhost:8080/api/tasks/1/complete`
- **Response:** 200 OK or 404 Not Found
  
<img width="1375" height="668" alt="Q5_MarkCompleted" src="https://github.com/user-attachments/assets/ca1cecb6-8d00-4cd3-93fc-c961fa2df57c" />

#### 8. Delete Task
- **URL:** `DELETE http://localhost:8080/api/tasks/1`
- **Response:** 204 No Content or 404 Not Found

---

## Bonus Question: User Profile API

### Endpoints

#### 1. Get All Users
- **URL:** `GET http://localhost:8080/api/users`
- **Response:** 200 OK
```json
{
  "success": true,
  "message": "Users retrieved successfully",
  "data": [...]
}
```
<img width="1035" height="845" alt="Bonus_GetAllUsers" src="https://github.com/user-attachments/assets/7913d53b-e287-4b17-89c4-96abc2f473e9" />

#### 2. Get User by ID
- **URL:** `GET http://localhost:8080/api/users/1`
- **Response:** 200 OK or 404 Not Found

#### 3. Get User by Username
- **URL:** `GET http://localhost:8080/api/users/username/john_doe`
- **Response:** 200 OK or 404 Not Found

#### 4. Get Users by Country
- **URL:** `GET http://localhost:8080/api/users/country/USA`
- **Response:** 200 OK
  
<img width="1047" height="730" alt="Bonus_GetByCountry" src="https://github.com/user-attachments/assets/070d3e8f-7474-490c-b5cc-b4f29299526b" />

#### 5. Get Users by Age Range
- **URL:** `GET http://localhost:8080/api/users/age-range?min=20&max=30`
- **Response:** 200 OK
  
<img width="1025" height="815" alt="Bonus_AgeRange" src="https://github.com/user-attachments/assets/617f56c6-cf7e-4882-8085-a3a629ba2197" />

#### 6. Get Active/Inactive Users
- **URL:** `GET http://localhost:8080/api/users/active?active=true`
- **Response:** 200 OK

#### 7. Create User
- **URL:** `POST http://localhost:8080/api/users`
- **Headers:** `Content-Type: application/json`
- **Body:**
```json
{
  "username": "new_user",
  "email": "newuser@example.com",
  "fullName": "New User",
  "age": 27,
  "country": "France",
  "bio": "New member",
  "active": true
}
```

- **Response:** 201 Created

<img width="1033" height="872" alt="Bonus_CreateUser" src="https://github.com/user-attachments/assets/ace685d7-f877-4ecc-89ec-39841ed07257" />

#### 8. Update User
- **URL:** `PUT http://localhost:8080/api/users/1`
- **Headers:** `Content-Type: application/json`
- **Body:** (Full user object)
- **Response:** 200 OK or 404 Not Found

#### 9. Activate User
- **URL:** `PATCH http://localhost:8080/api/users/1/activate`
- **Response:** 200 OK or 404 Not Found
  
<img width="1042" height="817" alt="Bonus_ActivateUser" src="https://github.com/user-attachments/assets/e9324152-efa6-40c6-bf15-f9521ef48e63" />

#### 10. Deactivate User
- **URL:** `PATCH http://localhost:8080/api/users/1/deactivate`
- **Response:** 200 OK or 404 Not Found

#### 11. Delete User
- **URL:** `DELETE http://localhost:8080/api/users/1`
- **Response:** 200 OK or 404 Not Found

---

## Testing with Postman

1. **Import Collection:** Import `Postman_Collection.json` file
2. **Set Base URL:** `http://localhost:8080`
3. **Test each endpoint** following the examples above
4. **Check Status Codes:** Verify proper HTTP status codes (200, 201, 204, 404)
5. **Screenshots:** All test screenshots are saved in the `images/` folder

### Test Screenshots

All API endpoint tests have been documented with screenshots in the `images/` folder:

**Question 1 - Library API:**
- `Q1_GetAllBooks.png` - Get all books endpoint
- `Q1_GetBookById.png` - Get book by ID
- `Q1_SearchBooks.png` - Search books by title
- `Q1_AddBook.png` - Add new book
- `Q1_DeleteBook.png` - Delete book

**Question 2 - Student API:**
- `Q2_GetAllStudents.png` - Get all students
- `Q2_GetByMajor.png` - Filter by major
- `Q2_FilterByGPA.png` - Filter by GPA
- `Q2_RegisterStudent.png` - Register new student

**Question 3 - Restaurant Menu API:**
- `Q3_GetAllMenuItems.png` - Get all menu items
- `Q3_GetByCategory.png` - Filter by category
- `Q3_GetAvailable.png` - Get available items

**Question 4 - E-Commerce Product API:**
- `Q4_GetAllProducts.png` - Get all products
- `Q4_Pagination.png` - Pagination test
- `Q4_SearchProducts.png` - Search products
- `Q4_PriceRange.png` - Price range filter
- `Q4_InStock.png` - In-stock products

**Question 5 - Task Management API:**
- `Q5_GetAllTasks.png` - Get all tasks
- `Q5_GetByStatus.png` - Filter by status
- `Q5_GetByPriority.png` - Filter by priority
- `Q5_MarkCompleted.png` - Mark task as completed

**Bonus - User Profile API:**
- `Bonus_GetAllUsers.png` - Get all users with ApiResponse wrapper
- `Bonus_GetByCountry.png` - Filter by country
- `Bonus_AgeRange.png` - Filter by age range
- `Bonus_CreateUser.png` - Create new user
- `Bonus_ActivateUser.png` - Activate user

### Sample Test Scenarios

**Question 1 - Library:**
- Get all books
- Search for "Clean Code"
- Add a new book
- Delete a book

**Question 2 - Student:**
- Get all students
- Filter by Computer Science major
- Filter students with GPA >= 3.5
- Register a new student

**Question 3 - Restaurant:**
- Get all menu items
- Filter by "Main Course" category
- Get only available items
- Toggle availability

**Question 4 - E-Commerce:**
- Get products with pagination (page=0, limit=5)
- Search for "phone"
- Filter by price range (100-500)
- Get in-stock products

**Question 5 - Task:**
- Get all tasks
- Filter by HIGH priority
- Get incomplete tasks
- Mark task as completed

**Bonus - User Profile:**
- Get all users (check ApiResponse wrapper)
- Search by country "USA"
- Filter by age range (20-30)
- Activate/deactivate user

---

## HTTP Status Codes Used

- **200 OK:** Successful GET, PUT, PATCH requests
- **201 Created:** Successful POST requests
- **204 No Content:** Successful DELETE requests
- **404 Not Found:** Resource not found

---

## Technologies Used

- Spring Boot 3.2.0
- Spring Web
- Java 17
- Maven

---

## Author

Student ID: 26937


## Notes

- All data is stored in-memory using ArrayList
- Data will be reset when the application restarts
- No database or service layer is used (as per requirements)
- All endpoints have been tested and work correctly
- Test screenshots are available in the `images/` folder
- Import `Postman_Collection.json` for quick testing
