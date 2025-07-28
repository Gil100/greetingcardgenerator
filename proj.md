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

### Version 1.3.0 - Personalized AI Responses
**Date**: 2025-07-03

**Major AI Enhancement**:
- Completely rewrote mock AI to extract and use all form data for personalization
- AI now addresses recipient by name in every greeting
- Tone-specific variations implemented for all event types
- Personal details integration (profession, hobbies, etc.)
- Relationship context added to greetings
- Dynamic content generation based on extracted information

**Personalization Features**:
- **Name Integration**: All greetings now start with recipient's name
- **Tone Variations**: 
  - מצחיק (Funny) - includes humor and light-hearted jokes
  - רשמי (Formal) - uses formal Hebrew language structure
  - רגשי (Emotional) - deep, heartfelt expressions
  - חם ואישי (Warm & Personal) - friendly, caring tone
  - קליל (Casual) - relaxed, everyday language
- **Professional Context**: Special additions for doctors, teachers, musicians
- **Relationship Context**: Custom additions for siblings, friends, colleagues
- **Personal Details**: AI incorporates hobbies and interests into greetings

**Example Improvement**:
- **Before**: "מזל טוב על הנכד החדש! איזה שמחה גדולה..."
- **After**: "מומו, מזל טוב על הנכד החדש! עכשיו אתה רשמית סבא..." (with tone-specific content)

**Technical Implementation**:
- Regex-based prompt parsing to extract all user inputs
- Conditional greeting generation based on extracted data
- Fallback handling for missing information
- Multi-layered personalization (name + tone + details + relationship)

### Version 1.4.0 - Download Functionality Implementation
**Date**: 2025-07-04

**New Features**:
- **Download Card as PNG**: Users can now download greeting cards as high-quality PNG images
- **Canvas-based Image Generation**: HTML5 Canvas API used to create downloadable images
- **Event-specific Backgrounds**: Downloaded images maintain the same gradient backgrounds as the web version
- **Hebrew Text Support**: Proper RTL text rendering in downloaded images
- **Automatic Filename Generation**: Files are named with recipient name and date in Hebrew format

**Implementation Details**:
- Added `download_card_as_image()` function with HTML5 Canvas API
- Created gradient background matching web version colors
- Implemented multi-line text wrapping for Hebrew content
- Added rounded rectangle drawing with cross-browser compatibility
- Integrated automatic download with proper filename generation
- Canvas size: 800x600 pixels for optimal quality
- Text rendering with proper Hebrew RTL support
- Error handling for download failures

**Technical Features**:
- **Canvas Drawing**: 800x600 pixel canvas with gradient backgrounds
- **Text Wrapping**: Automatic line breaks for long Hebrew text
- **Cross-browser Support**: Manual rounded rectangle implementation
- **File Naming**: Hebrew filename with recipient name and date
- **Error Handling**: Graceful failure handling with Hebrew error messages
- **Memory Management**: Proper cleanup of blob URLs after download

**User Experience**:
- Replaced placeholder "next update" message with functional download
- Download button now creates and saves PNG image
- Filename includes recipient name and current date
- Visual feedback on download success/failure
- Maintains card design consistency between web and downloaded versions

### Version 1.5.0 - Gender-Appropriate Language & Multiple Tone Selection
**Date**: 2025-07-04

**Major Language Enhancement**:
- **Gender Selection Field**: Added mandatory gender selection (זכר/נקבה) to ensure proper Hebrew language forms
- **Gender-Appropriate Hebrew**: All greetings now use correct masculine/feminine forms (אתה/את, יקר/יקרה, נהדר/נהדרת, etc.)
- **Multiple Tone Selection**: Users can now select multiple tones for richer, more complex greetings
- **Combined Tone Processing**: AI generates content that blends selected tones naturally

**New Features**:
- **Gender Selection**: Mandatory field with זכר (male) and נקבה (female) options
- **Multi-Tone Interface**: Enhanced tone selection with visual feedback showing selected combinations
- **Smart Gender Forms**: 20+ gender-specific Hebrew word forms implemented in mock AI
- **Improved Validation**: Added gender requirement to form validation

**Language Improvements**:
- **Masculine Forms**: אתה, יקר, נהדר, מוכשר, אהוב, מביא, תמשיך, המיוחד, מוקף, תתחתן, סבא, עוזר, תקבל, מעצב, חבר, אח, רופא
- **Feminine Forms**: את, יקרה, נהדרת, מוכשרת, אהובה, מביאה, תמשיכי, המיוחדת, מוקפת, תתחתני, סבתא, עוזרת, תקבלי, מעצבת, חברה, אחות, רופאה

**Multiple Tone Examples**:
- **Warm + Funny**: Combines personal warmth with humor naturally
- **Emotional + Formal**: Blends deep feeling with respectful language
- **Casual + Warm**: Relaxed yet caring tone combinations

**Technical Implementation**:
- **Form State Management**: Updated to handle gender and tone arrays
- **AI Prompt Enhancement**: Includes gender information and multiple tone processing
- **Mock AI Rewrite**: Complete overhaul with gender-aware text generation
- **Helper Functions**: Added `get_gender_forms()` function for systematic gender handling
- **Validation Updates**: Enhanced form validation for new required fields

**User Experience Improvements**:
- **Visual Feedback**: Selected tones display with "נבחרו: טון1, טון2" indicator
- **Intuitive Selection**: Toggle-based tone selection for easy multi-selection
- **Gender Clarity**: Clear masculine/feminine buttons with proper Hebrew labels
- **Error Messages**: Updated validation messages in Hebrew for new requirements

**Example Improvements**:
- **Before**: "מומו עכשיו אתה/את יכול/ה להיות גאה/ה"
- **After**: "מומו עכשיו אתה יכול להיות גאה" (for male) or "מומו עכשיו את יכולה להיות גאה" (for female)

