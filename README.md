# Pursuiter - AI Job Application Board

- [About Persuiter](#about-persuiter)
- [Installation](#installation)
- [Software Architecture](#software-architecture)
- [Contribution](#contribution)

## About Persuiter

Pursuiter is a revolutionary job board designed to enhance the job application process for both applicants and employers. By providing pre-application feedback, it ensures applicants are well-prepared, enhancing their chances for success. Additionally, by requiring applicants to meet minimum criteria set by employers, it guarantees that employers receive fewer, but more qualified applications.

## Installation

### Prerequisites

- Node.js (v22.2.0): [Download Node.js](https://nodejs.org/en/download/package-manager)
- MongoDB (v7.0.8): [Install MongoDB](https://www.mongodb.com/docs/manual/administration/install-community/)
- MongoDB Compass: [Download MongoDB Compass GUI](https://www.mongodb.com/try/download/atlascli)
- Add a `GEMINI_API_KEY` to the `.env` files : [Gemini API Key](https://ai.google.dev/gemini-api/docs/api-key)

### Run backend

Run `cd backend` to navigate to the backend directory.

1. Install dependencies

```
npm install
```

2. Setup database directory

```
mkdir data
cd data
mkdir db
cd ..
```

3. Start MongoDB server. Note: command is OS specific. If `mongod` is not available globally, use the path to the executable file.

```
mongod --dbpath=./data/db
```

4. Run the application

```
npm run dev
```

### Run frontend

Run `cd frontend` to navigate to the frontend directory.

1. Install dependencies

```
npm install
```

2. Run the application

```
npm start
```

## Screenshots

*Landing Page*

<img width="1728" alt="Screen Shot 2024-09-04 at 7 59 21 PM" src="https://github.com/user-attachments/assets/c08e1bdb-8565-4079-b7dc-c4a48fe04f9c">

*Login*

<img width="1728" alt="Screen Shot 2024-09-04 at 7 59 33 PM" src="https://github.com/user-attachments/assets/070c7a9c-e355-424d-9caf-722d2ce87ced">

*Applicant dashboard*

<img width="1720" alt="Screen Shot 2024-09-04 at 8 02 01 PM" src="https://github.com/user-attachments/assets/7c48bf33-c359-4f3b-9ca5-0e85f056887f">

*Recruiter Dashboard*

<img width="1728" alt="Screen Shot 2024-09-04 at 8 03 56 PM" src="https://github.com/user-attachments/assets/594ae780-affd-4cbb-9844-d778db9a94c1">

*Recruiter Applicant View*

<img width="1728" alt="Screen Shot 2024-09-04 at 8 04 53 PM" src="https://github.com/user-attachments/assets/415adc14-2915-41a9-9647-d529a92ac5a0">

## Software Architecture

This projecy leverages the Model-View-Controller (MVC) architecture to ensure easier management and scalability of the application. Each layer of the architecture plays a distinct role:

- **Model**: The model layer is managed by a backend server (`server.js`) which interacts with MongoDB. This setup handles all data logic, including data retrieval, storage, and processing.
- **View**: The view layer consists of React components, all stored within the `components` folder. Components do not contain business logic; they solely focus on presentation and user interaction.
- **Controller**: Controllers handle the logic necessary for processing user requests and ensuring the correct data flows back to the user interface. All controller components are stored within the `controller` folder.

## Contribution

### Workflow

- **Branching Strategy**: Our project uses a structured Git flow. All development should take place in feature branches, which should be created from the `dev` branch. Branch names must follow the format `ticketnumber`.
- **Pull Requests (PRs)**: After completing development on a feature branch, create a pull request to the `dev` branch. The PR title should clearly state the purpose of the changes, and the description should reference the relevant issue or ticket number.
- **Code Reviews**: At least one peer review is required for each pull request. Reviewers should ensure that the changes meet all project standards.
- **Merging**: No direct commits to the `main` branch are allowed. At the end of each development sprint, the `dev` branch is merged into `main`. Ensure that `dev` is stable before performing the merge.

### Coding Standards

- **Code Style**: Ensure that your code follows the existing formatting, naming conventions, and comment practices to maintain consistency across the codebase.
- **Component Structure**: All React components should be placed in the `components` folder. Each component should have its own folder named using kebab-case (e.g., `applicant-dashboard`). Inside this folder, both the JavaScript file and its corresponding CSS file should share the same name, using CamelCase (e.g., `ApplicantDashboard.js` and `ApplicantDashboard.css`).
- **Controller Organization**: Controllers should be stored in the `controllers` folder and named using CamelCase to reflect their functionality clearly (e.g., `UserController.js`).
