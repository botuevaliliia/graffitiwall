# Graffiti Wall

A standalone digital graffiti wall powered by Google Gemini AI. Users can double-click anywhere on the canvas to leave their mark with AI-generated graffiti-style text.

## Features

- 🎨 AI-generated graffiti images using Google Gemini
- 🖱️ Interactive canvas with pan, zoom, and drag functionality
- 🎯 Client-side background removal for clean graffiti rendering
- 💾 SQLite database for simple persistence
- ❤️ Like system for graffiti notes
- 🎨 8 vibrant color tones (pink, orange, yellow, lime, cyan, blue, purple, magenta)
- 🔄 Auto-generated rotation and scale for natural graffiti look

## Setup

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Set up environment variables:**
   Create a `.env.local` file in the root directory:
   ```
   DATABASE_URL="file:./dev.db"
   GEMINI_API_KEY="your-gemini-api-key-here"
   ```

   Get your Gemini API key from [Google AI Studio](https://makersuite.google.com/app/apikey)

3. **Initialize the database:**
   ```bash
   npm run db:push
   ```

4. **Start the development server:**
   ```bash
   npm run dev
   ```

5. **Open in browser:**
   Navigate to [http://localhost:3000](http://localhost:3000)

## Usage

- **Double-click** anywhere on the canvas to create a new graffiti note
- Type your text and press **Cmd/Ctrl + Enter** to generate the AI graffiti
- **Drag** notes to reposition them
- **Click the heart** to like a graffiti note
- **Cmd/Ctrl + scroll** to zoom in/out
- **Click and drag** the background to pan around the wall

## Tech Stack

- **Next.js 14** - React framework
- **TypeScript** - Type safety
- **Prisma** - Database ORM
- **SQLite** - Lightweight database
- **Google Gemini AI** - AI image generation
- **Tailwind CSS** - Styling

## Database Schema

```prisma
model GraffitiNote {
  id        String   @id @default(cuid())
  text      String
  imageUrl  String?
  x         Float    @default(0)
  y         Float    @default(0)
  tone      String?
  rotation  Int      @default(0)
  scale     Float    @default(1)
  likes     Int      @default(0)
  createdAt DateTime @default(now())
}
```

## API Endpoints

- `GET /api/graffiti` - Fetch all graffiti notes
- `POST /api/graffiti` - Create a new graffiti note with AI-generated image
- `PATCH /api/graffiti` - Update position or likes for a note

## Deployment

This app can be deployed to any platform that supports Next.js:

### Vercel (Recommended)

1. Push your code to GitHub
2. Import the project in Vercel
3. Add the `GEMINI_API_KEY` environment variable
4. Deploy!

Note: You'll need to switch from SQLite to PostgreSQL for production. Update `prisma/schema.prisma`:

```prisma
datasource db {
  provider = "postgresql"
  url      = env("DATABASE_URL")
}
```

Then run:
```bash
npx prisma migrate dev --name init
```

## License

MIT
# graffitiwall
