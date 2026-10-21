# 🌾 Farmer Helper — AI-Powered Smart Agriculture

Farmer Helper is an AI-powered agricultural platform that uses machine learning, deep learning, and cloud integration to assist farmers in making informed farming decisions. It provides crop recommendations, plant disease and weed detection, weather forecasts, market price insights, and an AI chatbot for agricultural assistance.

The platform aims to make farming smarter, more efficient, and less dependent on guesswork.

## 📌 Problem Statement

Farmers across India face challenges such as unpredictable weather, pest infestations, low crop yields, fluctuating market prices, and limited access to reliable agricultural information. Traditional farming decisions often depend on experience or local advice that may not account for changing environmental conditions.

Farmer Helper addresses these challenges by combining AI, data science, and real-time information to provide useful agricultural insights. It helps farmers make better-informed decisions, reduce avoidable losses, and improve farming efficiency.

## ✨ Key Features

- **Crop Recommendation:** Suggests suitable crops based on soil and environmental parameters.
- **Plant Disease Detection:** Uses deep learning to identify plant diseases from uploaded images.
- **Weed Detection:** Detects weeds using computer vision.
- **Weather Forecasting:** Provides weather information through OpenWeatherMap.
- **Market Price Insights:** Displays agricultural commodity price information.
- **AI Chatbot:** Supports agricultural queries in Marathi, Hindi, and English.
- **User Authentication:** Provides registration, login, and protected access.
- **Farmer Dashboard:** Offers a centralized interface for accessing agricultural tools.
- **Profile Management:** Allows users to manage their profile information.

## 🏗️ System Architecture

Farmer Helper follows a modular architecture that separates the frontend, backend, and machine learning services.

```text
                 FARMER HELPER
                       |
             React + Vite Frontend
                       |
                REST API Requests
                       |
              Node.js + Express
                 Backend API
                       |
          +------------+------------+
          |            |            |
       MongoDB      ML Services   External APIs
                     Python      Weather / Market
                       |
                Machine Learning
                     Models
                       |
              Crop / Disease /
                Weed Detection

              Dialogflow Chatbot
             Agricultural Assistant
```

### Technology Stack

| Component | Technologies |
|---|---|
| Frontend | React, Vite, Tailwind CSS |
| Backend | Node.js, Express.js |
| Database | MongoDB |
| Machine Learning | Python, scikit-learn |
| Deep Learning | PyTorch, YOLOv8 |
| API Communication | REST APIs |
| Authentication | JWT, bcrypt |
| Image Uploads | Multer |
| Weather Integration | OpenWeatherMap |
| Market Data | Agmarknet / Data.gov.in APIs |
| Chatbot | Dialogflow |
| Version Control | Git and GitHub |

## 📂 Project Structure

```text
Farmer-Helper-DevOps/
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── assets/
│   │   ├── Dashboard/
│   │   ├── LoginPage/
│   │   ├── landing_page/
│   │   ├── hooks/
│   │   ├── App.jsx
│   │   ├── backend.js
│   │   ├── RequireAuth.jsx
│   │   └── unique_values.json
│   └── package.json
│
├── backend/
│   ├── config/
│   ├── controllers/
│   ├── middlewares/
│   ├── models/
│   ├── routes/
│   ├── uploads/
│   └── server.js
│
├── ml_services/
│   ├── models/
│   ├── routes/
│   ├── services/
│   ├── uploads/
│   ├── app.py
│   └── requirements.txt
│
└── README.md
```

*Note: This is the documented logical structure. Actual folder names and files may differ in the cloned repository.*

## 🔄 Application Workflow

1. The farmer interacts with the React frontend.
2. The frontend sends requests to the Node.js backend.
3. The backend validates requests and communicates with the database, ML services, or external APIs.
4. Python-based ML services process agricultural data or uploaded images.
5. The relevant model generates a prediction or detection result.
6. The backend formats the response and returns it to the frontend.
7. The dashboard displays the result to the farmer.

## 🤖 Machine Learning Components

### Crop Recommendation