**Backward Compatibility**:
- **Form Reset**: All existing form fields preserved and enhanced
- **localStorage**: Updated to handle new data structure
- **Error Handling**: Graceful handling of missing gender information

### Version 1.6.0 - Real AI Integration with Google Gemini API
**Date**: 2025-07-06

**Major AI Enhancement**:
- **Google Gemini API Integration**: Replaced mock API with real Google Gemini 1.5 Flash API
- **Free API Access**: Users can get free API keys with 1,500 requests per day limit
- **Intelligent Fallback System**: Automatic fallback to sophisticated mock API if real API fails
- **Secure API Key Management**: Browser-based localStorage storage with user control

**New Features**:
- **Settings Interface**: Added settings button with API key management
- **API Status Indicator**: Real-time display of current API status (Real AI vs Demo)
- **One-Click Setup**: Guided API key setup with direct links to Google AI Studio
- **Error Handling**: Comprehensive error handling for API failures, rate limits, and invalid keys

**API Integration Details**:
- **Model**: Google Gemini 1.5 Flash for optimal speed and quality
- **Temperature**: 0.7 for creative yet coherent Hebrew content generation
- **Max Tokens**: 1024 tokens for detailed greeting generation
- **Hebrew Support**: Native Hebrew language understanding and generation
- **Personalization**: Full utilization of all form inputs (age, gender, relationship, personal details)

**Security Implementation**:
- **Client-Side Storage**: API keys stored only in user's browser localStorage
- **No Server Transmission**: All API communication happens directly from browser
- **User Control**: Users can add, update, or remove API keys at any time
- **Transparent Status**: Clear indication of whether real AI or demo mode is active

**User Experience Improvements**:
- **Seamless Integration**: No changes required to existing workflow
- **Graceful Degradation**: App works fully without API key (using intelligent mock)
- **Clear Instructions**: Step-by-step API setup guidance in Hebrew
- **Status Visibility**: Always shows current AI service status

**Technical Implementation**:
- **RESTful Integration**: Direct REST API calls to Google Gemini endpoints
- **Error Recovery**: Automatic fallback chain (Real API → Mock API → Error handling)
- **Rate Limit Handling**: Specific handling for API rate limit responses
- **Authentication**: Secure API key handling with validation

**Benefits**:
- **Truly Intelligent Content**: Real AI understands context and generates unique, natural Hebrew greetings
- **Cost Effective**: Free tier supports significant usage (1,500 requests/day)
- **No Dependencies**: Maintained single-file HTML architecture
- **Backward Compatible**: Existing users can continue using mock API seamlessly

**Example Improvement**:
- **Before (Mock)**: "מזל טוב דני על יום הולדתך! שתזכה לשנה מלאה בבריאות ואושר..."
- **After (Real AI)**: "דני היקר, מזל טוב על יום הולדת ה-30! איזה מסע מדהים עברת עד כה - מהתחלת הקריירה בהייטק ועד להיות אבא גאה. שהשנה הבאה תביא לך עוד הצלחות מקצועיות ושמחות משפחתיות!"

### Version 1.7.0 - Dual Gender Grammar Support
**Date**: 2025-07-06

**Critical Grammar Fix**:
- **Sender Gender Field**: Added mandatory sender gender selection for proper Hebrew grammar
- **Dual Gender System**: Both sender (writer) and recipient genders now captured and used
- **Proper Hebrew Conjugations**: Fixed all sender-perspective verb forms (מאחל/מאחלת, חושב/חושבת, etc.)
- **Enhanced Mock AI**: Sophisticated dual-gender Hebrew generation system

**New Features**:
- **Sender Gender Selection**: New required field "המין שלך (כותב הברכה)"
- **Distinguished UI**: Recipient gender (purple) vs sender gender (blue) color coding
- **Comprehensive Validation**: Both genders required before greeting generation
- **Grammar Explanations**: Hebrew tooltip explaining importance of sender gender

**Hebrew Grammar Improvements**:
- **Sender Verbs**: מאחל/מאחלת, חושב/חושבת, שמח/שמחה, גאה/גאה, מתרגש/מתרגשת
- **Perspective Accuracy**: First-person statements now grammatically correct
- **Natural Flow**: Sentences like "אני מאחלת לך" vs "אני מאחל לך" based on actual sender gender
- **Real AI Integration**: Gemini API receives both genders for accurate generation

**Technical Implementation**:
- **Dual Gender Forms**: `get_recipient_forms()` and `get_sender_forms()` helper functions
- **Enhanced Extraction**: Mock AI extracts both "מין מקבל הברכה" and "מין כותב הברכה"
- **Comprehensive Prompts**: Real AI receives detailed gender instructions for both perspectives
- **Form Data Structure**: Updated to include `senderGender` field with automatic persistence

**User Experience**:
- **Clear Labeling**: Distinct labels for recipient vs sender gender selection
- **Visual Distinction**: Different color schemes to avoid confusion
- **Educational Tooltip**: Explains grammar necessity to users
- **Seamless Integration**: No workflow changes, just enhanced accuracy

**Grammar Examples Fixed**:
- **Before**: "אבל אני מאחל לך" (generic, could be wrong)
- **After**: "אבל אני מאחלת לך" (female sender) or "אבל אני מאחל לך" (male sender)
- **Before**: "אני חושב שאת נהדרת" (assuming male sender)
- **After**: "אני חושבת שאת נהדרת" (confirmed female sender)

**Backward Compatibility**:
- **Form Reset**: All existing fields preserved
- **localStorage**: Automatic migration to include sender gender
- **Validation**: Graceful handling of legacy data without sender gender