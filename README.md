<div align="center">
<img width="1200" height="475" alt="GHBanner" src="https://github.com/user-attachments/assets/0aa67016-6eaf-458a-adb2-6e31a0763ed6" />
</div>

# Run and deploy your AI Studio app

This contains everything you need to run your app locally.

View your app in AI Studio: https://ai.studio/apps/1e87d087-53a8-44e2-b413-7587cc5a0e14

## Run Locally

**Prerequisites:**  Node.js


1. Install dependencies:
   `npm install`
2. Set the `VITE_DOUBAO_API_KEY` in [.env.local](.env.local) to your Doubao API key
3. Run the app:
   `npm run dev`

## Deploy to Vercel

This project is now configured for direct Vercel deployment:

- `vercel.json` sets:
  - build command: `npm run build`
  - output directory: `dist`
  - Node runtime for `/api/*.ts` serverless functions
  - SPA rewrite fallback to `/index.html` (while keeping `/api/*` routes working)

### Steps

1. Import this repo in Vercel.
2. Set environment variables in Vercel Project Settings:
   - `VITE_DOUBAO_API_KEY`
   - optional model variables like `VITE_DOUBAO_CHAT_MODEL`, `VITE_DOUBAO_IMAGE_MODEL`, `VITE_DOUBAO_VIDEO_MODEL`
3. Deploy.

After deployment, frontend requests to `/api/proxy` will be handled by `api/proxy.ts` on Vercel.
