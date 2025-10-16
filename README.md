# CozyTimes Photo Sharing Platform

> **Live**: [cozytimes.club](https://cozytimes.club) — *A warm corner of the internet for sharing life's cozy moments* ☕✨

## 🌟 About CozyTimes

CozyTimes is a photo sharing platform designed for authentic connection and mindful sharing. Built with modern web technologies on Cloudflare's global edge network, it delivers a fast, beautiful experience for capturing and sharing the small moments that make life special.

Whether it's a sunset from your window, a homemade meal, or your favorite reading nook, CozyTimes celebrates the everyday moments that bring warmth to our lives.

## ✨ Features

### Photo Sharing, Simplified
- **Effortless Uploads**: Share photos with captions and location tags
- **Curated Albums**: Organize memories into themed collections
- **Thoughtful Interactions**: Express appreciation with likes and meaningful comments
- **Cosmic Design**: A calming, space-inspired visual theme that's easy on the eyes

### Built for Performance
- **Edge-First Architecture**: Sub-100ms response times globally via Cloudflare Workers
- **Optimized Images**: Automatic compression and CDN delivery for instant loading
- **Offline-Ready**: Progressive Web App features for seamless mobile experience
- **Type-Safe**: End-to-end TypeScript for reliability and maintainability

## 🛠️ Technical Architecture

### Modern Stack
```typescript
Framework:    Next.js 15.4.4 (App Router + React Server Components)
Language:     TypeScript 5.7+ (Strict Mode)
CMS:          PayloadCMS 3.59.1
Database:     Cloudflare D1 (SQLite + Drizzle ORM)
Storage:      Cloudflare R2 (S3-compatible)
Runtime:      Cloudflare Workers (Edge)
```

### Frontend Experience
```typescript
UI:           React 19 + shadcn/ui (Radix UI primitives)
Styling:      TailwindCSS 3.4+ with custom cosmic theme
Animations:   Framer Motion 12+ (spring physics & stagger effects)
Forms:        React Hook Form 7.45
Icons:        Lucide React
Testing:      Playwright (E2E) + Vitest (Integration)
```

## 🎨 The Cosmic Theme

CozyTimes features a carefully crafted color palette inspired by deep space — calming blues, warm purples, and vibrant coral accents that create a serene browsing experience.

```css
Deep Space Blue  • Cosmic Purple  • Vibrant Coral  • Accent Gold
```

The design prioritizes readability, accessibility, and a sense of tranquility. Every interaction is thoughtfully animated with smooth, natural motion that feels responsive without being distracting.

## 🏗️ Architecture Highlights

### Headless CMS with PayloadCMS
Custom-built collections power the entire platform:
- **MediaPosts**: Photos with metadata, geolocation, and social features
- **PhotoAlbums**: Curated collections with custom ordering
- **Users**: Role-based authentication and access control
- **Media**: Intelligent file management with R2 storage integration

### Edge Computing Strategy
Deployed on Cloudflare's global network with:
- D1 SQLite for low-latency data access
- R2 object storage with automatic CDN distribution
- Read replicas for optimal query performance
- Worker bindings for seamless service integration

### Type Safety Throughout
```typescript
// Auto-generated types from CMS schema
import type { MediaPost, User, PhotoAlbum } from '@/payload-types'

// Strict TypeScript configuration ensures reliability
// Database → API → Components = End-to-end type safety
```

## 🚀 Development

### Local Setup
```bash
# Install dependencies
pnpm install

# Authenticate with Cloudflare
pnpm wrangler login

# Start development server (auto-binds D1 + R2)
pnpm dev

# Run test suite
pnpm test
```

### Deployment to Cloudflare Workers
```bash
# Create database migrations
pnpm payload migrate:create

# Deploy to production
pnpm run deploy
```

The deployment pipeline automatically runs migrations, builds the optimized bundle, and distributes to Cloudflare's global edge network.

## 📦 Project Structure

```
src/
├── app/
│   ├── (frontend)/         # Public photo feed & pages
│   ├── (payload)/          # Admin panel & CMS routes
│   └── api/                # Custom API endpoints
├── collections/
│   ├── MediaPosts.ts       # Photo sharing collection
│   ├── Users.ts            # Authentication & roles
│   ├── Media.ts            # R2 storage integration
│   └── PhotoAlbums.ts      # Curated collections
├── migrations/             # Drizzle ORM migrations
└── payload.config.ts       # CMS configuration
```

## 🔐 Access Control

Thoughtful permissions ensure privacy and safety:
- **Public**: Browse and discover photos
- **Authenticated Users**: Upload, like, comment, create albums
- **Administrators**: Full content moderation and user management

## 🌐 Deployment Architecture

**Production Environment**: Cloudflare Workers (Paid Plan)
- **Database**: D1 SQLite with read replicas enabled
- **Storage**: R2 bucket with CDN integration
- **Logs**: Real-time monitoring via Workers Logs
- **Bundle Size**: Optimized < 3MB for Worker limits

### Known Considerations
- GraphQL support limited by [upstream Workers issue](https://github.com/cloudflare/workerd/issues/5175)
- Requires Cloudflare Workers Paid plan due to bundle size requirements
- R2 storage configurable for custom CDN domains

## 💭 The Vision

CozyTimes is built on the belief that social media should feel *cozy* — a place where you can slow down, appreciate beauty in the everyday, and connect authentically without the pressure of perfection.

This platform demonstrates how modern web technologies can create experiences that are both technically excellent and emotionally resonant. Fast, reliable, and delightful to use.

## 🔗 Resources

- [PayloadCMS Documentation](https://payloadcms.com/docs)
- [Cloudflare Workers](https://developers.cloudflare.com/workers/)
- [Next.js 15 App Router](https://nextjs.org/docs)
- [Wrangler CLI Reference](https://developers.cloudflare.com/workers/wrangler/)

---

**Tech Stack**: TypeScript • Next.js 15 • PayloadCMS 3 • Cloudflare Workers • D1 SQLite • R2 Storage • React 19 • TailwindCSS • shadcn/ui • Framer Motion • Playwright • Vitest

*Built with care for those who appreciate life's cozy moments* ☕✨
