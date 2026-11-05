# OddJobs

OddJobs is an **open-source, campus-gated, student-to-student task exchange.** A *community-driven mobile app*, it allows peers to hire for short-term gigs, offer their skills, and coordinate everyday help efficiently. 

Needs for UCSD students arise suddenly; whether acquiring moving help, hiring photographers, or getting haircuts, students must often navigate a plethora of platforms without verification and trust. OddJobs organizes this into a unified mobile app **prioritizing coordination, speed, and mutual trust.**

## Open Source Contribution
This is an **open source** project! To make a contribution, read [CONTRIBUTING.md](CONTRIBUTING.md) for details on installation, development setup, and how to submit pull requests (PRs).

## Features

- Post & Browse Offerings
- Request Skills and Help
- Find jobs through descriptions with Semantic Search
- In-app chat to discuss timing, payment, and other details
- Two-way rating and feedback to establish credibility and report poor experiences
- UCSD SSO through Google Sign-In to maintain a trusted community

## Tech Stack
- **React Native + Expo** *(TS/TSX + CSS)*
- **Supabase PostgreSQL Database** *(SQL)*
    - pgvector for semantic searching on data
    - Built-in Google OAuth
    - WebSocket for chat connections

## Dependencies Included

- `npx create-expo-app@latest mobile` to create a React Native Expo app.  
- `npm install @supabase/supabase-js` used for Auth, Database, Realtime, Storage.
- `npx expo install react-native-screens react-native-safe-area-context` is the React navigation system.
- `npm install @tanstack/react-query` Server state management.
- `npm install zustand` For global states like current user, authentication, etc.
- `npm install react-hook-form` Used for Create Job, Edit Profile, Leave Review, etc.
- `npm install zod` Used with forms for checks like "title must exist".
- `npm install nativewind tailwindcss` Tailwind for React Native.
- `npx expo install expo-notifications` for messages.
- `npx expo install expo-secure-store` for auth tokens.
- `npm install -D eslint eslint-config-expo` Code quality.
- `npm install -D prettier` Formatting.

## License
This project is licensed under the [MIT License](LICENSE).

## Contact
For issues or questions, reach out to Andrew Rafal at **arafal@ucsd.edu** or contact the UC San Diego CSES Open Source Society.
