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

- `window.claude.complete()` must be available for AI functionality
- Tailwind CSS must be loaded for styling
- React and Lucide React must be available

## Form Data Structure

```typescript
formData = {
  eventType: string,      // Required
  recipientName: string,  // Required  
  recipientAge: string,   // Optional
  relationship: string,   // Optional
  personalDetails: string, // Optional
  tone: string,           // Required
  additionalNotes: string // Optional
}
```

## AI Prompt Structure

The application generates Hebrew prompts with:
- Event type and tone specifications
- Personal details integration
- Instructions for natural Hebrew language
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

## Future Development Considerations

- Add proper TypeScript interfaces
- Implement actual download functionality
- Add form validation beyond required fields
- Split into multiple components for maintainability
- Add error boundaries
- Implement state persistence
- Add loading states and better UX feedback