# Fullstack Notes App with AWS Amplify (GraphQL + Storage + Auth) 

Check out the web app here: [Webpage Link](https://main.dkfsfcuhup3em.amplifyapp.com/)

Architecture Diagram:
![image](https://github.com/user-attachments/assets/4f65211a-2749-4127-8372-75d33fec0f46)


This project is a full-stack note-taking app built with **React**, powered by **AWS Amplify Gen 2**, following the official AWS tutorial: [Build a React App with Amplify](https://aws.amazon.com/getting-started/hands-on/build-react-app-amplify-graphql/)

Users can sign up, create notes with titles and descriptions, upload and preview images stored in S3, and delete their notes — all securely authenticated using Amazon Cognito.

---

## Tech Stack

| Layer       | Tech                             |
|-------------|----------------------------------|
| Frontend    | React + Vite                     |
| UI          | AWS Amplify UI React Components |
| Auth        | Amazon Cognito                   |
| Data/API    | AWS AppSync + Amplify Data       |
| Storage     | Amazon S3                        |
| Backend     | AWS Amplify Gen 2                |
| Styling     | Vanilla CSS                      |

---

## Features

- **User Authentication** using Amplify’s `Authenticator`
- **Note Creation** with name, description, and optional image
- **List & Delete Notes**
- **Image Upload to S3**
- **Per-user file isolation using identityId**

---

## Key Files Overview

| File                | Purpose |
|---------------------|---------|
| `App.jsx`           | Main app logic: CRUD, file upload, and UI |
| `index.css`         | Custom styles and grid layout |
| `amplify/resource.ts` | Backend storage rules with `defineStorage()` |
| `amplify_outputs.json` | Auto-generated config for Amplify Gen 2 |

---

## Getting Started

### 1. Install dependencies

```bash
npm install
```

### 2. Start Amplify sandbox

```bash
npx ampx sandbox
```

> Keep this running — it deploys and connects your Amplify backend in real time.

### 3. Start development server

```bash
npm run dev
```

---

## Auth Flow

- Sign in/sign up handled via Amplify’s `Authenticator`
- User identity (`identityId`) is used to scope storage paths per user

---

## Image Storage

- Images are uploaded to:  
  `media/{identityId}/{imageName}`
- Fetched using signed S3 URLs via `getUrl()`

---

## Learnings

- Practiced Amplify Gen 2’s backend-as-code model with TypeScript
- Worked with GraphQL APIs using `generateClient`
- Used S3 for secure, identity-based media storage
- Integrated Amplify Auth, Data, and Storage in a React app

---

## Potential Enhancements

- Add edit/update functionality for notes
- Image preview before upload
- Group-based or public sharing of notes

---

## References

- [AWS Amplify Docs](https://docs.amplify.aws/)
- [Official Tutorial](https://aws.amazon.com/getting-started/hands-on/build-react-app-amplify-graphql/)
