# AWS S3 Knowledge Quiz Bot

Built an interactive quiz chatbot using AWS Lambda and Amazon Lex that tests users' knowledge of Amazon S3. The bot guides users through a 10-question quiz with personalized feedback and scoring.

# Features

# User Experience
- Personalized greeting with name collection
- Confirmation prompt before starting the quiz
- 10 multiple-choice and true/false questions about S3
- Progress check-ins after every 3 questions
- Option to exit early and see partial results
- Detailed score breakdown with performance rating

# Quiz Content
- S3 fundamentals and terminology
- Storage classes and features
- Bucket configuration and limits
- Object management concepts
- Durability and availability topics

# Scoring System
- Real-time answer validation
- Automatic score calculation
- Performance ratings based on percentage
- Shows correct answers for missed questions
- Supports both full completion and early exit

# Technical Implementation

# AWS Services Used
- AWS Lambda for backend logic
- Amazon Lex for conversational interface
- Session management for tracking progress

# Key Functionality
- Answer normalization for flexible input handling
- Slot-based conversation flow
- Session attributes for state management
- Dynamic question progression
- Conditional prompts based on progress

# Quiz Structure

The bot asks 10 questions covering S3 topics with automatic grading and feedback. Users can complete the full quiz or exit after questions 3, 6, or 9 to receive a partial score.
# Step-by-Step Implementation

# Step 1: Create Lambda Function
- Navigated to AWS Lambda in the console
- Created new function with Python runtime
- Copied the quiz handler code into the function
- Configured basic execution role with necessary permissions

# Step 2: Create Lex Bot
- Opened Amazon Lex console
- Created new bot with voice and text capabilities
- Configured bot settings and language (English)

# Step 3: Create Intent
- Added new intent for the quiz flow
- Named intent appropriately 

# Step 4: Configure Slots
- Created UserName slot for collecting user's name
- Created ReadyToStart slot for quiz confirmation
- Created Question1 through Question10 slots for answers
- Created ContinueQuiz slot for progress check-ins
- Set slot types (AMAZON.Confirmation, Username, etc)

# Step 5: Add Sample Utterances
- Added phrases users might say to start the quiz
- Examples: "quiz, start quiz, hello, hi"

# Step 6: Connect Lambda to Lex
- In Lex intent settings, enabled Lambda fulfillment
- Selected the Lambda function created in Step 1
- Granted Lex permission to invoke the Lambda function

# Step 7: Build and Test
- Built the Lex bot to compile all configurations
- Tested the bot using the test window in Lex console
- Verified question flow and scoring logic
- Fixed any issues with slot elicitation or responses

# Step 8: Deploy
- Created bot alias for deployment
- Published the bot version
- Made the bot available for testing