Uses soil and environmental parameters to predict a suitable crop.

### Plant Disease Detection

Uses an image-based deep learning model to identify potential plant diseases.

### Weed Detection

Uses a YOLO-based object detection model to identify weeds in images.

### AI Agricultural Assistant

Dialogflow provides natural-language interaction for agricultural questions, with backend integrations where configured.

## 🔌 External API Integrations

- **OpenWeatherMap:** Weather conditions and forecasts.
- **Agmarknet / Data.gov.in:** Agricultural commodity market information, depending on API availability and configuration.
- **Geolocation:** Supports location-specific agricultural information where implemented.

## 🔐 Security

The application is designed to use the following security mechanisms:

- JWT-based authentication.
- Password hashing using bcrypt.
- CORS configuration.
- File uploads managed through Multer.
- Environment variables for configuration and API credentials.

**Security note:** Keep database credentials, JWT secrets, API keys, and service-account files private. Never commit `.env` files or private credentials to GitHub.

## ⚙️ Installation and Setup

### Prerequisites

Install the following software before starting:

- Git
- Node.js and npm
- Python 3.11, if compatible with the project's dependencies
- MongoDB Atlas account or another configured MongoDB instance

### 1. Clone the Repository

```bash
git clone https://github.com/Pradnya1227/Farmer-Helper-DevOps.git
cd Farmer-Helper-DevOps
```

### 2. Configure the Backend

Navigate to the backend directory:

```bash
cd backend
npm install
```

Create a `.env` file inside `backend/`:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secure_jwt_secret
WEATHER_API_KEY=your_weather_api_key
ML_SERVICE_URL=http://localhost:5001
DATA_GOV_API_KEY=your_market_data_api_key
DATA_GOV_BASE_URL=your_market_data_api_base_url
```

Replace the placeholder values with your actual configuration.

Start the backend using the script defined in `backend/package.json`. If the project defines `server`, run:

```bash
npm run server
```

### 3. Configure the Frontend

Open a separate terminal:

```bash
cd frontend
npm install
```

Create a `.env` file inside `frontend/`:

```env
VITE_API_URL=http://localhost:5000
```

Start the development server:

```bash
npm run dev
```

Open the local URL printed by Vite, typically `http://localhost:5173`.

### 4. Configure the ML Services

Open a third terminal and navigate to `ml_services/`:

```bash
cd ml_services
python -m venv venv
```

Activate the virtual environment on Windows PowerShell:

```powershell
.\venv\Scripts\Activate.ps1
```

Install the Python dependencies:

```bash
pip install -r requirements.txt
```

Start the ML service:

```bash
python app.py
```

Ensure that the backend's `ML_SERVICE_URL` matches the actual address and port on which the Python service runs.

**Important:** Verify the actual filenames, npm scripts, Python dependencies, model files, and service ports in the repository before running the application. The commands above assume the documented structure is present.

## 🖥️ Running the Application

Run the three components in separate terminals:

| Terminal | Component | Purpose |
|---|---|---|
| 1 | Backend | Handles authentication, APIs, and integrations |
| 2 | Frontend | Runs the farmer dashboard |
| 3 | ML Services | Processes crop recommendations and image detection |

The application requires valid environment variables, a working database connection, and the relevant ML model files for the associated features to work.

## 🚀 Future Enhancements

- IoT-based soil monitoring.
- Predictive crop yield estimation.
- Drone-based crop monitoring.
- Offline access through a mobile application.
- Advanced multilingual agricultural assistance.
- Cloud-based deployment and automated CI/CD.
- Improved scalability and monitoring for ML services.

## 🌱 Conclusion

Farmer Helper combines modern web technologies, machine learning, and agricultural data to support smarter farming decisions. By bringing crop recommendations, disease detection, weather information, market insights, and conversational assistance into one platform, it aims to make useful agricultural technology more accessible to farmers.

---

**Repository:** [Pradnya1227/Farmer-Helper-DevOps](https://github.com/Pradnya1227/Farmer-Helper-DevOps)

*Farmer Helper — Empowering farmers through AI and technology.*
