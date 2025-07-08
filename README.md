<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>iplicit quiz - know your finance solution</title>
    <style>
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            background: linear-gradient(135deg, #1e3a8a 0%, #f59e0b 100%);
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
            background: linear-gradient(90deg, #1e3a8a 0%, #f59e0b 100%);
        }
        .progress-bar {
            width: 100%;
            height: 8px;
            background: #f2f2f2;
            border-radius: 10px;
            margin-bottom: 30px;
            overflow: hidden;
        }
        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #1e3a8a 0%, #f59e0b 100%);
            transition: width 0.3s ease;
            border-radius: 10px;
        }
        .question-counter {
            color: #555;
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
            background: #fef3c7;
            border-color: #f59e0b;
            transform: translateY(-2px);
        }
        .option.correct {
            background: #dbeafe;
            border-color: #1e40af;
            color: #1e40af;
            font-weight: bold;
            position: relative;
        }
        .option.correct::before {
            content: '✓';
            position: absolute;
            right: 15px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 18px;
            font-weight: bold;
        }
        .option.incorrect {
            background: #fee2e2;
            border-color: #dc2626;
            color: #dc2626;
            font-weight: bold;
            position: relative;
        }
        .option.incorrect::before {
            content: '✗';
            position: absolute;
            right: 15px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 18px;
            font-weight: bold;
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
            border-left: 4px solid #1e40af;
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
            color: #555;
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
            background: linear-gradient(135deg, #1e3a8a 0%, #f59e0b 100%);
            color: white;
        }
        .cta-button.primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(30, 58, 138, 0.2);
        }
        .cta-button.secondary {
            background: white;
            color: #1e3a8a;
            border: 2px solid #1e3a8a;
        }
        .cta-button.secondary:hover {
            background: #1e3a8a;
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
            color: #1e3a8a;
            font-weight: 600;
        }
        .restart-button:hover {
            background: #f59e0b;
            color: #fff;
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
        // Quiz data
        const quizData = [
            {
                question: "What is a key functional advantage of iplicit's deferred revenue automation for UK mid-market finance teams?",
                options: [
                    "It requires manual journal entries each month",
                    "It automatically calculates revenue spread and automates monthly reversals and journals",
                    "It only works for simple revenue recognition",
                    "It requires separate spreadsheet management"
                ],
                correct: 1,
                explanation: "iplicit automatically calculates the spread of revenue based on your required time period and then automates the monthly process of reversals and journals to accurately recognise revenue in a compliant manner - eliminating hours of manual work each month."
            },
            {
                question: "Which specific UK compliance feature does iplicit automate?",
                options: [
                    "Annual company filings only",
                    "VAT returns with automatic submission to HMRC",
                    "Basic bookkeeping entries",
                    "Manual tax calculations"
                ],
                correct: 1,
                explanation: "iplicit automates VAT returns using tax codes, rates and tax systems to generate the figures needed for returns, and can automatically submit your return to HMRC - crucial for UK mid-market finance teams."
            },
            {
                question: "What labour-saving benefit does iplicit provide for UK mid-market finance teams?",
                options: [
                    "Reduces work by a few hours per month",
                    "Can save days of labour every month for medium-sized organizations",
                    "Only helps with basic data entry",
                    "Provides minimal time savings"
                ],
                correct: 1,
                explanation: "iplicit can save days of labour every month for finance teams of medium-sized organizations by automating laborious tasks like group consolidation, intercompany transactions, and multi-currency handling."
            },
            {
                question: "What makes iplicit particularly suitable for UK organizations with multiple entities?",
                options: [
                    "It requires separate systems for each entity",
                    "Real-time consolidation with single unified architecture where transactions are entered once",
                    "It only works for single-entity businesses",
                    "Manual consolidation processes"
                ],
                correct: 1,
                explanation: "iplicit's single unified architecture means transactions are only entered once and are automatically consolidated in real-time, perfect for UK mid-market organizations managing multiple entities and currencies."
            },
            {
                question: "What heritage gives iplicit particular credibility in the UK accounting software market?",
                options: [
                    "It's a new startup with no track record",
                    "Brought to you by the team that originally created Exchequer",
                    "It's based on international software",
                    "It's a basic cloud migration"
                ],
                correct: 1,
                explanation: "iplicit is brought to you by the team that originally created Exchequer, giving it deep UK accounting software heritage and understanding of the specific needs of UK mid-market finance teams."
            }
        ];

        let currentQuestion = 0;
        let score = 0;
        let answered = false;

        function startQuiz() {
            currentQuestion = 0;
            score = 0;
            answered = false;
            showQuestion();
        }

        function showQuestion() {
            const questionData = quizData[currentQuestion];
            const progressPercent = ((currentQuestion + 1) / quizData.length) * 100;
            
            document.getElementById('progress-fill').style.width = progressPercent + '%';
            document.getElementById('question-counter').textContent = `Question ${currentQuestion + 1} of ${quizData.length}`;
            document.getElementById('question').textContent = questionData.question;
            
            const optionsContainer = document.getElementById('options');
            optionsContainer.innerHTML = '';
            
            questionData.options.forEach((option, index) => {
                const optionElement = document.createElement('div');
                optionElement.className = 'option';
                optionElement.textContent = option;
                optionElement.addEventListener('click', () => selectAnswer(index));
                optionsContainer.appendChild(optionElement);
            });
            
            document.getElementById('explanation-container').innerHTML = '';
            answered = false;
        }

        function selectAnswer(selectedIndex) {
            if (answered) return;
            
            answered = true;
            const questionData = quizData[currentQuestion];
            const options = document.querySelectorAll('.option');
            
            options.forEach((option, index) => {
                option.classList.add('disabled');
                if (index === questionData.correct) {
                    option.classList.add('correct');
                } else if (index === selectedIndex) {
                    option.classList.add('incorrect');
                }
            });
            
            if (selectedIndex === questionData.correct) {
                score++;
            }
            
            showExplanation(questionData.explanation);
            
            setTimeout(() => {
                currentQuestion++;
                if (currentQuestion < quizData.length) {
                    showQuestion();
                } else {
                    showResults();
                }
            }, 3000);
        }

        function showExplanation(explanation) {
            const explanationContainer = document.getElementById('explanation-container');
            explanationContainer.innerHTML = `<div class="explanation">${explanation}</div>`;
        }

        function showResults() {
            const percentage = Math.round((score / quizData.length) * 100);
            let message = '';
            
            if (percentage >= 80) {
                message = 'Excellent! You really know your stuff!';
            } else if (percentage >= 60) {
                message = 'Good job! You have a solid understanding.';
            } else if (percentage >= 40) {
                message = 'Not bad! Keep learning and practicing.';
            } else {
                message = 'Keep studying! You\'ll get better with practice.';
            }
            
            document.getElementById('quiz-content').innerHTML = `
                <div class="score-screen">
                    <div class="score-title">Quiz Complete!</div>
                    <div class="score-subtitle">You scored ${score} out of ${quizData.length} (${percentage}%)</div>
                    <div class="score-subtitle">${message}</div>
                    <div class="cta-buttons">
                        <a href="https://www.iplicit.com/book-a-demo" class="cta-button primary">Book a Demo</a>
                        <a href="mailto:francesca.roach@iplicit.com?subject=Quiz%20Inquiry%20-%20iplicit%20Demo%20Request" class="cta-button secondary">Contact Francesca Roach</a>
                        <button class="cta-button primary" onclick="startQuiz()">Take Quiz Again</button>
                    </div>
                </div>
            `;
        }

        // Initialize the quiz when the page loads
        window.addEventListener('load', startQuiz);
    </script>
</body>
</html>
