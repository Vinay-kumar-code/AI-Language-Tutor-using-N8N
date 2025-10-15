🧠 AI Language Tutor (n8n + Supabase + ElevenLabs)
This project automates a two-part AI Language Tutor using n8n, Supabase, and ElevenLabs. It personalizes language learning by leveraging user preferences, maintaining chat history memory, generating AI-driven responses, and providing text-to-speech audio replies.

🚀 Workflows Overview
This project consists of two core n8n workflows that work together to create a seamless user experience.

1️⃣ User Onboarding
Purpose: To collect and store the language learning preferences for each new user.

Trigger: A POST request to the webhook endpoint: /user-onboarding.

Action: Saves the user's data to the user_preferences table in a Supabase database.

Output: A JSON response confirming success.

{
  "status": "success",
  "message": "User preferences saved successfully."
}

<img width="1044" height="454" alt="image" src="https://github.com/user-attachments/assets/09152d1d-40ff-40fb-ad23-c04c45f35857" />

2️⃣ Conversational Tutor
Purpose: To respond to the user chat message.

Trigger: A POST request to the webhook endpoint: /chat-message.

Process:

Fetches the user's stored preferences and the last 10 messages from their chat history.

Constructs a smart, context-aware prompt for the language model.

Generates a personalized response using LLaMA 4 Maverick (via OpenRouter).

Saves both the user's new message and the AI's response to the chat_history table using Supabase Database.

Converts the AI's text response into speech using the ElevenLabs API.

Returns the generated audio file directly in the webhook response.

🧩 Tech Stack
Automation: n8n – The core platform for building and running the workflows.

Database: Supabase – Used for storing user preferences and chat history.

AI Model: OpenRouter / LLaMA 4 Maverick Free – For generating intelligent, human-like conversation.

Text-to-Speech: ElevenLabs – For converting the AI's text response into high-quality audio.

🧰 Project Files
File

Description

Workflow1_UserOnboarding.json

The n8n workflow for onboarding new users.

Workflow2_ConversationalTutor.json

The n8n workflow that powers the main AI tutor chat.

User_Preferences_Table.sql

(Optional) The SQL schema for the user preferences table.

Chat_History_Table.sql

(Optional) The SQL schema for the chat history table.

🎥 Demo
You can view a quick video walkthrough of the automation setup and see the project in action here:

📺 Watch the Demo Video (<- Replace with your actual video link)

👤 Author
Vinay Kumar

Built as part of the AI Internship Assignment.
