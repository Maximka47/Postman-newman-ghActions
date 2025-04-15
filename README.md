# 🚀 API Test Automation with Postman, Newman & GitHub Actions

This repository provides a setup for automating API testing using [Postman](https://www.postman.com/), [Newman](https://www.npmjs.com/package/newman), and GitHub Actions. It includes mock APIs and Postman collections for testing both local and public APIs.

---

## 📦 Features

- **Mock API**: A local mock API powered by `yaml-server` for testing.
- **Postman Collections**:
  - `store.collection.json`: Tests against the local mock API.
  - `petstore.collection.json`: Tests against the public Swagger Petstore API.
- **CI/CD Integration**: GitHub Actions pipeline to run tests automatically on every push.

---

## 🛠️ Requirements

Before you begin, ensure you have the following installed:

- [Node.js](https://nodejs.org/) (v16+ recommended)
- Git
- (Optional) Postman app for editing collections

---

## 🔧 Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/Maximka47/Postman-newman-ghActions
cd Postman-newman-ghActions
```

### 2. Install Dependencies

Run the following command to install the required dependencies from `package.json`:

```bash
npm install
```

### 3. Run the Local Mock API

To start the mock API server, use the following command:

```bash
npm run tern-on-api
```

This will:
- Copy the backup YAML database (`mockApi/db_back_up.yaml`) to the staging file (`mockApi/db_stage.yaml`).
- Start the `yaml-server` on port `3000` with the mock API data.

### 4. Run Postman Collections Locally (Optional)

You can use [Newman](https://www.npmjs.com/package/newman) to run the Postman collections locally. For example:

```bash
npx newman run store.collection.json
```

---

## 📂 Project Structure

- **`mockApi/`**: Contains mock API YAML files.
  - `db_back_up.yaml`: Backup database file.
  - `db_stage.yaml`: Staging database file used by the mock API.
- **`store.collection.json`**: Postman collection for testing the local mock API.
- **`petstore.collection.json`**: Postman collection for testing the public Swagger Petstore API.
- **`package.json`**: Contains project dependencies and scripts.

---

## 🤖 CI/CD Pipeline

This repository includes a GitHub Actions workflow to automatically run the Postman collections on every push. Ensure your repository is connected to GitHub to take advantage of this feature.

---