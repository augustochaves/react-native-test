# 🧪 Senior React Native Challenge

* 📦 **Stack**: Expo SDK (React Native), TypeScript
* ⏱ **Target Time**: 1 ½ – 2 ½ h
* 🎯 **Goal**: demonstrate senior-level mastery of core RN APIs, architecture and code quality

---

## 🗺️ What to Build

### 1. News Feed
- Infinite scroll (`FlatList` + `onEndReached`).
- Pull-to-refresh.
- **Detail screen** with hero image, headline & body.

### 2. Favorites
- Toggle ⭐ favorite on any article.
- Persist with `AsyncStorage`.
- Favorites screen (list only).

### 3. Accessibility & UX
- Screen-reader labels.
- Loading / error / empty states.

### ✨ Bonuses
- Live polling list of today’s matches *(optional – no penalty if skipped)*.

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
- If API is unavailable / quota hit, use local JSON mocks and `setTimeout` to simulate latency.

---

## 🧱 Project Structure (Suggested)

```
/src
  /features
    /news
      NewsList.tsx
      NewsDetail.tsx
      useNews.ts         # React-Query hook
    /favorites
      favorites.context.tsx
      FavoritesScreen.tsx
  /components
    Card.tsx
    Button.tsx
  /hooks
    useStorage.ts
  /services
    api.ts
  /tests
    NewsList.test.tsx
    useNews.test.ts
  ThemeProvider.tsx      # only if you do the bonus
  App.tsx
```

---

## 🧪 Testing Requirements

- At least **1 unit test** (e.g. for a custom hook like `useNews`)
- At least **1 integration test** (e.g. render list or card with mock data)

---

## 📝 **Senior-Level Add-On**

> In **≤ 200 words**, push an `ARCHITECTURE.md` explaining why you structured things the way you did (state boundaries, data flow, performance choices).

---

## 📊 Evaluation Criteria

| Area                              | % |
|-----------------------------------|---|
| Clean architecture & reasoning    | 35 |
| Code quality & TypeScript rigor   | 25 |
| Performance considerations        | 15 |
| Tests & DX                        | 15 |
| UX / Accessibility                | 10 |

---

## 🚚 Delivery Instructions

1. Create a GitHub repo (public or invite us privately).
2. Include a **README** with:
   - Setup instructions: `npm i && expo start`
   - Test instructions: `npm run test`
3. `ARCHITECTURE.md` as above.
4. Make atomic and descriptive commits.

---

### 🎯 Good luck – we’re interested in how you think, not how many screens you can ship!
