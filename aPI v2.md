
### Authentication
- `POST /auth/telegram`
  - Authenticate user via Telegram
  - Parameters: `{ id: string, first_name: string, username: string }`
  - Returns: `{ token: string, user: { id: string, username: string } }`

### User Actions
- `POST /api/users/tap`
  - Register a GPU tap
  - Returns: `{ compute: number, totalTaps: number, computePower: number }`

- `POST /api/users/upgrade-gpu`
  - Upgrade user's GPU
  - Returns: `{ message: string, user: object }`

- `POST /api/users/check-in`
  - Perform daily check-in
  - Returns: `{ xp: number, checkInStreak: number }`

### Quests and Achievements
- `GET /api/quests`
  - Retrieve  quests
  - Returns: `[{ id: string, name: string, description: string, xpReward: number, completed: boolean }]`

- `POST /api/quests/claim/:questId`
  - Claim completed quest
  - Returns: `{ message: string, xp: number }`

- `GET /api/achievements`
  - Retrieve user achievements
  - Returns: `[{ id: string, name: string, description: string, completed: boolean, progress: number }]`

### Leaderboard
- `GET /api/leaderboard/:type`
  - Get leaderboard (types: daily, weekly, all-time)
  - Returns: `[{ username: string, computePower: number, compute: number }]`

- `GET /api/leaderboard/position/:type`
  - Get user's position on leaderboard
  - Returns: `{ position: number, totalUsers: number }`

### Referrals
- `POST /api/referral/generate-code`
  - Generate referral code
  - Returns: `{ referralCode: string }`

- `POST /api/referral/apply-code`
  - Apply referral code
  - Parameters: `{ referralCode: string }`
  - Returns: `{ message: string, xpEarned: number }`

### Settings
- `GET /api/settings`
  - Get user settings
  - Returns: `{ notifications: boolean, language: string, theme: string }`

- `PUT /api/settings`
  - Update user settings
  - Parameters: `{ notifications?: boolean, language?: string, theme?: string }`
  - Returns: `{ message: string, settings: object }`

