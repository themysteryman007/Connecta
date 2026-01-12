# Connecta
This backend API is developed using Node.js and Express.js, with MongoDB as the database. It enables contact management features such as creating contacts and intelligently merging them based on matching email addresses and phone numbers.
# Linkify
This backend API is developed using Node.js and Express.js, with MongoDB as the database. It enables contact management features such as creating contacts and intelligently merging them based on matching email addresses and phone numbers.
# Features
- Save and manage contact information using MongoDB.
- Automatically merge contacts when email addresses or phone numbers match.
- Fetch and view all stored contacts from the database.
# Tech Stack
- Node.js
- Express.js
- MongoDB with Mongoose ORM
- Render for application deployment
# Setup Instructions
- # Prerequisites
- Node.js installed (v14+ recommended)
- MongoDB Atlas or a local MongoDB instance
# Installation
1.Clone the repository
```bash
git clone https://github.com/themysteryman007/Connecta.git
cd connecta
```


2. Install dependencies
```bash
npm install
```

3. Create a `.env` file in the root directory and configure the environment variables:
```env
MONGO_URI=your_mongodb_connection_string
PORT=10000
```
4. Start the server:
   ```bash
   node index.js
   ```

   ## API Endpoints

### **1. Identify Contact (POST /identify)**
**Endpoint:**
```
POST /identify
```
**Description:**
- Accepts an email and/or phone number to create or merge contacts.

   **Request Body:**
```json
{
  "name": "Rohan Mehta",
  "email": "rohan.mehta@company.com",
  "phone": "+918888777666"
}
```

**Response:**
```json
{
  "_id": "65f01aa93c8d441234abcd90",
  "name": ["Rohan Mehta", "R. Mehta"],
  "emails": ["rohan.mehta@company.com"],
  "phoneNumbers": ["+918888777666", "+919900112233"],
  "secondaryContactIds": ["65f01a1b3c8d441234abcd12"],
  "updatedAt": "2025-07-01T09:10:00.000Z",
  "createdAt": "2025-06-20T12:00:00.000Z",
  "__v": 0
}
```
### **2. Get All Contacts (GET /identify)**
**Endpoint:**
```
GET /identify
```
**Description:**
- Retrieves all stored contacts from the database.
**Response:**
   ```json
  {
    "_id": "65f01aa93c8d441234abcd90",
    "name": ["Rohan Mehta", "R. Mehta"],
    "emails": ["rohan.mehta@company.com"],
    "phoneNumbers": ["+918888777666", "+919900112233"],
    "secondaryContactIds": ["65f01a1b3c8d441234abcd12"],
    "updatedAt": "2025-07-01T09:10:00.000Z",
    "createdAt": "2025-06-20T12:00:00.000Z",
    "__v": 0
  }
  ```
   ## Deployment
The API is deployed on **Render** and can be accessed at:
```
  https://connecta.onrender.com
```
## Testing the API
You can use **Postman** or **cURL** to test the endpoints.

### **Example cURL for POST request**
```bash
curl -X POST "https://linkify-api.onrender.com/identify" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Rohan Mehta",
    "email": "rohan.mehta@company.com",
    "phone": "+918888777666"
  }'
```

## License
This project is open-source
```

🚀 **Developed with ❤️ by Akshat Kumar Saini**



