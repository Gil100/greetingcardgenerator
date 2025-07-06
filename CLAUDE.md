# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Hebrew greeting card generator built as a React component. The application creates personalized greeting cards for various occasions using AI-generated content through the Claude API.

## Core Dependencies

The project depends on these external libraries:
- **React** (functional components with hooks)
- **Lucide React** for icons (`Heart`, `Gift`, `Sparkles`, `Download`, `Share2`)
- **Tailwind CSS** for styling
- **Claude API** via `window.claude.complete()` - must be available globally

## Architecture

**Single Component Design**: All functionality is contained in `greeting-card-generator.tsx`
- Form handling with React hooks (`useState`)
- Event-driven state management
- Hebrew RTL interface (`dir="rtl"`)
- AI integration for content generation

## Key Features

- **Event Types**: birthday, wedding, bar/bat mitzvah, engagement, graduation, new job, holidays, anniversary
- **Tone Selection**: warm, funny, formal, emotional, casual
- **Hebrew Interface**: All text and prompts are in Hebrew
- **Dynamic Styling**: Event-specific gradient backgrounds
- **Share Functionality**: Native share API with clipboard fallback

## Development Environment

**Single-File HTML Application**: No build system required
- All dependencies loaded via CDN
- Ready to deploy directly to any web server
- No package.json or build configuration needed
- Open index.html directly in browser for development

## Critical Dependencies

- **Google Gemini API**: Primary AI service for intelligent content generation
- **Fallback Mock API**: Development fallback with personalized Hebrew greetings
- **Tailwind CSS**: Must be loaded for styling
- **React and Lucide React**: Must be available

## Form Data Structure

```typescript
formData = {
  eventType: string,      // Required
  recipientName: string,  // Required  
  recipientAge: string,   // Optional
  recipientGender: string, // Required (male/female)
  senderGender: string,   // Required (male/female) - NEW
  relationship: string,   // Optional
  personalDetails: string, // Optional
  tone: array,           // Required (multiple selection)
  additionalNotes: string // Optional
}
```

## AI Prompt Structure

The application generates Hebrew prompts with:
- Event type and tone specifications
- **Dual Gender Support**: Both sender and recipient gender information
- Personal details integration
- Instructions for natural Hebrew language
- **Grammatical Accuracy**: Proper Hebrew verb conjugations for both perspectives
- Specific formatting requirements (2-4 sentences)

## State Management

- `formData` - form input state
- `generatedCard` - AI-generated card content
- `isGenerating` - loading state for AI calls

## Error Handling

Basic error handling for:
- Missing required fields (alert popup)
- AI API failures (console error + alert)
- Network issues during generation

## Development Notes

- All text content is in Hebrew
- Uses Hebrew placeholders and labels
- RTL layout support throughout
- Event-specific color schemes in `getCardBackground()`
- Share functionality detects native share API availability
- Download feature is placeholder (shows alert)

## API Configuration

### Google Gemini API Setup

1. **Get Free API Key**:
   - Visit [Google AI Studio](https://aistudio.google.com/app/apikey)
   - Sign in with Google account
   - Create new API key (free tier: 1,500 requests/day)

2. **Configure API Key** (Choose one method):

   **Method 1: Secure Configuration File (Recommended)**
   - Edit `config.js` file in the project root
   - Replace `YOUR_GEMINI_API_KEY_HERE` with your actual API key
   - File is automatically gitignored for security

   **Method 2: User Settings**
   - Click "הגדרות" (Settings) button in top-right corner
   - Enter your API key when prompted
   - Key is stored securely in browser localStorage

3. **API Features**:
   - **Real AI Generation**: Uses Google Gemini 1.5 Flash model
   - **Hebrew Language Support**: Excellent Hebrew understanding and generation
   - **Personalization**: Utilizes all form data (age, gender, relationship, personal details)
   - **Rate Limiting**: Built-in quota tracking (1,500 requests/day)
   - **Error Handling**: Automatic fallback to mock API if issues occur
   - **Quota Management**: Real-time remaining quota display

4. **Rate Limiting**:
   - Daily limit: 1,500 requests (Google's free tier)
   - Automatic quota tracking and reset every 24 hours
   - Clear error messages when quota is exceeded
   - Quota status displayed in UI

5. **Fallback System**:
   - If no API key configured: Uses intelligent mock API
   - If API fails: Graceful fallback with error logging
   - If quota exceeded: Clear error message with reset time
   - Mock API includes sophisticated Hebrew personalization

### Security Notes

- API keys can be stored in gitignored config file
- Alternative: API keys stored only in browser localStorage
- No server-side storage or transmission
- User controls their own API key
- Remove key anytime via settings
- Config file is automatically excluded from git commits

## Future Development Considerations

- Add proper TypeScript interfaces
- Split into multiple components for maintainability
- Add error boundaries (already implemented)
- Implement state persistence (already implemented)
- Add loading states and better UX feedback (already implemented)
- Consider server-side API proxy for enhanced security