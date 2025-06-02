[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=19690156&assignment_repo_type=AssignmentRepo)
# Express.js RESTful API

A RESTful API built with Express.js that implements CRUD operations for a products resource.

## 🚀 Features

- RESTful API endpoints for products
- Custom middleware for logging and authentication
- Error handling
- Advanced features including:
  - Pagination
  - Filtering by category
  - Search functionality
  - Product statistics

## 📋 Prerequisites

- Node.js (v18 or higher)
- npm (Node Package Manager)

## 🛠️ Installation

1. Clone the repository
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create a `.env` file in the root directory with the following variables:
   ```
   PORT=3000
   API_KEY=your-secret-api-key-here
   ```

## 🚀 Running the Server

```bash
node server.js
```

The server will start on port 3000 (or the port specified in your .env file).

## 📚 API Documentation

### Authentication
All API endpoints require an API key to be passed in the request headers:
```
X-API-Key: your-api-key
```

### Endpoints

#### Products

1. **List All Products**
   - GET `/api/products`
   - Query Parameters:
     - `category`: Filter by category
     - `page`: Page number (default: 1)
     - `limit`: Items per page (default: 10)

2. **Get Product by ID**
   - GET `/api/products/:id`

3. **Create Product**
   - POST `/api/products`
   - Body:
     ```json
     {
       "name": "Product Name",
       "description": "Product Description",
       "price": 99.99,
       "category": "Category",
       "inStock": true
     }
     ```

4. **Update Product**
   - PUT `/api/products/:id`
   - Body: Same as Create Product (all fields optional)

5. **Delete Product**
   - DELETE `/api/products/:id`

6. **Search Products**
   - GET `/api/products/search?query=searchterm`

7. **Get Product Statistics**
   - GET `/api/products/stats`

## 🔍 Example Requests

### Create a Product
```bash
curl -X POST http://localhost:3000/api/products \
  -H "Content-Type: application/json" \
  -H "X-API-Key: your-api-key" \
  -d '{
    "name": "Sample Product",
    "description": "This is a sample product",
    "price": 29.99,
    "category": "Electronics",
    "inStock": true
  }'
```

### Get All Products
```bash
curl http://localhost:3000/api/products \
  -H "X-API-Key: your-api-key"
```

## ⚠️ Error Handling

The API returns appropriate HTTP status codes and error messages:

- 200: Success
- 201: Created
- 400: Bad Request
- 401: Unauthorized
- 404: Not Found
- 500: Internal Server Error

## 📝 License

This project is licensed under the MIT License.

## Files Included

- `Week2-Assignment.md`: Detailed assignment instructions
- `server.js`: Starter Express.js server file
- `.env.example`: Example environment variables file

## Requirements

- Node.js (v18 or higher)
- npm or yarn
- Postman, Insomnia, or curl for API testing

## Submission

Your work will be automatically submitted when you push to your GitHub Classroom repository. Make sure to:

1. Complete all the required API endpoints
2. Implement the middleware and error handling
3. Document your API in the README.md
4. Include examples of requests and responses

## Resources

- [Express.js Documentation](https://expressjs.com/)
- [RESTful API Design Best Practices](https://restfulapi.net/)
- [HTTP Status Codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) 