# FlexiSched- AI-Powered Timetable Generator

An intelligent timetable scheduling system that uses advanced constraint satisfaction algorithms to generate optimized academic timetables with zero conflicts and balanced teacher workloads.

![Status](https://img.shields.io/badge/status-active-success.svg)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

## ✨ Features

- **🤖 Smart AI Scheduling**: Advanced constraint satisfaction algorithm for conflict-free timetables
- **👥 Teacher Workload Optimization**: Intelligent distribution of teaching hours
- **📊 Batch Generation**: Generate multiple timetable variations for comparison
- **🎯 Custom Preferences**: Set time preferences, teacher assignments, and subject priorities
- **📈 Analytics Dashboard**: Real-time insights into schedule efficiency and teacher utilization
- **🔄 Conflict Detection**: Automatic validation and conflict resolution
- **📤 Multiple Export Formats**: Download timetables in various formats
- **🎨 Beautiful UI**: Modern, responsive interface built with Next.js and Tailwind CSS

## 🏗️ Architecture

```
The-Pheonix/
├── Frontend/              # Next.js frontend application
│   ├── src/
│   │   ├── components/   # React components
│   │   ├── pages/        # Next.js pages
│   │   ├── lib/          # Utilities and helpers
│   │   └── styles/       # CSS styles
│   └── package.json
│
├── backend/              # FastAPI backend server
│   ├── main.py          # Main application entry
│   ├── scheduler.py     # Smart scheduling algorithm
│   ├── solver.py        # Legacy solver (fallback)
│   ├── database.py      # Database configuration
│   ├── routes/          # API routes
│   └── requirements.txt
│
└── docs/                # Documentation
```

## 🚀 Quick Start

### Prerequisites

- **Node.js** 20.x or higher
- **Python** 3.11 or higher
- **Supabase** account (for database)
- **pnpm** (recommended) or npm

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/The-Pheonix-main.git
cd The-Pheonix-main
```

### 2. Backend Setup

```bash
cd backend

# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Copy environment file
cp .env.example .env

# Edit .env with your Supabase credentials
# Then start the server
uvicorn main:app --reload --port 8000
```

The backend API will be available at `http://localhost:8000`

### 3. Frontend Setup

```bash
cd Frontend

# Install dependencies (using pnpm)
pnpm install
# or with npm
npm install

# Copy environment file
cp .env.example .env.local

# Edit .env.local with your Supabase credentials
# Then start the development server
pnpm dev
# or
npm run dev
```

The frontend will be available at `http://localhost:3000`

## 🔐 Environment Variables

### Backend (.env)

```env
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_service_role_key
DATABASE_URL=your_database_url
```

### Frontend (.env.local)

```env
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_anon_key
NEXT_PUBLIC_API_URL=http://localhost:8000
```

## 📚 Database Setup

The project uses Supabase (PostgreSQL) with the following tables:

- `Faculty_Clg` - Teacher/faculty information
- `Subjects_Clg` - Subject catalog
- `Classes_Clg` - Class/course information
- `Timetables_Clg` - Generated timetables

See `docs/DATABASE.md` for complete schema information.

## 🌐 Deployment

### Deploy Frontend (Vercel)

1. Push your code to GitHub
2. Connect your repository to [Vercel](https://vercel.com)
3. Add environment variables in Vercel dashboard
4. Deploy!

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new)

### Deploy Backend (Render/Railway)

#### Render
1. Create a new Web Service on [Render](https://render.com)
2. Connect your repository
3. Set build command: `pip install -r requirements.txt`
4. Set start command: `uvicorn main:app --host 0.0.0.0 --port $PORT`
5. Add environment variables
6. Deploy!

#### Railway
1. Create a new project on [Railway](https://railway.app)
2. Connect your repository
3. Add environment variables
4. Railway will auto-detect and deploy

### Docker Deployment

```bash
# Build and run with Docker Compose
docker-compose up --build

# Or build individually
docker build -t phoenix-backend ./backend
docker build -t phoenix-frontend ./Frontend

docker run -p 8000:8000 phoenix-backend
docker run -p 3000:3000 phoenix-frontend
```

## 📖 API Documentation

Once the backend is running, visit:
- Swagger UI: `http://localhost:8000/docs`
- ReDoc: `http://localhost:8000/redoc`

### Key Endpoints

- `POST /upload_faculty` - Upload faculty data
- `POST /upload_subjects` - Upload subjects
- `POST /upload_courses` - Upload courses/classes
- `POST /generate_timetable` - Generate smart timetable
- `POST /generator/custom` - Custom generation with preferences
- `POST /generator/batch` - Generate multiple variations
- `GET /get_timetable/{user_id}` - Retrieve timetable
- `GET /scheduler/analytics/{user_id}` - Get analytics

## 🧪 Testing

```bash
# Backend tests
cd backend
pytest

# Frontend tests
cd Frontend
pnpm test
```

## 🎯 Usage Guide

1. **Upload Data**: Navigate to Create page and upload your faculty, subjects, and classes
2. **Generate Timetable**: Go to Generate page and click "Smart Generate"
3. **Review**: Check the generated timetable for conflicts
4. **Export**: Download the timetable in your preferred format
5. **Analyze**: View teacher workload and schedule analytics

## 🛠️ Tech Stack

### Frontend
- **Framework**: Next.js 14 (Pages Router)
- **UI Library**: React 18
- **Styling**: Tailwind CSS
- **Components**: Radix UI, shadcn/ui
- **State Management**: React Context API
- **HTTP Client**: Axios
- **Forms**: React Hook Form + Yup

### Backend
- **Framework**: FastAPI
- **Database**: Supabase (PostgreSQL)
- **ORM**: Direct Supabase Client
- **Scheduling**: Custom Constraint Satisfaction Algorithm
- **Authentication**: Supabase Auth

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Authors

- **Your Name** - *Initial work*

## 🙏 Acknowledgments

- Constraint satisfaction algorithm inspired by academic scheduling research
- UI components from shadcn/ui
- Icons from Lucide React

## 📞 Support

For support, email sarvagyasharma660@example.com or open an issue on GitHub.

## 🗺️ Roadmap

- [ ] Mobile app (React Native)
- [ ] Room allocation optimization
- [ ] Multi-campus support
- [ ] Calendar integration (Google Calendar, Outlook)
- [ ] Email notifications
- [ ] Advanced analytics and reporting
- [ ] Export to PDF/Excel
- [ ] Teacher preference management

---

Made by The Phoenix Team
Sarvagya Sharma
Shivam Mudgal
Vraddhi Srivastava
Suhani Srivastava
