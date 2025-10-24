# AI Virtual Assistant ✨: A Voice-Powered Full-Stack Application

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Cloudinary](https://img.shields.io/badge/Cloudinary-3448C5?style=for-the-badge&logo=cloudinary&logoColor=white)
![Google Gemini](https://img.shields.io/badge/Google_Gemini-8E77EE?style=for-the-badge&logo=google-gemini&logoColor=white)
## Executive Summary

AI Virtual Assistant is a sophisticated, full-stack application engineered to provide a hands-free, voice-controlled user experience. This project demonstrates a modern, robust architecture using the **MERN stack** (MongoDB, Express, React, Node.js). It features custom **JWT authentication**, real-time voice recognition via the **Web Speech API**, natural language processing powered by **Google's Gemini AI**, and integration with **Cloudinary** for media handling. The platform is designed to be customizable, secure, and intuitive, showcasing a comprehensive skill set in full-stack development and AI integration.

-----

## 📌 Live Demo

[🚀 Click here to view the deployed project](https://ai-virtual-assistant-yudu.onrender.com/)


-----

## ✨ Features & Technical Implementation

| Feature | ⚙️ Technical Implementation |
| :--- | :--- |
| 🔐 **Custom JWT Authentication** | Implements a secure, stateless authentication system using **JSON Web Tokens (JWT)**. The backend (`backend/controllers/auth.controllers.js`) handles user sign-up and login, hashing passwords with **bcrypt**, and issuing signed tokens. A custom middleware (`backend/middlewares/isAuth.js`) protects API routes by verifying the JWT on incoming requests. |
| 🗣️ **Voice Command & Recognition** | Leverages the browser's built-in **Web Speech API** for real-time speech-to-text conversion. The frontend (`frontend/src/pages/Home.jsx`) continuously listens for a wake word (`assistantName`) before processing commands, providing a hands-free user experience. |
| 🤖 **Natural Language Processing** | Integrates with **Google's Gemini AI** to understand and process user commands. The backend (`backend/gemini.js`) sends user input to the Gemini API and receives structured JSON responses, enabling the assistant to perform tasks like searching the web, answering questions, or opening applications. |
| 🎨 **Customizable Assistant** | Allows users to personalize their assistant by choosing a custom name and avatar. Image uploads are handled by **Multer** for processing and **Cloudinary** for cloud-based storage, with options to select from pre-defined images or upload a new one. The customization flow is managed across (`frontend/src/pages/Customize.jsx` and `frontend/src/pages/Customize2.jsx`). |
| 🖼️ **Cloud Image Storage** | Implements seamless image handling by integrating **Cloudinary** for cloud-based media storage. When a user uploads a custom avatar, the file is securely uploaded from the client to the server, which then streams it to the Cloudinary API. |
| 🖥️ **Modern, Responsive Frontend** | The UI is built with **React** and styled with **Tailwind CSS**, using **Vite** as the build tool. This combination allows for rapid development of a beautiful, responsive, and mobile-first interface. Global state is managed efficiently using **React Context** (`frontend/src/context/UserContext.jsx`). |
| 🧰 **Robust REST API** | The backend is a well-structured RESTful API built with **Node.js** and **Express**. It features a modular design with clear separation of concerns for routes (`backend/routes/`), controllers (`backend/controllers/`), and database models (`backend/models/`), ensuring maintainability and scalability. |

-----

## 🏗️ System Architecture

A high-level overview of the AI Virtual Assistant architecture.

```
ai-virtual-assistant/
├── 📁 backend/
│   ├── 📁 config/         # DB connection, Cloudinary, JWT
│   ├── 📁 controllers/   # Request handling logic (auth, user)
│   ├── 📁 middlewares/   # Auth verification, Multer
│   ├── 📁 models/       # MongoDB schemas (User)
│   ├── 📁 routes/       # API route definitions
│   ├── 📄 gemini.js      # Gemini AI integration logic
│   └── 📄 index.js       # Main server entry point
├── 📁 frontend/
│   ├── 📁 src/
│   │   ├── 📁 assets/       # Images, GIFs, and other static files
│   │   ├── 📁 components/   # Reusable React components
│   │   ├── 📁 context/      # React context for state management
│   │   ├── 📁 pages/        # Page components (Home, Login, Customize)
│   │   └── 📄 App.jsx       # Main application component
└── 📄 package.json          # Root project configuration
```

### Architectural Breakdown

  * **Client-Side (Frontend)** The frontend is a dynamic Single-Page Application (SPA) built with **React** and **Vite**.

      * **UI:** The interface is built with **React** and styled with **Tailwind CSS** for a modern, responsive design.
      * **State Management:** Global state, such as user data and assistant settings, is managed with **React Context** for a simple and effective solution.
      * **Voice Interaction:** The **Web Speech API** is used for listening to voice commands and providing spoken feedback to the user.
      * **API Communication:** The client communicates with the backend via a **REST API** using **Axios** for authentication and data management.

  * **Server-Side (Backend)** The backend is built with **Node.js** and **Express**, providing a REST API for core functionalities.

      * **REST API:** Exposes endpoints for user authentication (`/api/auth`) and assistant customization (`/api/user`).
      * **Database:** **MongoDB** is used as the data store, with **Mongoose** as the ODM for defining the `User` schema, which includes fields for the assistant's name, image, and command history.
      * **AI Integration:** The server acts as a proxy to the **Gemini AI**, formatting user commands and processing the AI's response before sending it back to the client.

  * **External Services**

      * **Gemini AI:** Powers the natural language understanding capabilities of the assistant.
      * **Cloudinary:** Manages the storage and delivery of user-uploaded assistant avatars.

-----

## 🚀 Getting Started

To get a local copy up and running, follow these simple steps.

### Prerequisites

Make sure you have the following installed on your machine:

  * Git
  * Node.js (v18.0.0 or later)
  * npm (Node Package Manager)
  * A running MongoDB instance (local or Atlas)

### Installation

1.  **Clone the repository:**

    ```sh
    git clone https://github.com/SKaran872/AI-Virtual-Assistant.git
    cd ai-virtual-assistant
    ```

2.  **Install backend dependencies:**

    ```sh
    cd backend
    npm install
    ```

3.  **Install frontend dependencies:**

    ```sh
    cd ../frontend
    npm install
    ```

### Set up environment variables

Create a `.env` file in the `/backend` directory. Refer to the example below for the required variables.

### Running the Project

1.  **Run the Backend Server:**

    ```sh
    cd backend
    npm run dev
    ```

2.  **Run the Frontend Development Server:**

    ```sh
    cd ../frontend
    npm run dev
    ```

Open `http://localhost:5173` in your browser to view the project.

-----

## 🔐 Environment Variables

To run this project locally, create a `.env` file in the `/backend` directory and add the following variables. You can obtain keys by creating free accounts on MongoDB Atlas, Cloudinary, and Google AI Studio.

```
# Server Configuration
PORT=5000
NODE_ENV=development

# MongoDB Connection
MONGODB_URL=your_mongodb_connection_string

# JWT Secret
JWT_SECRET=your_super_secret_jwt_key

# Gemini AI API
GEMINI_API_URL=your_gemini_api_url

# Cloudinary for Image Uploads
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
```

-----

## 📈 Future Improvements

  * **Expanded Command Set:** Integrate with third-party APIs (e.g., weather, calendar, news) to enable more complex and useful commands.
  * **Conversation Context:** Implement context-aware conversations, allowing the assistant to remember previous parts of the dialogue.
  * **Additional Voices & Languages:** Add options for different assistant voices and support for multiple languages.
  * **Web Socket Integration:** Transition from simple HTTP requests to Web Sockets for even faster, real-time communication between the client and server.

-----

## 🤝 Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you'd like to contribute, please follow these steps:

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'feat: Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

-----

## 📜 License

This project is licensed under the **MIT License**.
