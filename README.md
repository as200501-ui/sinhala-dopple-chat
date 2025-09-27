sinhala-dopple-chat/
├── index.html          # <!DOCTYPE html>
<html lang="si">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>සිංහල Dopple Chat - නොමිලේ AI සහාය</title>
    <link rel="stylesheet" href="style.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Sinhala&display=swap" rel="stylesheet">
</head>
<body>
    <div class="container">
        <header>
            <h1>🧠 සිංහල AI සහායකයා</h1>
            <p>ඔබේ ප්‍රශ්න සිංහලෙන් අසන්න. අපි ඉංග්‍රීසියට පරිවර්තනය කර AI එකට යවා, නැවත සිංහලට පරිවර්තනය කරන්නෙමු!</p>
        </header>

        <div class="chat-container">
            <div id="chat-messages" class="chat-messages">
                <div class="message bot-message">
                    <strong>AI සහායකයා:</strong> ආයුබෝවන්! මම ඔබට සිංහලෙන් සහාය වීමට සුදුසු AI අසිස්ටන්ට් එකක්. ඔබට කුමක් ගැන දැනගන්න අවශ්‍යද?
                </div>
            </div>

            <div class="input-area">
                <textarea 
                    id="message-input" 
                    placeholder="ඔබේ ප්‍රශ්නය සිංහලෙන් ඇතුළත් කරන්න..." 
                    rows="3"
                ></textarea>
                <button id="send-btn" onclick="sendMessage()">
                    <span>පණිවිඩය යවන්න</span>
                    <div class="loading-spinner" id="loading-spinner"></div>
                </button>
            </div>

            <div class="instructions">
                <h3>උපදෙස්:</h3>
                <ul>
                    <li>සිංහලෙන් සරලව ටයිප් කරන්න</li>
                    <li>Enter බොත්තම ඔබා පණිවිඩය යවන්න</li>
                    <li>ප්‍රතිචාරය ලැබෙන තුරු රැඳී සිටින්න</li>
                </ul>
            </div>
        </div>

        <footer>
            <p>Powered by Free AI APIs | 100% නොමිලේ සේවාව</p>
        </footer>
    </div>

    <script src="script.js"></script>
</body>
</html>
├── style.css           # * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Noto Sans Sinhala', 'Arial Unicode MS', sans-serif;
    line-height: 1.6;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    min-height: 100vh;
    direction: ltr;
}

.container {
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
}

header {
    text-align: center;
    margin-bottom: 30px;
    color: white;
}

header h1 {
    font-size: 2.5em;
    margin-bottom: 10px;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
}

header p {
    font-size: 1.1em;
    opacity: 0.9;
}

.chat-container {
    background: white;
    border-radius: 15px;
    padding: 30px;
    box-shadow: 0 10px 30px rgba(0,0,0,0.2);
    flex: 1;
    display: flex;
    flex-direction: column;
}

.chat-messages {
    flex: 1;
    height: 400px;
    overflow-y: auto;
    border: 2px solid #e0e0e0;
    border-radius: 10px;
    padding: 20px;
    margin-bottom: 20px;
    background: #fafafa;
}

.message {
    margin-bottom: 15px;
    padding: 12px;
    border-radius: 10px;
    animation: fadeIn 0.3s ease-in;
}

@keyframes fadeIn {
    from { opacity: 0; transform: translateY(10px); }
    to { opacity: 1; transform: translateY(0); }
}

.user-message {
    background: #007bff;
    color: white;
    margin-left: 50px;
    text-align: right;
}

.bot-message {
    background: #e9ecef;
    color: #333;
    margin-right: 50px;
}

.input-area {
    display: flex;
    flex-direction: column;
    gap: 15px;
}

textarea {
    width: 100%;
    padding: 15px;
    border: 2px solid #ddd;
    border-radius: 10px;
    font-family: 'Noto Sans Sinhala', sans-serif;
    font-size: 16px;
    resize: vertical;
    transition: border-color 0.3s;
}

