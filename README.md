<p align="center">
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" height="25">
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" height="25">
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" height="25">
  <img src="https://img.shields.io/badge/WebRTC-333333?style=for-the-badge&logo=webrtc&logoColor=white" height="25">
  <img src="https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white" height="25">
  <img src="https://img.shields.io/badge/Flowise-4A90E2?style=for-the-badge&logo=flowise&logoColor=white" height="25">
</p>

# REX-RT: Real-time Chat with OpenAI's WebRTC API

A modern single-page vanilla JavaScript/HTML application featuring real-time voice communication powered by OpenAI's Real-time API using WebRTC. This application provides seamless voice interaction, text chat, and data visualization capabilities, all implemented in pure JavaScript without any frameworks.

> 🤖 **AI-Assisted Development**: This application was built with Cursor AI. Changes and customizations described in this guide can be easily implemented by sharing these instructions with Cursor AI or your preferred AI coding assistant. For guidance on using Cursor AI effectively, check out the Volo Builds tutorials in the video guides section below.

📚 **Official Documentation & Guides**:
- [OpenAI Real-time Model Capabilities](https://platform.openai.com/docs/guides/realtime-model-capabilities)
- [OpenAI Real-time WebRTC Guide](https://platform.openai.com/docs/guides/realtime-webrtc)
- [OpenAI Realtime Console](https://github.com/openai/openai-realtime-console) - Essential reference implementation showing WebRTC integration, event handling, and component interactions. This codebase provides valuable insights into real-time communication patterns and event logging that you can adapt for your application.

---

## Key Features

🎙️ **Real-time Voice Communication**: Powered by OpenAI's Real-time API using WebRTC for natural conversations.  
🤖 **AI Assistant Integration**: Advanced language models through OpenAI's Real-time API.  
⚡ **Flowise AI Integration**: Connected to Flowise AI for enhanced agent capabilities.  
🔄 **FastAPI Backend**: Robust API server for handling backend operations.  
📊 **Data Visualization**: Charts generated dynamically based on LLM agent queries to the backend database.  
📱 **Responsive Design**: Mobile-friendly interface with tab-based navigation.  
🎛️ **Voice Activity Detection**: Configurable VAD settings for optimal voice interaction.  
🔗 **Database Integration**: Connected to database systems for data persistence and retrieval.  

---

## Video Guides

🎥 **Video walkthroughs for setup and usage**:  

1. **Volo Builds**: Comprehensive guides for Cursor AI and full-stack app development  
   [https://www.youtube.com/@VoloBuilds](https://www.youtube.com/@VoloBuilds)

2. **Leon Van Zyl**: For anything Flowise AI, Leon's videos are the best. Also for ElevenLabs voice widget setup as well as ElevenLabs custom build with its SDK  
   [https://www.youtube.com/@leonvanzyl](https://www.youtube.com/@leonvanzyl)

3. **REX Series Guides**:
   - **REX-V**: AI Analytics Assistant V2. Execute tasks, automate reports, analyze data with voice and text instructions. Detailed 5 Part series of nearly 120 minutes of video guide.
     [https://link.tigzig.com/anly5pt](https://link.tigzig.com/anly5pt)
   
   - **REX-A**: Build AI apps to connect to any database, create new databases on the fly, and upload text files. With nearly 180 minutes of video guides.
     [https://link.tigzig.com/rex2HowTo](https://link.tigzig.com/rex2HowTo)
   
   - **REX-D**: Data Analytics Assistant System
     [https://link.tigzig.com/dataLLM](https://link.tigzig.com/dataLLM)

---

## Step-by-Step Deployment Process

### Step 1: 🚀 Initial Setup

1. Clone the repository:
   ```bash
   git clone [your-repo-url]
   cd [repo-name]
   ```

2. Deploy the application:
   - Use platforms like **Vercel**, **Netlify**, or any static hosting service
   - Point the deployment to the `public` directory
   - Ensure HTTPS is enabled (required for WebRTC)

---

### Step 2: 🛠️ LLM Agent Setup

The `docs` folder contains all necessary JSON schemas for Flowise AI chatflows and tools configuration. For detailed setup instructions:
- Follow the REX-A and REX-D video guides for database integration and analytics setup
- Check Leon Van Zyl's tutorials for Flowise AI configuration
- Import the provided JSON schemas from the `docs` folder into your Flowise AI instance

Update the Flowise AI configurations in `index.html`:
```javascript
const chatflowId = 'your-chatflow-id';  // Replace with your Flowise AI chatflow ID
const baseUrl = 'your-flowise-url';     // Replace with your Flowise AI API endpoint
```

Note: Search for "flowise", "baseUrl", or "chatflowId" in the code and JSON schemas to locate all places requiring updates.

---

### Step 3: 🖥️ FastAPI Backend Setup

1. Deploy the FastAPI servers:

   a. Ephemeral Key Server:
   - Repository: [FastAPI Ephemeral Key Server](https://github.com/amararun/shared-openai-realtime-fastapi-ephemeral)
   - Clone and install dependencies:
     ```bash
     git clone https://github.com/amararun/shared-openai-realtime-fastapi-ephemeral
     cd shared-openai-realtime-fastapi-ephemeral
     pip install -r requirements.txt
     ```

   b. Cricket Data Server:
   - Repository: [Cricket FastAPI Server](https://github.com/amararun/shared-rexc-cricket-fastapi)
   - Deploy on Render, Railway, or AWS Lambda
   - Follow the deployment instructions in the repo

2. Update the API endpoints in your application configuration.

---

### Step 4: 🗄️ Database Setup and Data Loading

1. **Set Up Database**:
   - Use any PostgreSQL database (example uses Aiven)
   - Follow the REX-A video guide for Aiven setup
   - Configure database credentials in FastAPI server environment variables

2. **Load Initial Data**:
   - Download `odi.txt` from [Google Drive](https://drive.google.com/drive/folders/1VHD9UzeYaJF_dBPecnjucHpoGocf4IvR)
   - Upload using one of these methods:
     - rex.tigzig.com (using your database credentials)
     - Python/JavaScript scripts
     - DBeaver or similar tools

3. **Update Data (Optional)**:
   - Current data is as of 6th Dec 2024
   - For newer data:
     1. Download latest ZIP from [Cricsheet.org](https://cricsheet.org/downloads/#experimental)
     2. Process the ZIP file:
        - Use [Cricket Data Processor](https://github.com/amararun/shared-cricket-data-flask)
        - Or visit rex.tigzig.com -> Automation for AI Apps -> Cricsheet.org CSV-ZIP File Processor

---

### Step 5: 🔐 Security Configuration

Adding security to your app is **critical**, especially for API endpoints. Here are a few approaches:
- **API Keys**
- **IP Whitelisting**
- **Authentication**
- **Backend-Frontend Segregation** (requires a separate build)

For this app, I implemented **IP-Domain Whitelisting** for my domain `tigzig.com`:

#### Implementations:
- **Flowise AI Agent**:  
  `Configuration -> Allowed Domain -> Add your domain.`  

- **FastAPI Servers**:  
  Added the domain to the **CORS middleware configuration**.  
  *(Details available in the repo)*  

⚡ **Tip**: Do this **last**, once everything else is up and running. Debugging becomes easier.

---

### Step 6: 🎙️ Voice Settings Configuration

The application includes configurable Voice Activity Detection (VAD) settings:

- **Threshold**: Sensitivity of voice detection (0.0 - 1.0)
- **Prefix Padding**: Buffer time before voice activity (ms)
- **Silence Duration**: Time before considering speech ended (ms)

Access these settings through the settings button in the UI.

---

## Usage Guide

### Voice Interaction
1. Click the "Connect" button to start a session
2. Allow microphone access when prompted
3. Speak naturally - the VAD system will detect voice activity
4. Adjust VAD settings if needed through the settings panel

### Text Chat
1. Use the text input field for typing messages
2. Press Enter or click Send to submit
3. Switch between voice and text modes as needed

### Charts and Documents
1. Use the tab navigation to switch between chat, charts, and documents
2. Charts are automatically generated based on your requests to the LLM agent, which queries the backend database
3. Documents can be viewed and edited through the integrated viewer

---

## Troubleshooting

Common issues and solutions:

1. **Connection Issues**
   - Ensure HTTPS is enabled
   - Check browser microphone permissions
   - Verify WebRTC compatibility

2. **Voice Detection Problems**
   - Adjust VAD settings in the configuration panel
   - Check microphone input levels
   - Ensure proper audio device selection

3. **Backend Connection Errors**
   - Verify API endpoints are correct
   - Check network connectivity
   - Confirm server status

---

## License

MIT License - Feel free to use and modify as needed.

---
