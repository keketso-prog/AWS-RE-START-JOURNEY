# AWS S3 Knowledge Quiz Bot

Built an interactive quiz chatbot using AWS Lambda and Amazon Lex that tests users' knowledge of Amazon S3. The bot guides users through a 10-question quiz with personalized feedback and scoring.

# Quiz Structure

The bot asks 10 questions covering S3 topics with automatic grading and feedback. Users can complete the full quiz or exit after questions 3, 6, or 9 to receive a partial score.
# Step-by-Step Implementation

# Step 1: Create Lambda Function
- Navigated to AWS Lambda in the console
- Created new function with Python runtime
- Copied the quiz handler code into the function
- Configured basic execution role with necessary permissions

<img width="1587" height="861" alt="Screenshot (1945)" src="https://github.com/user-attachments/assets/1930e8af-987f-4948-96d7-81322a52ad80" />

<img width="1590" height="829" alt="Screenshot (1946)" src="https://github.com/user-attachments/assets/ea783f3c-2f85-43fb-a5de-816558060221" />

<img width="1584" height="819" alt="Screenshot (1947)" src="https://github.com/user-attachments/assets/654d93c2-cbdb-4715-b833-928670510f78" />

<img width="1600" height="819" alt="Screenshot (1948)" src="https://github.com/user-attachments/assets/319a32e7-180d-4d80-b60e-238de3ad1aa5" />

<img width="1590" height="819" alt="Screenshot (1951)" src="https://github.com/user-attachments/assets/0aa8e55b-b36d-4b26-8827-7521deb700bc" />


# Step 2: Create Lex Bot
- Opened Amazon Lex console
- Created new bot with voice and text capabilities
- Configured bot settings and language (English)

<img width="1581" height="752" alt="Screenshot (1973)" src="https://github.com/user-attachments/assets/58eaf4b2-990a-4f83-9bfa-dd0fbeb6206d" />

<img width="1600" height="810" alt="Screenshot (1926)" src="https://github.com/user-attachments/assets/e2020f3d-a4cd-4be8-a852-1e21e5d33be9" />

<img width="1590" height="819" alt="Screenshot (1927)" src="https://github.com/user-attachments/assets/c801723c-5804-43a9-b2dc-1c8585ea1689" />

<img width="1590" height="819" alt="Screenshot (1928)" src="https://github.com/user-attachments/assets/5609df1f-e4fc-41ea-976f-f8cfeaf0987b" />


# Step 3: Create Intent
- Added new intent for the quiz flow
- Named intent appropriately 

<img width="1594" height="816" alt="Screenshot (1929)" src="https://github.com/user-attachments/assets/1d783b4a-d9e7-474e-a0ff-e905d26eb95f" />

<img width="1590" height="865" alt="Screenshot (1938)" src="https://github.com/user-attachments/assets/abace96b-a577-4fe3-9fd3-f00f7ded3e30" />

<img width="1600" height="819" alt="Screenshot (1948)" src="https://github.com/user-attachments/assets/b7efa15e-24b4-4eed-96f7-03648b846e3d" />


# Step 4: Configure Slots
- Created UserName slot for collecting user's name
- Created ReadyToStart slot for quiz confirmation
- Created Question1 through Question10 slots for answers
- Created ContinueQuiz slot for progress check-ins
- Set slot types (AMAZON.Confirmation, Username, etc)

<img width="1594" height="823" alt="Screenshot (1956)" src="https://github.com/user-attachments/assets/a9c56fb1-7d79-4de1-b712-fc5b941933ba" />

<img width="1590" height="819" alt="Screenshot (1957)" src="https://github.com/user-attachments/assets/e55a4a24-2ee1-4ab5-b8cf-43d7890930f3" />

<img width="1600" height="819" alt="Screenshot (1958)" src="https://github.com/user-attachments/assets/a2d82833-711e-4a38-bc61-0a71a449de06" />


# Step 5: Add Sample Utterances
- Added phrases users might say to start the quiz
- Examples: "quiz, start quiz, hello, hi"

<img width="1584" height="813" alt="Screenshot (1955)" src="https://github.com/user-attachments/assets/db96af08-cb0c-43b2-98be-de8a5a938602" />

# Step 6: Connect Lambda to Lex
- In Lex intent settings, enabled Lambda fulfillment
- Selected the Lambda function created in Step 1
- Granted Lex permission to invoke the Lambda function

<img width="1594" height="819" alt="Screenshot (1949)" src="https://github.com/user-attachments/assets/55181892-bb81-4b20-8605-b39cd0077694" />

<img width="1594" height="823" alt="Screenshot (1950)" src="https://github.com/user-attachments/assets/89be6662-49dd-466a-a0d5-72f73fd9b3d7" />


# Step 7: Build and Test
- Built the Lex bot to compile all configurations
- Tested the bot using the test window in Lex console
- Verified question flow and scoring logic
- Fixed any issues with slot elicitation or responses




# Step 8: Deploy
- Created bot alias for deployment
- Published the bot version
- Made the bot available for testing

<img width="1596" height="737" alt="Screenshot (1972)" src="https://github.com/user-attachments/assets/b282e9a0-f114-4a09-a18c-18004a882778" />


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

  # Challenges
 -  Connecting Lambda to Lex
Getting Lambda and Lex to work together was harder than expected. At first, they wouldn't connect properly. I had to make sure Lex had the right permissions to call my Lambda function. There were integration errors that I had to fix one by one. After several tries and adjustments, I finally got them connected and communicating correctly.
- Arranging the Slots
Setting up the slots in the right order was tricky. I needed to plan out exactly when each question should appear and how the conversation should flow. The bot needed to ask for the user's name first, then confirm they were ready, then go through all 10 questions in order, and also check if they wanted to continue after questions 3, 6, and 9.
Getting the slot priority right took time. I had to make sure each slot was elicited at the correct moment and that the bot didn't skip questions or ask them out of order. It took several attempts and testing sessions to get everything working smoothly. Each time I tested, I found something that needed adjusting until the flow felt natural


# What i learned
This project showed me that building AI-powered applications involves more than just code—it requires careful planning, understanding how services interact, and lots of testing to create a smooth user experience

# Working as a team

This was a team project where everyone had different roles. I took the initiative to build the bot and handle the Lambda intent because I wanted to learn more about how conversational AI works on AWS. I was curious about the backend logic and how to make a chatbot actually function.
Other team members focused on creating the presentation and explaining our work. While they prepared slides and practiced the demo, I dove deep into the technical implementation. This division of work allowed each person to contribute their strengths to the project.
Taking on the bot development pushed me out of my comfort zone and forced me to learn new skills. It was challenging, but the hands-on experience was exactly what I needed to understand how these AWS services really work together.
