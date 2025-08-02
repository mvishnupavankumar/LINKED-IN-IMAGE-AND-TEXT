# LINKED-IN-IMAGE-AND-TEXT

🤖 AI-Powered LinkedIn Post Generator 🚀
This n8n workflow lets you automatically generate and publish a personalized LinkedIn post, complete with an image, simply by filling out a form. It uses AI to turn a simple text file into a professional, engaging post and then publishes it to your LinkedIn profile.

⚙️ How It Works (step-by-step)
🔹 1. On form submission ✍️
Simple: This is the starting point of the workflow. You fill out a simple form to provide the necessary information.

Tech: Uses the Form Trigger node to start the workflow when a form is submitted with a text file and an image file.

🔹 2. EXTRACT JSON 🧱
Simple: This step reads the text file you uploaded and understands the content inside.

Tech: A Code node decodes the base64-encoded text file and parses its contents as a JSON object, making the data accessible to later nodes.

🔹 3. MAKE PREETY WAY & SUMMARIZE IT 🤖
Simple: This is where the magic happens! The workflow sends your content to an AI model to create a high-quality summary.

Tech: Two Code nodes and an HTTP Request node work together to craft a detailed prompt for a Gemini AI model, which then generates a summary of the provided text.

🔹 4. EXTRACT DATA & MAKE IN FORMAT ✍️
Simple: This part takes the summary from the AI and turns it into a formatted LinkedIn post in a specific style.

Tech: A Set node extracts the summary text, and another Code node uses it to create a new prompt for the AI to generate a complete LinkedIn post with a specific tone and structure.

🔹 5. MAKE POST TEXT & MAKE PREETY WAY1 🎉
Simple: The final text for your LinkedIn post is generated here. It's ready to be published.

Tech: An HTTP Request node sends the new prompt to the Gemini AI to get the final post content, and a Code node cleans up the response to make it ready for LinkedIn.

🔹 6. EXTRACT DATA1 🧱
Simple: This step prepares the final post text so it can be combined with the image.

Tech: A Set node extracts the cleaned-up LinkedIn post text and makes it available as a single variable for the next step.

🔹 7. Merge 🤝
Simple: This node brings the image and the generated post text together into a single item.

Tech: A Merge node combines the output of the initial form submission (the image) and the final post text from the AI generation.

🔹 8. Create a post 📝
Simple: The workflow publishes your brand-new, AI-generated post directly to your LinkedIn profile.

Tech: The LinkedIn node uses the combined image and text to create a new share on your profile.

🔹 9. Send a text message ✅
Simple: You get a confirmation message letting you know the post was successfully published.

Tech: A Telegram node sends a simple text message to a specified chat to confirm the workflow's completion.

🔁 Replace the following before running:
🔐 YOUR_GOOGLE_GEMINI_API_KEY
Replace this with your personal Google Gemini API key inside the HTTP Request nodes (SUMMARIZE IT and MAKE POST TEXT).

🪪 YOUR_LINKEDIN_CREDENTIALS
Configure your LinkedIn OAuth2 credentials in n8n under the Credentials section.

💬 YOUR_TELEGRAM_BOT_TOKEN
Add your bot token to your Telegram credentials in n8n.

💬 YOUR_TELEGRAM_CHAT_ID
Insert your personal Telegram chat ID in the Send a text message node to receive notifications.

🧪 Testing Instructions
✅ Open n8n at http://localhost:5678
🔧 Click “Import Workflow” and paste the JSON data.
✍️ Fill out the form provided by the Form Trigger node.
🧪 Click “Execute Workflow” to run the entire process.
🪵 Check the execution log to troubleshoot any issues.

💡 Tips for Beginners
💡 Use the "Credentials" tab to set up your LinkedIn and Telegram accounts securely.
💡 Check the output of each node by clicking it after a test run to see the data flow.
💡 You can customize the AI prompts in the Code nodes (MAKE PREETY WAY and MAKE IN FORMAT) to change the tone and style of your LinkedIn posts.
💡 Ensure the JSON file you upload in the form is correctly formatted for the AI to process.




Gemini can make mistak
