# 🧪 Senior React Native Challenge (Expo - Minimal Dependencies)

* ⏱ **Estimated Time**: 2–4 hours
* 📦 **Stack**: Expo SDK (React Native), TypeScript
* 🎯 **Goal**: Evaluate your ability to build a clean, maintainable, and performant React Native app using **minimal external libraries**.

---

## 🧩 Project Overview

Build a **"MatchCenter Lite"** mobile app with:

1. **News Feed**: List and read sports news.
2. **Live Scores**: Show sports matches for the day.
3. **Favorites**: Mark any news or match as favorite.
4. **Theme Toggle**: Light/dark mode with persistence.

The app must be developed using **Expo** and focus on **core React Native APIs**, avoiding unnecessary dependencies.

---

## ✅ Functional Requirements

### 1. News Feed
- Display a list of sports news articles.
- Implement infinite scroll (`FlatList` + `onEndReached`).
- Pull-to-refresh using `RefreshControl`.
- Navigate to a **detail screen** showing:
  - Hero image
  - Headline
  - Body content (markdown or plain text)

### 2. Live Scores
- Display a list of **today’s matches** with:
  - Teams, status, kickoff time, live score
- Poll every 15 seconds to simulate live updates.

### 3. Favorites
- User can favorite/unfavorite both news and matches.
- Persist favorites using `AsyncStorage`.
- Display favorites in a separate screen.

### 4. Theme Toggle
- Light/dark mode using a toggle button.
- Persist the theme preference locally.

### 5. Accessibility & UX
- Add screen reader labels to buttons and list items.
- Display clear loading, error, and empty states.

---

## 🔧 Technical Constraints

| Area             | Allowed                        | Not Allowed                                  |
|------------------|--------------------------------|----------------------------------------------|
| **Remote state** | React Query (TanStack)         | Redux, Zustand, MobX, etc.                   |
| **Local state**  | `useState`, `useReducer`, Context | Any external state libraries                |
| **Styling**      | `StyleSheet`, inline styles    | Styled-Components, Tailwind, UI libraries    |
| **Networking**   | Native `fetch` or Axios        | GraphQL clients, SWR                         |
| **Testing**      | Jest, Testing Library          | Detox, Cypress, E2E                          |
| **Routing**      | `expo-router` or `react-navigation` | —                                        |

---

## 🔗 Suggested APIs

- **News**: `https://www.scorebat.com/video-api/v3/` *(no key required)*
- **Live Scores**: `https://www.thesportsdb.com/api/v1/json/3/eventsday.php?d=YYYY-MM-DD&s=Soccer`
- If API is unavailable, use local JSON mocks and `setTimeout` to simulate latency.

---

## 🧱 Project Structure (Suggested)

```
/src
  /features
    /news
      NewsList.tsx           # Screen: list of news
      NewsDetail.tsx         # Screen: news detail
      useNews.ts             # React Query hook for fetching news

    /scores
      ScoreList.tsx          # Screen: today's matches
      useScores.ts           # Hook for polling match data

    /favorites
      favorites.context.tsx  # Context for managing favorite items
      FavoritesScreen.tsx    # Screen: list of favorited news or matches

  /components
    Card.tsx                 # Generic UI card component
    Button.tsx               # Reusable button with consistent theming
    Header.tsx               # App header with theme toggle or back button

  /theme
    colors.ts                # Color palette (light/dark)
    ThemeProvider.tsx        # Context provider for managing theme
    useTheme.ts              # Hook to consume and toggle theme

  /hooks
    useStorage.ts            # Wrapper around AsyncStorage
    usePolling.ts            # Optional: abstract polling logic

  /services
    api.ts                   # Fetch wrapper or Axios instance
    endpoints.ts             # API endpoints (centralized config)

  /types
    news.ts                  # Type definitions for News API
    scores.ts                # Type definitions for Match data

  /tests
    NewsList.test.tsx        # Integration test example
    useNews.test.ts          # Unit test example

  App.tsx                    # Entry point
  router.tsx / app.config.ts # Routing or Expo config (if needed)
```

---

## 🧪 Testing Requirements

- At least **1 unit test** (e.g. for a custom hook like `useNews`)
- At least **1 integration test** (e.g. render list or card with mock data)

---

## 📊 Evaluation Criteria

| Area                          | Weight (%) |
|-------------------------------|------------|
| Project structure & modularity | 30%        |
| Code quality & reusability     | 20%        |
| State management (manual)      | 15%        |
| Performance optimizations      | 15%        |
| UX & accessibility             | 10%        |
| Testing coverage               | 10%        |

---

## 🚚 Delivery Instructions

1. Create a GitHub repo (public or invite us privately).
2. Include a **README** with:
   - Setup instructions: `npm i && expo start`
   - Test instructions: `npm run test`
   - Brief architecture/decision overview
3. Make atomic and descriptive commits.

---

## 💡 Time Management Tips

- Start with the **News Feed** (list + detail).
- Reuse components/layouts for **Live Scores**.
- Implement **favorites** with Context + AsyncStorage (fast).
- Leave theme toggle and tests for the final stretch if time allows.
- Prefer **simple but complete flows** over starting too many features.

---

### 🎯 We’re looking for a clean, modular, performant solution — as close as possible to real-world production code, using only essential tools.

Good luck!
