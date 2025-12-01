# Swiggy_API_Testing_Using_Postman
Below is a clean, professional **README.md** you can use for GitHub based on your Postman collection (CRUD API testing with automated Postman tests).
You can copy–paste directly into your repository.

---

# 🍽️ Food API – Postman Collection (CRUD Operations)

This repository contains a Postman collection for testing a **Food API** with complete CRUD operations:
`GET`, `POST`, `GET by ID`, `PUT`, `PATCH`, and `DELETE`.

The collection includes **automated Postman tests** to validate API responses, status codes, performance, and data extraction.

---

## 📌 Features

### ✔️ **GET – Get All Food**

Tests included:

* Status code is `200`
* Response received successfully
* Valid request
* Status code between `200–299`
* Response time validation
* Client success code (>199)
* Less than 400

### ✔️ **POST – Add Food**

Tests included:

* Status code is `201`
* Response received successfully
* Valid request
* Extract and save created `id` to **collection variable**:

  ```js
  pm.collectionVariables.set("Id", pm.response.json().id)
  ```

### ✔️ **GET by ID**

Uses saved `{{Id}}` to fetch created item.
Tests validate:

* Status code `200`
* Valid and successful response

### ✔️ **PUT / PATCH – Update Food**

Tests verify:

* Status code `200`
* Successful update
* Valid request

### ✔️ **DELETE – Remove Food**

Tests confirm:

* Status code `200` or `204`
* Food item deleted successfully

---

## 📂 Project Structure

```
📁 postman/
   ├── Food API Collection.json
   ├── environment.json (if applicable)
📄 README.md
```

---

## 🚀 How to Use

1. Download this repository or clone it:

   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   ```
2. Open **Postman**.
3. Go to **File → Import**.
4. Select the `.json` collection file from this repo.
5. Set up environment variables if required (`baseurl` etc.).
6. Run the collection or individual requests.

---

## 🧪 Testing Automation

Each endpoint includes Postman test scripts such as:

### Example (GET all food)

```js
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("getting response successfully ", function () {
    pm.response.to.have.status('OK');
});

pm.test("passed one valid request", function () {
    pm.expect(pm.response.code).to.be.oneOf([201, 200]);
});
```

### Example (POST request)

```js
pm.collectionVariables.set("Id", pm.response.json().id);

pm.test("getting response successfully", function () {
    pm.response.to.have.status(201);
});

pm.test("passed one valid request", function () {
    pm.expect(pm.response.code).to.be.oneOf([201, 200]);
});
```

---

## 🖼️ Screenshots

### ✔️ GET All Food – All Tests Passed

*(Add screenshot here)*

### ✔️ POST Food – Auto-Save ID

*(Add screenshot here)*

---

## 🤝 Contributing

Pull requests are welcome.
For major changes, please open an issue first.

---

## 📜 License

This project is licensed under the MIT License.

---

If you want, I can also generate:
✅ A **beautiful GitHub badge section**
✅ A **markdown table of all endpoints**
✅ A **workflow CI file** for automated API testing

Just tell me!
