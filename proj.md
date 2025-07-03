# Greeting Card Generator Project

## Product Requirements Document (PRD)

### Project Overview
Hebrew greeting card generator with AI-powered content creation, following single-file HTML architecture with CDN dependencies.

### Core Features
- **Multi-event Support**: Birthday, wedding, bar/bat mitzvah, engagement, graduation, new job, holidays, anniversary
- **Tone Selection**: Warm, funny, formal, emotional, casual
- **AI Integration**: Mock Claude API for development
- **Hebrew RTL Interface**: Full Hebrew support with right-to-left layout
- **Data Persistence**: localStorage for form data and generated cards
- **Error Handling**: React Error Boundary with graceful error recovery
- **Share Functionality**: Native share API with clipboard fallback

### Technical Stack
- **Frontend**: React 18 with functional components and hooks
- **Styling**: Tailwind CSS via CDN
- **Icons**: Lucide React
- **Architecture**: Single-file HTML application
- **Data Storage**: localStorage for client-side persistence
- **Error Handling**: React Error Boundary + try-catch blocks

### Implementation Plan

#### Phase 1: Core Infrastructure ✅
- [x] Set up single-file HTML structure with CDN dependencies
- [x] Implement React Error Boundary for error handling
- [x] Create mock Claude API for development
- [x] Implement Hebrew RTL layout and styling

#### Phase 2: Form and State Management ✅
- [x] Build multi-step form with event types and tones
- [x] Implement form validation with Hebrew error messages
- [x] Add localStorage persistence for form data
- [x] Create state management with React hooks

#### Phase 3: AI Integration and Card Generation ✅
- [x] Connect to mock Claude API
- [x] Implement Hebrew prompt generation
- [x] Create dynamic card display with event-specific styling
- [x] Add generated cards storage in localStorage

#### Phase 4: User Experience Features ✅
- [x] Implement share functionality with clipboard fallback
- [x] Add loading states and error feedback
- [x] Create responsive design for mobile and desktop
- [x] Add form reset functionality

### File Structure
```
greetingcardgenerator/
├── index.html                 # Main application file
├── greeting-card-generator.tsx # Original React component (deprecated)
├── CLAUDE.md                  # Development guidance
└── proj.md                   # This project plan
```

### Key Features Implemented

#### Form Validation
- Required fields: event type, recipient name, tone
- Real-time validation feedback in Hebrew
- Error message display with clear styling

#### Data Persistence
- Form data automatically saved to localStorage
- Generated cards history (last 10 cards)
- Error logging for debugging

#### Error Handling
- React Error Boundary for component errors
- Try-catch blocks for API calls and localStorage operations
- Graceful degradation for share functionality

#### Hebrew Language Support
- RTL layout with `dir="rtl"` attribute
- Hebrew placeholders and labels
- Israeli date formatting ready
- Hebrew error messages

### Development Standards Applied
- **Naming**: camelCase for React, snake_case for functions
- **Code Style**: Functional components with hooks
- **Error Handling**: Comprehensive error boundaries
- **Performance**: useMemo for expensive calculations
- **Accessibility**: Proper semantic HTML and ARIA labels

### Testing Checklist
- [ ] Form validation works correctly
- [ ] Data persistence across browser sessions
- [ ] Error handling displays proper messages
- [ ] Share functionality works on different devices
- [ ] Hebrew text displays correctly in RTL layout
- [ ] Responsive design works on mobile and desktop
- [ ] AI integration generates appropriate content
- [ ] LocalStorage doesn't exceed browser limits

## Change Log

### Version 1.0.0 - Initial Implementation
**Date**: 2025-07-03

**Changes Made**:
- Converted standalone React component to single-file HTML application
- Implemented CDN-based dependencies (React 18, Tailwind CSS, Lucide React)
- Added comprehensive error handling with React Error Boundary
- Created mock Claude API for development and testing
- Implemented Hebrew RTL layout and full Hebrew interface
- Added localStorage data persistence for form data and generated cards
- Created responsive design with mobile-first approach
- Implemented form validation with Hebrew error messages
- Added share functionality with native API and clipboard fallback
- Created event-specific styling with gradient backgrounds
- Added loading states and user feedback mechanisms

**Technical Improvements**:
- Snake_case function naming convention applied
- Memoized expensive calculations with useMemo
- Proper error boundaries and try-catch blocks
- Client-side data validation and storage
- Cross-browser compatibility focus
- Performance optimizations for single-file deployment

**Bug Fixes**:
- Fixed app crash by providing proper HTML structure
- Added missing dependencies via CDN
- Implemented proper state management
- Fixed Hebrew text direction and layout issues
- Added error recovery mechanisms

### Version 1.1.0 - Production Console Fixes
**Date**: 2025-07-03

**Console Error Fixes**:
- Switched to React production builds to eliminate development warnings
- Added crossorigin attributes for proper CORS handling
- Added dependency loading error handling with Hebrew fallback UI
- Enhanced Babel configuration with explicit React presets
- Added process.env polyfill to suppress production warnings

**Production Optimizations**:
- Replaced development React builds with minified production versions
- Added dependency availability checks before app initialization
- Improved error boundary with better Hebrew error messages
- Enhanced loading resilience for CDN failures

### Version 1.2.0 - Custom Event Types Support
**Date**: 2025-07-03

**New Features**:
- Added "אירוע אחר" (Other Event) option to event type selection
- Custom event type input field with Hebrew placeholder examples
- Dynamic event validation for custom events
- AI prompt enhancement to handle custom event types specifically
- Custom event display in generated greeting cards

**Implementation Details**:
- Added `customEventType` to form data state management
- Enhanced form validation to require custom event description when selected
- Modified AI prompt to include custom event-specific instructions
- Updated card display logic to show custom event names
- Added mock AI responses for common custom events (new grandchild, aliyah)
- Extended localStorage persistence to include custom event data

**Examples Supported**:
- נכד חדש (New grandchild) - with appropriate blessing
- עליה לארץ (Immigration to Israel) - with welcome message
- Any user-defined event with contextual AI-generated greetings