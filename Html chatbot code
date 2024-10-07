<!DOCTYPE html>
<html>
<head>
    <title>Student Chatbot</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
        }
        .chatbox {
            width: 400px;
            height: 500px;
            background-color: #fff;
            border-radius: 10px;
            padding: 20px;
            margin: 100px auto;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .chatbox textarea {
            width: 100%;
            height: 50px;
            border-radius: 5px;
            padding: 10px;
            border: 1px solid #ddd;
            margin-top: 20px;
        }
        .chatbox .chatlog {
            height: 380px;
            overflow-y: auto;
            border-bottom: 1px solid #ddd;
            padding-bottom: 20px;
        }
        .chatbox .chatlog p {
            margin: 10px 0;
        }
    </style>
</head>
<body>
    <div class="chatbox">
        <div class="chatlog" id="chatlog"></div>
        <textarea id="user_input" placeholder="Type your message here..."></textarea>
    </div>

    <script>
        const chatlog = document.getElementById('chatlog');
        const userInput = document.getElementById('user_input');

        userInput.addEventListener('keypress', function (e) {
            if (e.key === 'Enter') {
                const userText = userInput.value;
                appendMessage("You: " + userText);
                getBotResponse(userText);
                userInput.value = '';
            }
        });

        function appendMessage(message) {
            const p = document.createElement('p');
            p.textContent = message;
            chatlog.appendChild(p);
            chatlog.scrollTop = chatlog.scrollHeight;
        }

        function getBotResponse(userText) {
            const xhr = new XMLHttpRequest();
            xhr.open('GET', `/get?msg=${userText}`, true);
            xhr.onload = function () {
                if (xhr.status === 200) {
                    appendMessage("Bot: " + xhr.responseText);
                }
            };
            xhr.send();
        }
    </script>
</body>
</html>
