# Saaj (صاج)

**An Arabic-first AI recipe app: paste a TikTok, Instagram or YouTube link and get a clean, structured recipe you can actually cook from.**

<img src="images/screens.webp" alt="Welcome screen, recipe library and step-by-step cook mode" width="100%">

## The problem

Gulf home cooks save recipes from TikTok and Instagram, but the recipe is buried in a video or a messy caption. When it's time to cook, there's no ingredient list, no quantities and no steps.

## The solution

- **Import from anywhere.** A social link, a photo or typed text becomes a structured recipe (title, servings, times, ingredients with quantities, and ordered steps) using the Gemini API.
- **Cook mode.** One step at a time, in large type, with the screen kept awake.
- **Make it fit my diet.** Ingredient substitutions for dietary needs.
- **What's in my fridge?** Take a photo and get recipe suggestions you can make right now.
- **Organisation.** Cookbooks, a meal plan and a grocery list grouped by aisle.

## How it works

```
Link / photo / text
        │
        ▼
Supabase Edge Function ──▶ Gemini API ──▶ structured recipe (JSON)
        │                                   (Gemini key stays server-side)
        ▼
Postgres: ingredients + steps stored as JSONB
Row-Level Security on every user table
        │
        ▼
React Native app (Expo): library · cook mode · meal plan · groceries
```

## Tech stack

React Native · Expo Router · TypeScript · Zustand · Supabase (Postgres, Auth, Edge Functions, RLS) · Gemini API

## Status

🛠️ **In development.** The app runs in guest/local mode, and the AI backend is built but not yet deployed.

*Screenshots show invented demo recipes.*

---

Source code is private and available on request. More about me: [Abdullah-Albariqi](https://github.com/Abdullah-Albariqi)
