# FullStack Video Hosting Platform - Backend Development

A complete backend implementation for a **YouTube-like** video hosting platform. This project is designed with scalability and security in mind, offering essential features like user authentication, video management, comments, likes, subscriptions, and more. Built with **Node.js, Express.js, MongoDB, and Mongoose**, it follows **industry best practices** to ensure robustness and performance.

---

## Features

✅ **User Authentication**  
- Secure **JWT-based authentication** with **access & refresh tokens**  
- Password encryption using **bcrypt**  

✅ **Video Management**  
- Video **upload, update, delete** functionalities  
 
✅ **User Interactions**  
- **Like & Dislike** system for videos and comments  
- **Commenting system** with **threaded replies**  
- **Subscribe & Unsubscribe** to channels  
- **Playlists & video organization**  

✅ **Scalable & Secure**  
- Built with **Node.js, Express.js, MongoDB, and Mongoose**  
- Well-structured database design  

---

## 🛠️ Tech Stack

🔹 **Backend**: Node.js, Express.js  
🔹 **Database**: MongoDB, Mongoose  
🔹 **Authentication**: JWT, bcrypt  
🔹 **Middleware**: Express Middleware for authentication and validation  
🔹 **Storage**: Cloudinary for media storage  

---

## Installation & Setup

1️⃣ **Clone the repository**
```sh
git clone https://github.com/prks61/FullStack-Video-Hosting-Backend-Development.git
cd FullStack-Video-Hosting-Backend-Development
```

2️⃣ **Install dependencies**
```sh
npm install
```

3️⃣ **Setup environment variables**
Create a `.env` file in the root directory and configure:
```plaintext
PORT=8000
MONGODB_URL=your_mongodb_url
ACCESS_TOKEN_SECRET=your_access_token_secret
REFRESH_TOKEN_SECRET=your_refresh_token_secret
ACCESS_TOKEN_EXPIRY=1h
REFRESH_TOKEN_EXPIRY=7d
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
CORS_ORIGIN=your_cors_origin
```

4️⃣ **Start the development server**
```sh
npm run dev
```
Your backend will be running on `http://localhost:8000`

---

## API Endpoints

### User Routes
- `POST /api/v1/users/register` - Register a new user
- `POST /api/v1/users/login` - Login a user
- `POST /api/v1/users/logout` - Logout a user
- `POST /api/v1/users/refresh-token` - Refresh access token
- `POST /api/v1/users/change-password` - Change user password
- `GET /api/v1/users/current-user` - Get current user details
- `PATCH /api/v1/users/update-account` - Update account details
- `PATCH /api/v1/users/avatar` - Update user avatar
- `PATCH /api/v1/users/cover-image` - Update user cover image
- `GET /api/v1/users/c/:username` - Get user channel profile
- `GET /api/v1/users/history` - Get user watch history

### Video Routes
- `GET /api/v1/videos` - Get all videos
- `POST /api/v1/videos` - Publish a new video
- `GET /api/v1/videos/:videoId` - Get video by ID
- `PATCH /api/v1/videos/:videoId` - Update video details
- `DELETE /api/v1/videos/:videoId` - Delete a video
- `PATCH /api/v1/videos/toggle/publish/:videoId` - Toggle video publish status

### Comment Routes
- `GET /api/v1/comments/:videoId` - Get comments for a video
- `POST /api/v1/comments/:videoId` - Add a comment to a video
- `PATCH /api/v1/comments/c/:commentId` - Update a comment
- `DELETE /api/v1/comments/c/:commentId` - Delete a comment

### Like Routes
- `POST /api/v1/likes/toggle/v/:videoId` - Toggle like on a video
- `POST /api/v1/likes/toggle/c/:commentId` - Toggle like on a comment
- `GET /api/v1/likes/videos` - Get liked videos

### Playlist Routes
- `POST /api/v1/playlists` - Create a new playlist
- `GET /api/v1/playlists/:playlistId` - Get playlist by ID
- `PATCH /api/v1/playlists/:playlistId` - Update playlist details
- `DELETE /api/v1/playlists/:playlistId` - Delete a playlist
- `PATCH /api/v1/playlists/add/:videoId/:playlistId` - Add video to playlist
- `PATCH /api/v1/playlists/remove/:videoId/:playlistId` - Remove video from playlist
- `GET /api/v1/playlists/user/:userId` - Get user playlists

### Subscription Routes
- `POST /api/v1/subscriptions/c/:channelId` - Toggle subscription
- `GET /api/v1/subscriptions/c/:channelId` - Get subscribed channels
- `GET /api/v1/subscriptions/u/:subscriberId` - Get user channel subscribers

### Tweet Routes
- `POST /api/v1/tweets` - Create a new tweet
- `GET /api/v1/tweets/user/:userId` - Get user tweets
- `PATCH /api/v1/tweets/:tweetId` - Update a tweet
- `DELETE /api/v1/tweets/:tweetId` - Delete a tweet

### Healthcheck Route
- `GET /api/v1/healthcheck` - Healthcheck endpoint

---

## Folder Structure
```
.env
.gitignore
.prettierrc
package.json
public/
  temp/
    .gitkeep
README.md
src/
  app.js
  controllers/
    user.controller.js
    video.controller.js
    comment.controller.js
    like.controller.js
    playlist.controller.js
    subscription.controller.js
    tweet.controller.js
    healthcheck.controller.js
  db/index.js
  middlewares/
    auth.middleware.js
    multer.middleware.js
  models/
    user.model.js
    video.model.js
    comment.model.js
    like.model.js
    playlist.model.js
    subscription.model.js
    tweet.model.js
  routes/
    user.routes.js
    video.routes.js
    comment.routes.js
    like.routes.js
    playlist.routes.js
    subscription.routes.js
    tweet.routes.js
  utils/
    ApiError.js
    ApiResponse.js
    asyncHandler.js
    cloudinary.js
```

---
