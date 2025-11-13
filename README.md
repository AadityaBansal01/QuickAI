# QuickAI

An AI-powered platform that provides multiple creative tools including image generation, background removal, object removal, article writing, resume review, and blog title generation. Built with React and powered by various AI APIs.




## ✨ Features

- **🖼️ AI Image Generation**: Create stunning images from text prompts
- **🎨 Background Removal**: Remove backgrounds from images with AI precision
- **✂️ Object Removal**: Intelligently remove unwanted objects from photos
- **✍️ Article Writing**: Generate well-structured articles with AI assistance
- **📝 Blog Title Generator**: Create catchy blog titles instantly
- **📄 Resume Review**: Get AI-powered feedback on your resume
- **👥 Community Showcase**: Share and explore AI-generated creations
- **🔐 User Authentication**: Secure login with Clerk
- **💾 Cloud Storage**: Store and manage creations with Cloudinary

## 🛠️ Tech Stack

### Frontend
- **React** with Vite
- **CSS** for styling
- **Clerk** for authentication
- **Axios** for API calls

### Backend
- **Node.js** with Express
- **Neon Database** (PostgreSQL)
- **Cloudinary** for media management
- **Multer** for file uploads

### AI Services
- **OpenAI API** for text generation
- **Gemini API** for content creation
- **Clipdrop API** for image manipulation

## 📋 Prerequisites

Before you begin, ensure you have:
- **Node.js** (v14.0 or higher) - [Download here](https://nodejs.org/en/download/)
- npm or yarn package manager
- Git

## 🚀 Installation & Setup

> **Important**: Run the server first, then the client

### Server Setup

1. **Clone the repository**
```bash
git clone https://github.com/AadityaBansal01/QuickAI.git
cd QuickAI
```

2. **Setup Neon Database**
   - Visit [Neon.tech](https://neon.com)
   - Create a new project and database
   - Run this SQL query in the SQL Editor:

```sql
CREATE TABLE creations (
    id SERIAL PRIMARY KEY,
    user_id TEXT NOT NULL,
    prompt TEXT NOT NULL,
    content TEXT NOT NULL,
    type TEXT NOT NULL,
    publish BOOLEAN DEFAULT FALSE,
    likes TEXT[] DEFAULT '{}',
    created_at TIMESTAMPTZ DEFAULT NOW(),
    updated_at TIMESTAMPTZ DEFAULT NOW()
);
```

3. **Setup Cloudinary**
   - Sign up at [Cloudinary](https://cloudinary.com/users/register_free)
   - Get your Cloud Name, API Key, and API Secret

4. **Setup Clerk Authentication**
   - Create account at [Clerk](https://clerk.com/)
   - Create a new application
   - Get your Publishable Key and Secret Key

5. **Setup Clipdrop API**
   - Visit [Clipdrop APIs](https://clipdrop.co/apis)
   - Get your API key

6. **Setup Gemini API**
   - Go to [AI Studio](https://aistudio.google.com/apikey)
   - Generate your API key

7. **Install server dependencies**
```bash
npm install
```

8. **Configure environment variables**
   - Create a `.env` file in the server root
   - Add your API keys and credentials:

```env
# Neon Database
DATABASE_URL=your_neon_database_url

# Cloudinary
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

# Clerk
CLERK_SECRET_KEY=your_clerk_secret_key

# OpenAI
OPENAI_API_KEY=your_openai_api_key

# Gemini
GEMINI_API_KEY=your_gemini_api_key

# Clipdrop
CLIPDROP_API_KEY=your_clipdrop_api_key
```

9. **Run the server**
```bash
npm run server
```

The server should now be running on `http://localhost:5000` (or your configured port)

### Client Setup

1. **Open client folder in a new terminal**
```bash
cd client
```

2. **Install client dependencies**
```bash
npm install
```

3. **Configure client environment variables**
   - Create a `.env` file in the client root
   - Add your Clerk Publishable Key:

```env
VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
```

4. **Run the client**
```bash
npm run dev
```

5. **Open your browser**
   - Navigate to `http://localhost:5173` (or the URL shown in terminal)

## 📁 Project Structure

### Server Structure
```
server/
├── configs/          # Configuration files
├── controllers/      # Request handlers
├── middlewares/      # Custom middleware
├── routes/           # API routes
├── node_modules/     # Dependencies
└── .env              # Environment variables
```

### Client Structure
```
client/
├── public/           # Static assets
│   ├── favicon.svg
│   └── gradientBackground.png
├── src/
│   ├── assets/       # Images and icons
│   ├── components/   # React components
│   │   ├── Navbar.jsx
│   │   ├── Hero.jsx
│   │   ├── AiTools.jsx
│   │   ├── Sidebar.jsx
│   │   ├── Footer.jsx
│   │   └── ...
│   ├── pages/        # Application pages
│   │   ├── Home.jsx
│   │   ├── Dashboard.jsx
│   │   ├── GenerateImages.jsx
│   │   ├── RemoveBackground.jsx
│   │   ├── RemoveObject.jsx
│   │   ├── WriteArticle.jsx
│   │   ├── BlogTitles.jsx
│   │   ├── ReviewResume.jsx
│   │   └── Community.jsx
│   ├── App.jsx       # Main app component
│   └── main.jsx      # Entry point
└── package.json
```

## 🎯 Usage

1. **Sign Up/Login**: Use Clerk authentication to create an account
2. **Choose a Tool**: Select from various AI tools on the dashboard
3. **Generate Content**: Enter your prompts or upload files
4. **Save & Share**: Save your creations and share them with the community
5. **Explore Community**: Browse creations from other users

## 🌐 Deployment

The project includes a `vercel.json` configuration file for easy deployment on Vercel or other hosting platforms.

## 📦 Key Dependencies

### Server
- `express` - Web framework
- `@clerk/express` - Authentication middleware
- `@neondatabase/serverless` - Database client
- `cloudinary` - Media management
- `openai` - OpenAI API client
- `multer` - File upload handling
- `cors` - CORS middleware
- `dotenv` - Environment variables

### Client
- `react` - UI library
- `react-router-dom` - Routing
- `@clerk/clerk-react` - Authentication
- `axios` - HTTP client
- `swr` - Data fetching
- `vite` - Build tool

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is open source and available under the MIT License.

## 👤 Author

**Aaditya Bansal**

- GitHub: [@AadityaBansal01](https://github.com/AadityaBansal01)

## 🙏 Acknowledgments

- Special thanks to GreatStack for guidance and tutorials
- OpenAI for GPT models
- Google for Gemini API
- Clipdrop for image processing APIs
- Clerk for authentication services
- Cloudinary for media management
- Neon for serverless PostgreSQL

## 📞 Support

If you encounter any issues or have questions:
- Open an issue on GitHub

## ⚠️ Important Notes

- Always run the server before starting the client
- Keep your API keys secure and never commit them to version control
- Make sure all environment variables are properly configured
- Database tables must be created before running the application

---

**Made with ❤️ by Aaditya Bansal**