textarea:focus {
    outline: none;
    border-color: #007bff;
}

button {
    background: #28a745;
    color: white;
    border: none;
    padding: 15px 30px;
    border-radius: 10px;
    font-size: 16px;
    cursor: pointer;
    transition: background 0.3s;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
}

button:hover {
    background: #218838;
}

button:disabled {
    background: #6c757d;
    cursor: not-allowed;
}

.loading-spinner {
    width: 20px;
    height: 20px;
    border: 2px solid #ffffff;
    border-top: 2px solid transparent;
    border-radius: 50%;
    animation: spin 1s linear infinite;
    display: none;
}

@keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
}

.instructions {
    margin-top: 20px;
    padding: 15px;
    background: #f8f9fa;
    border-radius: 10px;
    border-left: 4px solid #007bff;
}

.instructions h3 {
    color: #007bff;
    margin-bottom: 10px;
}

.instructions ul {
    list-style-type: none;
    padding-left: 0;
}

.instructions li {
    padding: 5px 0;
    color: #666;
}

footer {
    text-align: center;
    margin-top: 20px;
    color: white;
    opacity: 0.8;
}

/* Mobile Responsive */
@media (max-width: 768px) {
    .container {
        padding: 10px;
    }
    
    header h1 {
        font-size: 2em;
    }
    
    .chat-container {
        padding: 20px;
    }
    
    .chat-messages {
        height: 300px;
    }
    
    .user-message {
        margin-left: 20px;
    }
    
    .bot-message {
        margin-right: 20px;
    }
}

/* Sinhala Font Support */
@font-face {
    font-family: 'Arial Unicode MS';
    src: local('Arial Unicode MS');
}

/* Scrollbar Styling */
.chat-messages::-webkit-scrollbar {
    width: 8px;
}

.chat-messages::-webkit-scrollbar-track {
    background: #f1f1f1;
    border-radius: 10px;
}

.chat-messages::-webkit-scrollbar-thumb {
    background: #007bff;
    border-radius: 10px;
}

.chat-messages::-webkit-scrollbar-thumb:hover {
    background: #0056b3;
}
├── script.js           # // Free Translation API - MyMemory Translation
async function translateText(text, sourceLang, targetLang) {
    try {
        const response = await fetch(
            `https://api.mymemory.translated.net/get?q=${encodeURIComponent(text)}&langpair=${sourceLang}|${targetLang}`
        );
        const data = await response.json();
        
        if (data.responseStatus === 200) {
            return data.responseData.translatedText;
        } else {
            throw new Error('Translation failed');
        }
    } catch (error) {
        console.error('Translation error:', error);
        return text; // Return original text if translation fails
    }
}

