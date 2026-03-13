EventVerse is a unified digital platform built to simplify event organization, collaboration, and participation using modern AI, backend automation, and real-time communication. 
It connects: 
  -Students / Participants – who discover and join events or committees. 
  -Committee Heads / Admins – who create and manage events, send updates, and approve member requests. 
  -AI Engine – that provides recommendations and intelligent insights to users. 
  
Technologies Used :
  -Frontend:	Angular 20, HTML, CSS, TypeScript 
  -Backend:	Node.js (ESM), Express-style routes 
  -Databases:	MongoDB (NoSQL), MySQL (RDBMS) 
  -AI / Recommendation	Node ML or Python AI API 
  -Media Storage:- Cloudinary 
  -Communication:- Socket.IO (WebSocket), HTTP 

 System Architecture Overview 
Frontend (Angular) 
  -Acts as the interactive user interface. 
  -Developed in Angular 20 for high performance and modularity. 
  =Handles routing, UI state, and component-based rendering. 
  -Connects to backend APIs through HTTP requests and WebSockets. 

Key UI Modules: 
🔹 Login/Signup Page 
🔹 Dashboard (Posts, Committees, Events) 
🔹 Notifications Panel 
🔹 Group Chat Interface 
🔹 Livestream Page (with media streaming support) 
🔹 Profile Management (including committee profile picture) 

Backend (Node.js with Express-style structure) 
The backend is the logic core of EventVerse — built using Node.js (Express Modules) and structured into multiple modules: Main File – main.js Central entry point of the backend. Creates HTTP + Socket.IO server. Connects to both MongoDB and MySQL databases. Routes incoming API calls to different modules. Enables real-time chat via WebSocket connections. 

Key Modules: 
  -post.js	Handles event & post creation, image uploads (via Cloudinary), and feed retrieval. 
  -chat.js	Manages real-time private/group chats using Socket.IO. 
  -livestream.js	Enables live event streaming (media extension integrated). 
  -recommendation.js	Implements AI logic for suggesting events, committees, and users. 
  -mongodb.js	Connects to the MongoDB cluster (eventverse). 
  -mysql.js	Connects to relational data (users, notifications, roles, etc.). 

Databases:
  -MongoDB (NoSQL): Used for unstructured data and media-heavy collections. 

Collections: 
  -posts → Stores user posts, event descriptions, media URLs. 
  -chats → Messages in private or group chats. 
  -livestreams → Active or past live event details. 
  -committeeProfiles → Committee profile images and metadata. 

MySQL (Relational): Used for structured data and relationships (foreign keys). 
Tables: 
  -Users → Login, authentication, role. 
  -Committees → Each committee’s info. 
  -Notifications → Event, join, and role-transfer notifications. 
  -Notification_Receivers → Tracks notification delivery and user actions. 
  -GroupChats → Group information for chat module. 

API Communication Flow 
  -Frontend Angular → Backend (Node.js) via HTTP requests 
    Example: GET /api/posts, POST /api/chat/send, GET /api/notifications. 
  -Backend → MongoDB / MySQL for fetching or storing data. 
  -Socket.IO (WebSocket) for real-time chat and notifications. 
  -Cloudinary API for storing media files securely online. 

AI Modules & Functions 
  -Event Recommendation: Analyzes user participation, posts viewed, and interactions. - Suggests relevant upcoming events. 
  -Committee Recommendation:	Matches students’: interests or past events with active committees. -Recommends suitable committees to join. 
  -Notification Prioritization: AI ranks which notifications are important for the user.	Smarter, - cleaner notification panel. 
  -Content Insights: Detects trending keywords or popular events in MongoDB posts. - Enables admins to make data-driven decisions. 
  -AI Stack Used: Python-based recommender API (or Node.js ML libraries) integrated through recommendation.js. 
