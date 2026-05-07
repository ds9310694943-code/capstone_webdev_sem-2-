# 🏆 SportsPulse — Sports Analytics Dashboard

> A capstone React project for real-time sports data exploration, built with the full modern stack.

---

## 📌 Problem Definition

Sports fans and analysts lack a unified, fast, and visually rich platform to explore league data, team statistics, and match histories across multiple sports. **SportsPulse** solves this by aggregating real-time data from TheSportsDB public API into an intuitive React dashboard.

---

## 🧰 Tech Stack

| Layer | Technology |
|---|---|
| **Frontend** | React 18 (Vite) |
| **Language** | JavaScript ES6+ |
| **State Management** | Redux Toolkit |
| **Routing** | React Router v6 |
| **API Integration** | Axios + TheSportsDB API |
| **Styling** | Tailwind CSS |
| **Charts** | Recharts |
| **Deployment** | Vercel |

---

## 🚀 Features

### Core Features
- **Dashboard** — Overview stats, sports distribution pie chart, EPL match bar chart, featured leagues
- **Leagues Explorer** — Browse 500+ real-world leagues with filtering, sorting, and team grids
- **Team Profiles** — Detailed team cards with stadium info, manager, history, and goals line chart
- **Search** — Debounced real-time team search across all sports

### Advanced Features (Capstone Requirements ✅)
1. **Dashboard with Charts** — Bar charts (match scores), Line charts (team goals trend), Pie chart (sports distribution), horizontal progress bars (country distribution)
2. **Dark Mode Toggle** — Full CSS variable-based theming, persisted in localStorage, respects system preference on first load
3. **Search + Filter + Sort** — League filters by sport and country, sort A→Z / Z→A, team search filter by sport with 3 sort options
4. **Pagination** — Smart paginator on league teams (12 per page)
5. **Debounced API Calls** — 500ms debounce on the search input prevents excess network requests
6. **Error Boundary** — Class-based React error boundary wraps every page with user-friendly recovery UI
7. **Performance Optimization** — `useMemo` for derived data (filtered lists, chart data, sport/country options), `useCallback` for event handlers, lazy loading for all pages via `React.lazy` + `Suspense`, skeleton loaders for progressive UI
8. **Lazy Loading** — All 4 pages are code-split and loaded on demand

---

## 🗂 Project Structure

```
sportspulse/
├── src/
│   ├── components/
│   │   ├── ErrorBoundary.jsx   # Class-based error boundary
│   │   ├── Navbar.jsx          # Sidebar navigation + dark mode
│   │   ├── Pagination.jsx      # Smart paginator
│   │   └── Skeletons.jsx       # Loading skeleton variants
│   ├── hooks/
│   │   └── useDebounce.js      # Custom debounce hook
│   ├── pages/
│   │   ├── Dashboard.jsx       # Overview + charts
│   │   ├── Leagues.jsx         # League browser + filters
│   │   ├── Teams.jsx           # Team detail + match history
│   │   └── Search.jsx          # Debounced search
│   ├── store/
│   │   ├── store.js            # Redux store config
│   │   ├── sportsSlice.js      # Async thunks + reducers
│   │   └── themeSlice.js       # Dark mode reducer
│   ├── App.jsx                 # Router + lazy loading
│   ├── main.jsx                # Entry point + Provider
│   └── index.css               # Tailwind + CSS variables
├── index.html
├── vite.config.js
├── tailwind.config.js
└── vercel.json
```

---

## 🌐 API Used

**TheSportsDB** — Free public sports database  
Base URL: `https://www.thesportsdb.com/api/v1/json/3`

| Endpoint | Used For |
|---|---|
| `/all_leagues.php` | Fetch all leagues |
| `/lookup_all_teams.php?id={leagueId}` | Teams in a league |
| `/lookupteam.php?id={teamId}` | Team details |
| `/eventslast.php?id={teamId}` | Team's recent matches |
| `/eventspastleague.php?id={leagueId}` | League match history |
| `/searchteams.php?t={query}` | Search teams by name |

---

## 🛠 Setup & Running Locally

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/sportspulse.git
cd sportspulse

# Install dependencies
npm install

# Start dev server
npm run dev

# Build for production
npm run build
```

---

## 🚢 Deployment (Vercel)

1. Push code to a GitHub repository
2. Go to [vercel.com](https://vercel.com) → New Project → Import from GitHub
3. Select the `sportspulse` repo
4. Framework: **Vite** (auto-detected)
5. Click **Deploy**

The `vercel.json` handles SPA routing automatically.

---

## 🎨 Design Decisions

- **Bebas Neue** display font for bold sports-editorial look
- **CSS Variables** for seamless light/dark theming without re-renders
- **Orange accent (#f97316)** — energetic, sports-appropriate
- Sidebar navigation for quick access across all 4 pages
- Skeleton loaders instead of spinners for perceived performance

---

## 👨‍💻 Author

Capstone Project — React Frontend Development  
API: TheSportsDB (Free Tier, no API key required)