// Free AI API - Hugging Face Inference API (Free tier)
async function getAIResponse(message) {
    try {
        // Using a free model from Hugging Face
        const response = await fetch(
            'https://api-inference.huggingface.co/models/microsoft/DialoGPT-medium',
            {
                method: 'POST',
                headers: {
                    'Authorization': 'Bearer YOUR_HUGGING_FACE_TOKEN', // Free token from huggingface.co
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify({
                    inputs: message,
                    parameters: {
                        max_length: 150,
                        temperature: 0.7
                    }
                })
            }
        );
        
        const data = await response.json();
        
        if (data.error) {
            // Fallback to a simple rule-based response
            return getFallbackResponse(message);
        }
        
        return data.generated_text || "I'm sorry, I didn't understand that.";
        
    } catch (error) {
        console.error('AI API error:', error);
        return getFallbackResponse(message);
    }
}

// Fallback responses for when API fails
function getFallbackResponse(message) {
    const lowerMessage = message.toLowerCase();
    
    if (lowerMessage.includes('hello') || lowerMessage.includes('hi')) {
        return "Hello! How can I help you today?";
    } else if (lowerMessage.includes('how are you')) {
        return "I'm doing well, thank you! How can I assist you?";
    } else if (lowerMessage.includes('thank')) {
        return "You're welcome! Is there anything else I can help with?";
    } else {
        return "I understand you're saying: " + message + ". Can you tell me more?";
    }
}

// Main chat function
async function sendMessage() {
    const messageInput = document.getElementById('message-input');
    const sendBtn = document.getElementById('send-btn');
    const loadingSpinner = document.getElementById('loading-spinner');
    const chatMessages = document.getElementById('chat-messages');
    
    const message = messageInput.value.trim();
    
    if (!message) return;
    
    // Disable button and show loading
    sendBtn.disabled = true;
    loadingSpinner.style.display = 'block';
    sendBtn.querySelector('span').textContent = 'ප්‍රතිචාරය ලබාගැනීම...';
    
    // Add user message to chat
    addMessageToChat('user', message);
    messageInput.value = '';
    
    try {
        // Step 1: Sinhala to English translation
        const englishMessage = await translateText(message, 'si', 'en');
        
        // Step 2: Get AI response
        const englishResponse = await getAIResponse(englishMessage);
        
        // Step 3: English to Sinhala translation
        const sinhalaResponse = await translateText(englishResponse, 'en', 'si');
        
        // Add AI response to chat
        addMessageToChat('bot', sinhalaResponse);
        
    } catch (error) {
        console.error('Chat error:', error);
        addMessageToChat('bot', 'කණගාටුයි! දෝෂයක් ඇතිවිය. කරුණාකර යළි උත්සාහ කරන්න.');
    }
    
    // Re-enable button and hide loading
    sendBtn.disabled = false;
    loadingSpinner.style.display = 'none';
    sendBtn.querySelector('span').textContent = 'පණිවිඩය යවන්න';
}

// Add message to chat UI
function addMessageToChat(sender, message) {
    const chatMessages = document.getElementById('chat-messages');
    const messageDiv = document.createElement('div');
    
    messageDiv.className = `message ${sender}-message`;
    messageDiv.innerHTML = `<strong>${sender === 'user' ? 'ඔබ' : 'AI සහායකයා'}:</strong> ${message}`;
    
    chatMessages.appendChild(messageDiv);
    chatMessages.scrollTop = chatMessages.scrollHeight;
}

// Enter key support
document.getElementById('message-input').addEventListener('keypress', function(e) {
    if (e.key === 'Enter' && !e.shiftKey) {
        e.preventDefault();
        sendMessage();
    }
});

// Initialize with welcome message
document.addEventListener('DOMContentLoaded', function() {
    // Add any initialization code here
    console.log('සිංහල Dopple Chat initialized!');
});

// Service Worker for PWA features (optional)
if ('serviceWorker' in navigator) {
    window.addEventListener('load', function() {
        navigator.serviceWorker.register('/sw.js')
            .then(function(registration) {
                console.log('ServiceWorker registration successful');
            })
            .catch(function(error) {
                console.log('ServiceWorker registration failed: ', error);
            });
    });
}
└── README.md           # # සිංහල Dopple Chat

සිංහල භාෂාවෙන් AI සමග සංවාදයට හැකි වන නොමිලේ වෙබ් යෙදුමකි.

## Features
- සිංහල ටයිප් කිරීමේ හැකියාව
- ස්වයංක්‍රීය පරිවර්තනය (සිංහල ↔ English)
- AI-powered responses
- Mobile-friendly design
- 100% නොමිලේ

## How to Use
1. සිංහලෙන් ඔබේ ප්‍රශ්නය ටයිප් කරන්න
2. "පණිවිඩය යවන්න" බොත්තම ක්ලික් කරන්න
3. AI ප්‍රතිචාරය බලාපොරොත්තු වන්න

## Technologies Used
- HTML5, CSS3, JavaScript
- MyMemory Translation API
- Hugging Face AI API
- GitHub Pages & Netlify Hosting

## Live Demo
[(https://beta.dopple.ai/)]
