# FileNest v2.0.0 - LAN Messaging & File Sharing App

A real-time messaging and file sharing web application designed for Local Area Network (LAN) communication. Built with Node.js, Express, and Socket.io for instant message delivery and live user status updates.

## 🚀 Features

- **Real-Time Messaging**: Instant message delivery using WebSocket (Socket.io)
- **Online Users List**: See who's currently connected to the LAN
- **File Sharing**: Share images, videos, audio, PDFs, and documents (up to 50MB)
- **Typing Indicators**: See when others are typing
- **Message Management**: Delete messages with confirmation
- **Persistent Storage**: Messages saved to local JSON database
- **Responsive Design**: Works on desktop and mobile devices
- **User Sessions**: Auto-save username for quick login

## 📦 Tech Stack

- **Backend**: Node.js + Express.js
- **Real-Time**: Socket.io for WebSocket communication (WebSocket + Polling)
- **File Upload**: Multer for handling local file uploads
- **Frontend**: Vanilla JavaScript (no frameworks)
- **Styling**: CSS3 with responsive design
- **Database**: JSON file-based storage
- **Storage**: Local file system (uploads/ folder)

## 💾 Local Storage

Files are stored locally on your computer in the `uploads/` folder. This version uses local storage instead of cloud services:

- **Messages**: Stored in `data/messages.json`
- **Files**: Stored in `uploads/` directory on your local machine
- **No cloud required**: All data stays on your LAN
- **Easy backup**: Simply copy the `data/` and `uploads/` folders to backup

## 🛠️ Installation

1. **Install Dependencies**:
   ```bash
   npm install
   ```

2. **Start Server**:
   ```bash
   npm start
   # or
   node server.js
   ```

3. **Access the App**:
   - Open browser and navigate to `http://localhost:3000`
   - Or access from other LAN devices: `http://<your-ip>:3000`

## 📋 Project Structure

```
project/
├── server.js              # Express + Socket.io server
├── package.json           # Dependencies and scripts
├── data/
│   └── messages.json     # Message storage
├── uploads/              # Uploaded files storage
└── public/
    ├── index.html        # Main UI
    ├── script.js         # Client-side logic
    └── style.css         # Styling
```

## 🎯 Key API Endpoints

- `GET /api/messages` - Fetch all messages
- `POST /api/messages` - Send new message (with optional file)
- `DELETE /api/messages/:id` - Delete a message
- `GET /api/users` - Get list of online users
- `GET /uploads/*` - Access uploaded files

## 🔌 WebSocket Events

### Client to Server
- `user_join` - User joins with their name
- `user_typing` - Notify others user is typing
- `typing_stopped` - Notify others user stopped typing

### Server to Client
- `message_sent` - New message received
- `message_deleted` - Message was deleted
- `users_updated` - Online users list updated
- `user_typing` - Someone is typing
- `typing_stopped` - Someone stopped typing

## 🎨 Features Breakdown

### Messaging
- Send text messages instantly to all connected users
- Auto-scroll to latest message
- Display sender name and timestamp
- Delete messages (with confirmation)

### File Sharing
- Upload images, videos, audio files, PDFs, and documents
- Files stored locally in the `uploads/` folder (no cloud service required)
- Preview images/videos inline
- Download uploaded files
- File size limit: 50MB
- Files accessible at `http://localhost:3000/uploads/filename`

### User Management
- See list of online users with status indicator
- Online count in sidebar
- Auto-save username in browser storage
- Quick user switching

### UI/UX
- Clean, modern interface
- Sidebar with quick actions
- Online users panel
- Real-time typing indicators
- Responsive layout for all devices

## 🔐 Security Features

- HTML/XSS protection via text content encoding
- File type validation on upload
- File size limits
- CORS enabled for LAN access
- Input sanitization

## 🚨 File Upload Limits

- Maximum file size: 50MB
- Supported types: Images, videos, audio, PDFs, documents, archives

## 📱 Browser Compatibility

- Chrome/Chromium (recommended)
- Firefox
- Safari
- Edge
- Mobile browsers (iOS Safari, Chrome Mobile)

## 🌐 LAN Access

To access from other devices on the same network:

1. Find your computer's IP address:
   - Windows: `ipconfig` (look for IPv4 Address)
   - Mac/Linux: `ifconfig` (look for inet)

2. On another device, open: `http://<your-ip>:3000`

Example: `http://192.168.1.100:3000`

## 📝 Configuration

Server runs on port `3000` by default. Messages and files are stored locally in the `data/` and `uploads/` directories.

## 🔄 Data Persistence

- Messages: Stored in `data/messages.json`
- Files: Stored in `uploads/` directory
- User data: Stored in browser's localStorage

## ⚡ Performance

- Real-time message delivery (< 100ms)
- Efficient WebSocket communication
- Optimized for LAN speeds
- Automatic reconnection on disconnect

## 📖 Usage Tips

1. Enter your name to start chatting
2. Messages appear in real-time for all connected users
3. Attach files by clicking the paperclip icon
4. View who's online in the right sidebar
5. See typing indicators when others compose messages

## 🛠️ Development

To modify the app:
- Frontend: Edit `public/script.js`, `public/index.html`, `public/style.css`
- Backend: Edit `server.js`
- Styles: Update CSS variables in `public/style.css` `:root` section

---

**FileNest** - Making LAN communication simple and efficient! 📁💬
# FileNest-Message
