<!doctype html><html lang="ar"><head>
<meta charset="UTF-8"/><meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Home NS</title></head><body><div id="root"></div><script type="module" src="/src/main.jsx"></script></body></html>
{
  "name": "home-ns-all-in-one",
  "private": true,
  "version": "0.2.0",
  "type": "module",
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview"
  },
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0"
  },
  "devDependencies": {
    "@vitejs/plugin-react": "^4.2.0",
    "vite": "^5.0.0"
  }
}
{
  "version": 2,
  "builds": [
    {
      "src": "api/*.js",
      "use": "@vercel/node"
    },
    {
      "src": "index.html",
      "use": "@vercel/static"
    }
  ],
  "routes": [
    {
      "src": "/api/(.*)",
      "dest": "/api/$1.js"
    },
    {
      "src": "/(.*)",
      "dest": "/index.html"
    }
  ]
}
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'
export default defineConfig({ plugins:[react()] })
