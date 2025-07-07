<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Iplicit Finance Quiz</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .quiz-container {
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            max-width: 600px;
            width: 100%;
            padding: 40px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .quiz-container::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 6px;
            background: linear-gradient(90deg, #667eea, #764ba2);
        }

        .progress-bar {
            width: 100%;
            height: 8px;
            background: #e5e7eb;
            border-radius: 10px;
            margin-bottom: 30px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #667eea, #764ba2);
            transition: width 0.3s ease;
            border-radius: 10px;
        }

        .question-counter {
            color: #6b7280;
            font-size: 14px;
            margin-bottom: 20px;
        }

        .question {
            font-size: 24px;
            font-weight: 600;
            color: #1f2937;
            margin-bottom: 30px;
            line-height: 1.4;
        }

        .options {
            display: grid;
            gap: 15px;
            margin-bottom: 30px;
        }

        .option {
            padding: 20px;
            border: 2px solid #e5e7eb;
            border-radius: 15px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 16px;
            text-align: left;
            background: white;
        }

        .option:hover {
            background: #f9fafb;
            border-color: #667eea;
            transform: translateY(-2px);
        }

        .option.correct {
            background: #dcfce7;
            border-color: #16a34a;
            color: #15803d;
        }

        .option.incorrect {
            background: #fef2f2;
            border-color: #dc2626;
            color: #dc2626;
        }

        .option.disabled {
            opacity: 0.6;
            cursor: not-allowed;
        }

        .option.disabled:hover {
            transform: none;
        }

        .explanation {
            background: #f0f9ff;
            border-left: 4px solid #0ea5e9;
            padding: 20px;
            margin: 20px 0;
            border-radius: 0 10px 10px 0;
            text-align: left;
            opacity: 0;
            animation: fadeIn 0.5s ease forwards;
        }

        .explanation::before {
            content: '💡 ';
            font-size: 18px;
        }

        .score-screen {
            text-align: center;
        }

        .score-title {
            font-size: 32px;
            font-weight: 700;
            color: #1f2937;
            margin-bottom: 20px;
        }

        .score-subtitle {
            font-size: 18px;
            color: #6b7280;
            margin-bottom: 40px;
        }

        .cta-buttons {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .cta-button {
            padding: 15px 30px;
            border: none;
            border-radius: 10px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
        }

        .cta-button.primary {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }

        .cta-button.primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(102, 126, 234, 0.3);
        }

        .cta-button.secondary {
            background: white;
            color: #667eea;
            border: 2px solid #667eea;
        }

        .cta-button.secondary:hover {
            background: #667eea;
            color: white;
            transform: translateY(-2px);
        }

        .restart-button {
            margin-top: 20px;
            padding: 10px 20px;
            background: #f3f4f6;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 14px;
            color: #6b7280;
        }

        .restart-button:hover {
            background: #e5e7eb;
        }

        @keyframes fadeIn {
            to { opacity: 1; }
        }

        @media (max-width: 640px) {
            .quiz-container {
                padding: 30px 20px;
            }
            
            .question {
                font-size: 20px;
            }
            
            .option {
                padding: 15px;
            }
        }
    </style>
</head>
<body>
    <div class="quiz-container">
        <div id="quiz-content">
            <div class="progress-bar">
                <div class="progress-fill" id="progress-fill"></div>
            </div>
            <div class="question-counter" id="question-counter">Question 1 of 5</div>
            <div class="question" id="question">Loading...</div>
            <div class="options" id="options"></div>
            <div id="explanation-container"></div>
        </div>
    </div>

    <script>
        const quizData = [
            {
                question: "What makes iplicit different from legacy on-premise finance systems?",
                options: [
                    "It's cheaper to install",
                    "It's only for large enterprises",
                    "It's cloud-native and designed for growing organisations",
                    "It doesn't require accounting knowledge",
                ],
                correctIndex: 2,
                explanation: "iplicit is a true-cloud finance solution designed for mid-sized organisations that have outgrown entry-level software.",
            },
            {
                question: "Which of these is a key benefit of iplicit's powerful reporting engine?",
                options: [
                    "Reports only work in Excel",
                    "Real-time insights with multi-dimensional analysis",
                    "Only available at year-end",
                    "It requires coding knowledge",
                ],
                correctIndex: 1,
                explanation: "iplicit enables live, detailed reporting across departments, dimensions, and entities—without needing tech skills.",
            },
            {
                question: "What makes iplicit ideal for multi-entity organisations?",
                options: [
                    "Every entity needs a separate login",
                    "Consolidation across entities is built-in and instant",
                    "It uses blockchain",
                    "It only supports UK accounts",
                ],
                correctIndex: 1,
                explanation: "iplicit simplifies consolidations with automatic intercompany elimination and real-time group-level reporting.",
            },
            {
                question: "How does iplicit help reduce reliance on spreadsheets?",
                options: [
                    "It converts them into charts",
                    "Built-in automation removes manual processes",
                    "It uploads spreadsheets to SharePoint",
                    "It creates AI-powered Excel macros",
                ],
                correctIndex: 1,
                explanation: "By automating workflows and reporting, iplicit removes the need for spreadsheet workarounds.",
            },
            {
                question: "Which feature helps iplicit users adapt to changing regulations or needs?",
                options: [
                    "Built-in WhatsApp support",
                    "No-code configuration and flexible approval workflows",
                    "AI predicts new laws",
                    "Monthly audits by robots",
                ],
                correctIndex: 1,
                explanation: "iplicit's adaptable configuration options mean it evolves with your organisation and compliance needs.",
            },
        ];

        let currentQuestion = 0;
        let score = 0;
        let selectedAnswer = null;
        let isAnswered = false;

        function updateProgress() {
            const progressFill = document.getElementById('progress-fill');
            const progress = ((currentQuestion + 1) / quizData.length) * 100;
            progressFill.style.width = progress + '%';
        }

        function displayQuestion() {
            const questionElement = document.getElementById('question');
            const optionsElement = document.getElementById('options');
            const questionCounter = document.getElementById('question-counter');
            const explanationContainer = document.getElementById('explanation-container');

            questionCounter.textContent = `Question ${currentQuestion + 1} of ${quizData.length}`;
            questionElement.textContent = quizData[currentQuestion].question;
            
            optionsElement.innerHTML = '';
            explanationContainer.innerHTML = '';
            
            quizData[currentQuestion].options.forEach((option, index) => {
                const optionElement = document.createElement('div');
                optionElement.className = 'option';
                optionElement.textContent = option;
                optionElement.onclick = () => selectAnswer(index);
                optionsElement.appendChild(optionElement);
            });

            updateProgress();
            isAnswered = false;
            selectedAnswer = null;
        }

        function selectAnswer(index) {
            if (isAnswered) return;

            isAnswered = true;
            selectedAnswer = index;
            const options = document.querySelectorAll('.option');
            const correctIndex = quizData[currentQuestion].correctIndex;

            options.forEach((option, i) => {
                option.classList.add('disabled');
                if (i === correctIndex) {
                    option.classList.add('correct');
                } else if (i === selectedAnswer) {
                    option.classList.add('incorrect');
                }
            });

            if (selectedAnswer === correctIndex) {
                score++;
            }

            // Show explanation
            const explanationContainer = document.getElementById('explanation-container');
            const explanationElement = document.createElement('div');
            explanationElement.className = 'explanation';
            explanationElement.textContent = quizData[currentQuestion].explanation;
            explanationContainer.appendChild(explanationElement);

            // Move to next question after delay
            setTimeout(() => {
                if (currentQuestion < quizData.length - 1) {
                    currentQuestion++;
                    displayQuestion();
                } else {
                    showResults();
                }
            }, 2500);
        }

        function showResults() {
            const quizContent = document.getElementById('quiz-content');
            const percentage = Math.round((score / quizData.length) * 100);
            
            let emoji = '🎉';
            if (percentage < 50) emoji = '😅';
            else if (percentage < 80) emoji = '👍';
            
            quizContent.innerHTML = `
                <div class="score-screen">
                    <div class="score-title">${emoji} You scored ${score} out of ${quizData.length}!</div>
                    <div class="score-subtitle">That's ${percentage}% correct! Want to learn more about how iplicit can transform your finance function?</div>
                    <div class="cta-buttons">
                        <a href="https://www.iplicit.com/quick-tour?utm_content=337329471&utm_medium=social&utm_source=linkedin&hss_channel=lcp-10141131" target="_blank" class="cta-button primary">
                            🚀 Take the Quick Tour
                        </a>
                        <a href="mailto:francesca.roach@iplicit.com" class="cta-button secondary">
                            📧 Email: francesca.roach@iplicit.com
                        </a>
                    </div>
                    <button class="restart-button" onclick="restartQuiz()">🔄 Take Quiz Again</button>
                </div>
            `;
        }

        function restartQuiz() {
            currentQuestion = 0;
            score = 0;
            selectedAnswer = null;
            isAnswered = false;
            
            const quizContent = document.getElementById('quiz-content');
            quizContent.innerHTML = `
                <div class="progress-bar">
                    <div class="progress-fill" id="progress-fill"></div>
                </div>
                <div class="question-counter" id="question-counter">Question 1 of 5</div>
                <div class="question" id="question">Loading...</div>
                <div class="options" id="options"></div>
                <div id="explanation-container"></div>
            `;
            
            displayQuestion();
        }

        // Initialize the quiz
        displayQuestion();
    </script>
</body>
</html>
