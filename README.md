# Graffiti Wall

A standalone digital graffiti wall powered by Google Gemini AI. Users can double-click anywhere on the canvas to leave their mark with AI-generated graffiti-style text.

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

3. **Initialize the database:**
   ```bash
   npm run db:push
   ```

4. **Start the development server:**
   ```bash
   npm run dev
   ```
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

## Usage

- **Double-click** anywhere on the canvas to create a new graffiti note
- Type your text and press **Cmd/Ctrl + Enter** to generate the AI graffiti
- **Drag** notes to reposition them
- **Cmd/Ctrl + scroll** to zoom in/out
- **Click and drag** the background to pan around the wall


<img width="982" height="966" alt="Screenshot 2025-11-19 at 5 44 42 PM" src="https://github.com/user-attachments/assets/2feda230-ca1c-4aca-9cd9-5dc58eb4ecb7" />

Wouldn't it be cool if street art could exist in internet too? like how you walk in city and discover cool art on the walls - you could surf in the web - and see arts there as well 🤓
