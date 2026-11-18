import tailwindcss from '@tailwindcss/vite';
import react from '@vitejs/plugin-react';
import fs from 'fs';
import path from 'path';
import {defineConfig} from 'vite';

export default defineConfig(() => {
  return {
    plugins: [
      react(),
      tailwindcss(),
      // Copies src/assets into dist/ so root-relative URLs like
      // "/src/assets/images/..." (e.g. generate_image output) still resolve
      // in production builds. Do not remove.
      {
        name: 'copy-unbundled-src-assets',
        apply: 'build',
        closeBundle(error?: Error): void {
          if (error) {
            return;
          }
          const distDir = path.resolve(__dirname, 'dist');
          const srcAssets = path.resolve(__dirname, 'src/assets');
          const distAssets = path.resolve(distDir, 'src/assets');
          if (fs.existsSync(distDir) && fs.existsSync(srcAssets)) {
            fs.cpSync(srcAssets, distAssets, {recursive: true, force: true});
          }
        },
      },
    ],
    resolve: {
      alias: {
        '@': path.resolve(__dirname, '.'),
      },
    },
    server: {
      // HMR is disabled in AI Studio via DISABLE_HMR env var.
      // Do not modify—file watching is disabled to prevent flickering during agent edits.
      hmr: process.env.DISABLE_HMR !== 'true',
      {
  "compilerOptions": {
    "target": "ES2022",
    "experimentalDecorators": true,
    "useDefineForClassFields": false,
    "module": "ESNext",
    "types": ["vite/client"],
    "lib": [
      "ES2022",
      "DOM",
      "DOM.Iterable"
    ],
    "skipLibCheck": true,
    "moduleResolution": "bundler",
    "isolatedModules": true,
    "moduleDetection": "force",
    "allowJs": true,
    "jsx": "react-jsx",
    "paths": {
      "@/*": [
        "./*"
      ]
    },
    "allowImportingTsExtensions": true,
    "noEmit": true
  },
  "exclude": ["dist"]
  {
  "name": "react-example",
  "private": true,
  "version": "0.0.0",
  "type": "module",
  "scripts": {
    "dev": "vite --port=3000 --host=0.0.0.0",
    "build": "vite build",
    "preview": "vite preview",
    "clean": "rm -rf dist server.js",
    "lint": "tsc --noEmit"
  },
  "dependencies": {
    "@google/genai": "^2.4.0",
    "@tailwindcss/vite": "^4.3.3",
    "@vitejs/plugin-react": "^6.1.1",
    "lucide-react": "^0.546.0",
    "react": "^19.0.1",
    "react-dom": "^19.0.1",
    "vite": "^8.3.0",
    "express": "^4.21.2",
    "dotenv": "^17.2.3",
    "motion": "^12.23.24"
  },
  "devDependencies": {
    "@types/node": "^22.14.0",
    "@types/react": "^19.3.0",
    "@types/react-dom": "^19.3.0",
    "autoprefixer": "^10.4.21",
    "esbuild": "^0.25.0",
    "tailwindcss": "^4.3.3",
    "tsx": "^4.21.0",
    "typescript": "^7.0.2",
    "@types/express": "^4.17.21"
    
  "name": "AgriShare Energy",
  "description": "منصة رقمية جزائرية لمشاركة المعدات الفلاحية وتبادل فائض الطاقة الشمسية والبطاريات بالدينار الجزائري عبر 58 ولاية",
  "requestFramePermissions": [],
  "majorCapabilities": ["MAJOR_CAPABILITY_SERVER_SIDE_GEMINI_API"]
  <!doctype html>
<html lang="ar" dir="rtl">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>AgriShare Energy الجزائر — مشاركة المعدات الفلاحية والطاقة الشمسية عبر 58 ولاية</title>
    <meta name="description" content="منصة رقمية جزائرية لمشاركة المعدات الفلاحية وتبادل فائض الطاقة الشمسية والبطاريات بالدينار الجزائري عبر كل ولايات الجزائر الـ 58" />
    <meta property="og:title" content="AgriShare Energy الجزائر — مشاركة المعدات الفلاحية والطاقة الشمسية" />
    <meta property="og:description" content="منصة رقمية جزائرية لمشاركة المعدات الفلاحية وتبادل فائض الطاقة الشمسية والبطاريات بالدينار الجزائري عبر 58 ولاية" />
    <meta property="og:type" content="website" />
    <meta property="og:image" content="/assets/aistudio/2b7084da-ef95-417d-b423-1e1d05e64c21_193bf8b4.jpg" />
    <meta name="twitter:card" content="summary_large_image" />
    <link rel="icon" type="image/jpeg" href="/assets/aistudio/2b7084da-ef95-417d-b423-1e1d05e64c21_193bf8b4.jpg" />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Cairo:wght@600;700&family=IBM+Plex+Mono:wght@400;500&family=IBM+Plex+Sans+Arabic:wght@400;500;600;700&display=swap"
      rel="stylesheet"
    />
  </head>
  <body class="bg-[#F7F9F6] text-[#0F1F16] antialiased selection:bg-[#15803D]/15 selection:text-[#0F1F16]">
    <div id="root"></div>
    <script type="module" src="/src/main.tsx"></script>
  </body>
</html>

      // Disable file watching when DISABLE_HMR is true to save CPU during agent edits.
      @import "tailwindcss";

@theme {
  --font-display: "Cairo", "IBM Plex Sans Arabic", system-ui, sans-serif;
  --font-sans: "IBM Plex Sans Arabic", system-ui, sans-serif;
  --font-mono: "IBM Plex Mono", ui-monospace, monospace;
}

@layer base {
  html {
    font-family: var(--font-sans);
    scroll-behavior: smooth;
  }

  h1, h2, h3, .font-display {
    font-family: var(--font-display);
  }

  .tabular-nums {
    font-variant-numeric: tabular-nums;
  }
}

@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
    
      watch: process.env.DISABLE_HMR === 'true' ? null : {},
    },
