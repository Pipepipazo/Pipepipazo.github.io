<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive English Learning</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
        /* Custom scrollbar for better aesthetics */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f1f1;
            border-radius: 10px;
        }
        ::-webkit-scrollbar-thumb {
            background: #888;
            border-radius: 10px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #555;
        }
    </style>
</head>
<body class="bg-gradient-to-br from-blue-100 to-purple-100 min-h-screen flex flex-col items-center p-4">

    <div class="container bg-white rounded-xl shadow-2xl p-6 md:p-10 max-w-4xl w-full my-8">
        <!-- Header Section -->
        <header class="text-center mb-10">
            <h1 class="text-5xl md:text-6xl font-extrabold text-blue-800 mb-4 animate-fade-in-down">
                Learn English Playing!
            </h1>
            <p class="text-xl text-gray-600">
                Improve your irregular verbs and phrasal verbs interactively.
            </p>
            <p class="text-sm text-gray-400 italic mt-2">
                Pipe es una chima!
            </p>
        </header>

        <!-- Navigation Tabs -->
        <nav class="flex justify-center mb-8">
            <button id="tab-quiz" class="tab-button bg-blue-600 text-white px-6 py-3 rounded-l-lg text-lg font-semibold shadow-md hover:bg-blue-700 transition-colors duration-300">
                Irregular Verbs
            </button>
            <button id="tab-phrasal-verbs" class="tab-button bg-gray-300 text-gray-800 px-6 py-3 text-lg font-semibold shadow-md hover:bg-gray-400 transition-colors duration-300">
                Phrasal Verbs List
            </button>
            <button id="tab-fill-in-blanks" class="tab-button bg-gray-300 text-gray-800 px-6 py-3 text-lg font-semibold shadow-md hover:bg-gray-400 transition-colors duration-300">
                Fill in the Blanks
            </button>
            <button id="tab-phrasal-verb-quiz" class="tab-button bg-gray-300 text-gray-800 px-6 py-3 rounded-r-lg text-lg font-semibold shadow-md hover:bg-gray-400 transition-colors duration-300">
                Phrasal Verbs Quiz
            </button>
        </nav>

        <!-- Quiz Section (Irregular Verbs) -->
        <section id="quiz-section" class="tab-content">
            <h2 class="text-3xl font-bold text-blue-700 mb-6 text-center">Irregular Verbs Game</h2>
            <div id="quiz-container" class="bg-blue-50 p-6 rounded-lg shadow-inner">
                <div id="question-display" class="text-2xl font-semibold text-gray-800 mb-6 text-center">
                    Loading question...
                </div>
                <div id="answer-options" class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-6">
                    <!-- Answer buttons will be dynamically inserted here -->
                </div>
                <div id="feedback-message" class="text-center text-lg font-medium mb-4 min-h-[2rem]">
                    <!-- Feedback messages appear here -->
                </div>
                <div id="hint-display" class="text-center text-sm text-gray-500 italic mb-6 min-h-[1.5rem]">
                    <!-- Hint will appear here -->
                </div>
                <div class="flex justify-center space-x-4">
                    <button id="show-hint-button" class="bg-yellow-500 text-white px-6 py-3 rounded-full text-lg font-semibold shadow-md hover:bg-yellow-600 transition-colors duration-300">
                        Show Hint
                    </button>
                    <button id="next-question-button" class="bg-green-600 text-white px-6 py-3 rounded-full text-lg font-semibold shadow-md hover:bg-green-700 transition-colors duration-300 hidden">
                        Next Question
                    </button>
                    <button id="restart-quiz-button" class="bg-red-500 text-white px-6 py-3 rounded-full text-lg font-semibold shadow-md hover:bg-red-600 transition-colors duration-300 hidden">
                        Restart Quiz
                    </button>
                </div>
            </div>
        </section>

        <!-- Phrasal Verbs List Section -->
        <section id="phrasal-verbs-section" class="tab-content hidden">
            <h2 class="text-3xl font-bold text-purple-700 mb-6 text-center">Learn Phrasal Verbs</h2>
            <div class="bg-purple-50 p-6 rounded-lg shadow-inner">
                <p class="text-gray-700 mb-6 text-center">
                    A phrasal verb is a combination of a verb and a preposition or adverb (or both) that together create a new meaning. Explore some of the most common ones!
                </p>
                <div id="phrasal-verbs-list" class="space-y-4">
                    <!-- Phrasal verbs will be dynamically inserted here -->
                </div>
            </div>
        </section>

        <!-- Fill in the Blanks Section -->
        <section id="fill-in-blanks-section" class="tab-content hidden">
            <h2 class="text-3xl font-bold text-teal-700 mb-6 text-center">Phrasal Verbs: Fill in the Blanks</h2>
            <div id="fill-in-blanks-container" class="bg-teal-50 p-6 rounded-lg shadow-inner">
                <div id="fib-question-display" class="text-2xl font-semibold text-gray-800 mb-6 text-center">
                    Loading question...
                </div>
                <div id="fib-answer-options" class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-6">
                    <!-- Answer buttons will be dynamically inserted here -->
                </div>
                <div id="fib-feedback-message" class="text-center text-lg font-medium mb-4 min-h-[2rem]">
                    <!-- Feedback messages appear here -->
                </div>
                <div id="fib-hint-display" class="text-center text-sm text-gray-500 italic mb-6 min-h-[1.5rem]">
                    <!-- Hint will appear here -->
                </div>
                <div class="flex justify-center space-x-4">
                    <button id="fib-show-hint-button" class="bg-yellow-500 text-white px-6 py-3 rounded-full text-lg font-semibold shadow-md hover:bg-yellow-600 transition-colors duration-300">
                        Show Hint
                    </button>
                    <button id="fib-next-question-button" class="bg-green-600 text-white px-6 py-3 rounded-full text-lg font-semibold shadow-md hover:bg-green-700 transition-colors duration-300 hidden">
                        Next Question
                    </button>
                    <button id="fib-restart-quiz-button" class="bg-red-500 text-white px-6 py-3 rounded-full text-lg font-semibold shadow-md hover:bg-red-600 transition-colors duration-300 hidden">
                        Restart Game
                    </button>
                </div>
            </div>
        </section>

        <!-- Phrasal Verbs Quiz Section -->
        <section id="phrasal-verb-quiz-section" class="tab-content hidden">
            <h2 class="text-3xl font-bold text-pink-700 mb-6 text-center">Phrasal Verbs Quiz</h2>
            <div id="phrasal-verb-quiz-container" class="bg-pink-50 p-6 rounded-lg shadow-inner">
                <div id="pv-quiz-question-display" class="text-2xl font-semibold text-gray-800 mb-6 text-center">
                    Loading question...
                </div>
                <div id="pv-quiz-image-display" class="mb-6 flex justify-center">
                    <!-- Image for phrasal verb quiz will be inserted here -->
                </div>
                <div id="pv-quiz-answer-options" class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-6">
                    <!-- Answer buttons will be dynamically inserted here -->
                </div>
                <div id="pv-quiz-feedback-message" class="text-center text-lg font-medium mb-4 min-h-[2rem]">
                    <!-- Feedback messages appear here -->
                </div>
                <div id="pv-quiz-hint-display" class="text-center text-sm text-gray-500 italic mb-6 min-h-[1.5rem]">
                    <!-- Hint will appear here -->
                </div>
                <div class="flex justify-center space-x-4">
                    <button id="pv-quiz-show-hint-button" class="bg-yellow-500 text-white px-6 py-3 rounded-full text-lg font-semibold shadow-md hover:bg-yellow-600 transition-colors duration-300">
                        Show Hint
                    </button>
                    <button id="pv-quiz-next-question-button" class="bg-green-600 text-white px-6 py-3 rounded-full text-lg font-semibold shadow-md hover:bg-green-700 transition-colors duration-300 hidden">
                        Next Question
                    </button>
                    <button id="pv-quiz-restart-quiz-button" class="bg-red-500 text-white px-6 py-3 rounded-full text-lg font-semibold shadow-md hover:bg-red-600 transition-colors duration-300 hidden">
                        Restart Quiz
                    </button>
                </div>
            </div>
        </section>
    </div>

    <script>
        // Quiz data for Irregular Verbs
        const allIrregularVerbs = [
            {
                "question": "What is the simple past and past participle form of the verb 'be'?",
                "answerOptions": [
                    { "text": "was/were, been", "isCorrect": true, "rationale": "Correct. 'Was' (singular) and 'were' (plural) are the simple past forms, and 'been' is the past participle." },
                    { "text": "beed, beed", "isCorrect": false, "rationale": "This verb is highly irregular and does not follow the regular '-ed' pattern." },
                    { "text": "is, are", "isCorrect": false, "rationale": "These are present tense forms, not past tense." },
                    { "text": "being, be", "isCorrect": false, "rationale": "These are present participle and base forms, not simple past or past participle." }
                ],
                "hint": "This is the most common and irregular verb in English."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'have'?",
                "answerOptions": [
                    { "text": "had, had", "isCorrect": true, "rationale": "Correct. 'Had' serves as both the simple past and past participle for 'have'." },
                    { "text": "haved, haved", "isCorrect": false, "rationale": "This verb is irregular and does not take the '-ed' ending." },
                    { "text": "has, having", "isCorrect": false, "rationale": "These are present tense and present participle forms, not past tense." },
                    { "text": "have, had", "isCorrect": false, "rationale": "The simple past is 'had', and the past participle is also 'had'." }
                ],
                "hint": "This verb is crucial for forming perfect tenses."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'do'?",
                "answerOptions": [
                    { "text": "did, done", "isCorrect": true, "rationale": "Correct. 'Did' is the simple past and 'done' is the past participle of 'do'." },
                    { "text": "doed, doed", "isCorrect": false, "rationale": "This verb is irregular and does not take the '-ed' ending." },
                    { "text": "does, doing", "isCorrect": false, "rationale": "These are present tense and present participle forms." },
                    { "text": "done, did", "isCorrect": false, "rationale": "The order of the forms is inverted." }
                ],
                "hint": "Think about completing an action in the past."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'say'?",
                "answerOptions": [
                    { "text": "said, said", "isCorrect": true, "rationale": "Correct. 'Said' is both the simple past and past participle of 'say'." },
                    { "text": "sayed, sayed", "isCorrect": false, "rationale": "This verb is irregular and does not take the '-ed' ending." },
                    { "text": "says, saying", "isCorrect": false, "rationale": "These are present tense and present participle forms." },
                    { "text": "say, said", "isCorrect": false, "rationale": "The simple past is 'said', and the past participle is also 'said'." }
                ],
                "hint": "This verb is about speaking words."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'go'?",
                "answerOptions": [
                    { "text": "went, gone", "isCorrect": true, "rationale": "Correct. 'Went' is the simple past and 'gone' is the past participle of 'go'." },
                    { "text": "goed, goed", "isCorrect": false, "rationale": "This verb is irregular and does not form its past by adding '-ed'." },
                    { "text": "go, gone", "isCorrect": false, "rationale": "The simple past of 'go' is 'went', not 'go'." },
                    { "text": "gone, went", "isCorrect": false, "rationale": "The order of the forms is inverted." }
                ],
                "hint": "This is one of the most common irregular verbs."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'get'?",
                "answerOptions": [
                    { "text": "got, gotten/got", "isCorrect": true, "rationale": "Correct. 'Got' is the simple past. Both 'gotten' (American English) and 'got' (British English) are acceptable past participles." },
                    { "text": "getted, getted", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "get, got", "isCorrect": false, "rationale": "The past participle is 'gotten' or 'got'." },
                    { "text": "gotten, got", "isCorrect": false, "rationale": "The simple past is 'got'." }
                ],
                "hint": "This verb has two common past participle forms depending on the dialect."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'make'?",
                "answerOptions": [
                    { "text": "made, made", "isCorrect": true, "rationale": "Correct. 'Made' is both the simple past and past participle of 'make'." },
                    { "text": "maked, maked", "isCorrect": false, "rationale": "This verb is irregular and does not form its past by adding '-ed'." },
                    { "text": "make, made", "isCorrect": false, "rationale": "The simple past of 'make' is 'made', not 'make'." },
                    { "text": "made, make", "isCorrect": false, "rationale": "The order of the forms is inverted." }
                ],
                "hint": "This verb is used for creating or producing something."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'know'?",
                "answerOptions": [
                    { "text": "knew, known", "isCorrect": true, "rationale": "Correct. 'Knew' is the simple past and 'known' is the past participle of 'know'." },
                    { "text": "knowed, knowed", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "know, knew", "isCorrect": false, "rationale": "The past participle is 'known'." },
                    { "text": "known, knew", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to have information or understanding."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'think'?",
                "answerOptions": [
                    { "text": "thought, thought", "isCorrect": true, "rationale": "Correct. 'Thought' is both the simple past and past participle of 'think'." },
                    { "text": "thinked, thinked", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "think, thought", "isCorrect": false, "rationale": "The simple past is 'thought'." },
                    { "text": "thought, think", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb relates to mental processes."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'take'?",
                "answerOptions": [
                    { "text": "took, taken", "isCorrect": true, "rationale": "Correct. 'Took' is the simple past and 'taken' is the past participle of 'take'." },
                    { "text": "taked, taked", "isCorrect": false, "rationale": "This verb is irregular and does not form its past by adding '-ed'." },
                    { "text": "take, took", "isCorrect": false, "rationale": "The past participle of 'take' is 'taken', not 'took'." },
                    { "text": "taken, took", "isCorrect": false, "rationale": "The order of the forms is inverted." }
                ],
                "hint": "This verb is used for actions like 'to grab' or 'to carry'."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'see'?",
                "answerOptions": [
                    { "text": "saw, seen", "isCorrect": true, "rationale": "Correct. 'Saw' is the simple past and 'seen' is the past participle of 'see'." },
                    { "text": "seed, seed", "isCorrect": false, "rationale": "This verb is irregular and does not form its past by adding '-ed'." },
                    { "text": "see, saw", "isCorrect": false, "rationale": "The past participle of 'see' is 'seen', not 'saw'." },
                    { "text": "seen, saw", "isCorrect": false, "rationale": "The order of the forms is inverted." }
                ],
                "hint": "Think about what you did when you observed something in the past."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'come'?",
                "answerOptions": [
                    { "text": "came, come", "isCorrect": true, "rationale": "Correct. 'Came' is the simple past and 'come' is the past participle of 'come'." },
                    { "text": "comed, comed", "isCorrect": false, "rationale": "This verb is irregular and does not form its past by adding '-ed'." },
                    { "text": "come, came", "isCorrect": false, "rationale": "The order of the forms is inverted." },
                    { "text": "came, came", "isCorrect": false, "rationale": "The past participle of 'come' is 'come', not 'came'." }
                ],
                "hint": "This verb's past participle is the same as its base form."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'give'?",
                "answerOptions": [
                    { "text": "gave, given", "isCorrect": true, "rationale": "Correct. 'Gave' is the simple past and 'given' is the past participle of 'give'." },
                    { "text": "gived, gived", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "give, gave", "isCorrect": false, "rationale": "The past participle is 'given'." },
                    { "text": "given, gave", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to hand over something."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'find'?",
                "answerOptions": [
                    { "text": "found, found", "isCorrect": true, "rationale": "Correct. 'Found' is both the simple past and past participle of 'find'." },
                    { "text": "finded, finded", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "find, found", "isCorrect": false, "rationale": "The simple past is 'found'." },
                    { "text": "found, find", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to discover something."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'tell'?",
                "answerOptions": [
                    { "text": "told, told", "isCorrect": true, "rationale": "Correct. 'Told' is both the simple past and past participle of 'tell'." },
                    { "text": "telled, telled", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "tell, told", "isCorrect": false, "rationale": "The simple past is 'told'." },
                    { "text": "told, tell", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to communicate information to someone."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'write'?",
                "answerOptions": [
                    { "text": "wrote, written", "isCorrect": true, "rationale": "Correct. 'Wrote' is the simple past and 'written' is the past participle of 'write'." },
                    { "text": "writed, writed", "isCorrect": false, "rationale": "This verb is irregular and does not form its past by adding '-ed'." },
                    { "text": "write, wrote", "isCorrect": false, "rationale": "The past participle of 'write' is 'written', not 'wrote'." },
                    { "text": "written, wrote", "isCorrect": false, "rationale": "The order of the forms is inverted." }
                ],
                "hint": "Think about the action of putting words on paper."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'eat'?",
                "answerOptions": [
                    { "text": "ate, eaten", "isCorrect": true, "rationale": "Correct. 'Ate' is the simple past and 'eaten' is the past participle of 'eat'." },
                    { "text": "eated, eated", "isCorrect": false, "rationale": "This verb is irregular and does not form its past by adding '-ed'." },
                    { "text": "eat, eaten", "isCorrect": false, "rationale": "The simple past of 'eat' is 'ate', not 'eat'." },
                    { "text": "eaten, ate", "isCorrect": false, "rationale": "The order of the forms is inverted." }
                ],
                "hint": "Think about what you did after finishing your meal yesterday."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'run'?",
                "answerOptions": [
                    { "text": "ran, run", "isCorrect": true, "rationale": "Correct. This is a special case where the past participle ('run') returns to the infinitive form." },
                    { "text": "runned, runned", "isCorrect": false, "rationale": "As an irregular verb, it does not end in '-ed' to form the past." },
                    { "text": "ran, ran", "isCorrect": false, "rationale": "Although the simple past is 'ran', the past participle is different." },
                    { "text": "run, ran", "isCorrect": false, "rationale": "You have inverted the order of the verb forms." }
                ],
                "hint": "This verb is a bit tricky because its past participle is identical to its base form."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'bring'?",
                "answerOptions": [
                    { "text": "brought, brought", "isCorrect": true, "rationale": "Correct. 'Brought' is both the simple past and past participle of 'bring'." },
                    { "text": "bringed, bringed", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "bring, brought", "isCorrect": false, "rationale": "The simple past is 'brought'." },
                    { "text": "brought, bring", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to carry something to a place."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'buy'?",
                "answerOptions": [
                    { "text": "bought, bought", "isCorrect": true, "rationale": "Correct. 'Bought' is both the simple past and past participle of 'buy'." },
                    { "text": "buyed, buyed", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "buy, bought", "isCorrect": false, "rationale": "The simple past is 'bought'." },
                    { "text": "bought, buy", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to acquire something by paying money."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'build'?",
                "answerOptions": [
                    { "text": "built, built", "isCorrect": true, "rationale": "Correct. 'Built' is both the simple past and past participle of 'build'." },
                    { "text": "builded, builded", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "build, built", "isCorrect": false, "rationale": "The simple past is 'built'." },
                    { "text": "built, build", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to construct something."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'cut'?",
                "answerOptions": [
                    { "text": "cut, cut", "isCorrect": true, "rationale": "Correct. 'Cut' remains the same in all three forms." },
                    { "text": "cutted, cutted", "isCorrect": false, "rationale": "This verb is irregular and does not change form." },
                    { "text": "cut, cutted", "isCorrect": false, "rationale": "The past participle is also 'cut'." },
                    { "text": "cutted, cut", "isCorrect": false, "rationale": "The order is inverted, and the forms are incorrect." }
                ],
                "hint": "This verb is one of those rare cases where all three forms are identical."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'draw'?",
                "answerOptions": [
                    { "text": "drew, drawn", "isCorrect": true, "rationale": "Correct. 'Drew' is the simple past and 'drawn' is the past participle of 'draw'." },
                    { "text": "drawed, drawed", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "draw, drew", "isCorrect": false, "rationale": "The past participle is 'drawn'." },
                    { "text": "drawn, drew", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to create a picture with a pen or pencil."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'drink'?",
                "answerOptions": [
                    { "text": "drank, drunk", "isCorrect": true, "rationale": "Correct. 'Drank' is the simple past and 'drunk' is the past participle of 'drink'." },
                    { "text": "drinked, drinked", "isCorrect": false, "rationale": "This verb is irregular and does not form its past by adding '-ed'." },
                    { "text": "drink, drank", "isCorrect": false, "rationale": "The past participle of 'drink' is 'drunk', not 'drank'." },
                    { "text": "drunk, drank", "isCorrect": false, "rationale": "The order of the forms is inverted." }
                ],
                "hint": "Think about consuming a beverage."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'fall'?",
                "answerOptions": [
                    { "text": "fell, fallen", "isCorrect": true, "rationale": "Correct. 'Fell' is the simple past and 'fallen' is the past participle of 'fall'." },
                    { "text": "falled, falled", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "fall, fell", "isCorrect": false, "rationale": "The past participle is 'fallen'." },
                    { "text": "fallen, fell", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to drop down suddenly."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'feed'?",
                "answerOptions": [
                    { "text": "fed, fed", "isCorrect": true, "rationale": "Correct. 'Fed' is both the simple past and past participle of 'feed'." },
                    { "text": "feeded, feeded", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "feed, fed", "isCorrect": false, "rationale": "The simple past is 'fed'." },
                    { "text": "fed, feed", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to give food to someone or something."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'fight'?",
                "answerOptions": [
                    { "text": "fought, fought", "isCorrect": true, "rationale": "Correct. 'Fought' is both the simple past and past participle of 'fight'." },
                    { "text": "fighted, fighted", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "fight, fought", "isCorrect": false, "rationale": "The simple past is 'fought'." },
                    { "text": "fought, fight", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to engage in a struggle or conflict."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'forget'?",
                "answerOptions": [
                    { "text": "forgot, forgotten/forgot", "isCorrect": true, "rationale": "Correct. 'Forgot' is the simple past. Both 'forgotten' (common) and 'forgot' (less common) are past participles." },
                    { "text": "forgetted, forgetted", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "forget, forgot", "isCorrect": false, "rationale": "The past participle is 'forgotten' or 'forgot'." },
                    { "text": "forgotten, forgot", "isCorrect": false, "rationale": "The simple past is 'forgot'." }
                ],
                "hint": "This verb means to fail to remember."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'hear'?",
                "answerOptions": [
                    { "text": "heard, heard", "isCorrect": true, "rationale": "Correct. 'Heard' is both the simple past and past participle of 'hear'." },
                    { "text": "heared, heared", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "hear, heard", "isCorrect": false, "rationale": "The simple past is 'heard'." },
                    { "text": "heard, hear", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to perceive sound with your ears."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'hold'?",
                "answerOptions": [
                    { "text": "held, held", "isCorrect": true, "rationale": "Correct. 'Held' is both the simple past and past participle of 'hold'." },
                    { "text": "holded, holded", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "hold, held", "isCorrect": false, "rationale": "The simple past is 'held'." },
                    { "text": "held, hold", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to grasp or keep something."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'keep'?",
                "answerOptions": [
                    { "text": "kept, kept", "isCorrect": true, "rationale": "Correct. 'Kept' is both the simple past and past participle of 'keep'." },
                    { "text": "keeped, keeped", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "keep, kept", "isCorrect": false, "rationale": "The simple past is 'kept'." },
                    { "text": "kept, keep", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to retain possession of something."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'leave'?",
                "answerOptions": [
                    { "text": "left, left", "isCorrect": true, "rationale": "Correct. 'Left' is both the simple past and past participle of 'leave'." },
                    { "text": "leaved, leaved", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "leave, left", "isCorrect": false, "rationale": "The simple past is 'left'." },
                    { "text": "left, leave", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to go away from a place."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'lose'?",
                "answerOptions": [
                    { "text": "lost, lost", "isCorrect": true, "rationale": "Correct. 'Lost' is both the simple past and past participle of 'lose'." },
                    { "text": "loosed, loosed", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "lose, lost", "isCorrect": false, "rationale": "The simple past is 'lost'." },
                    { "text": "lost, lose", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to misplace something or to be defeated."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'meet'?",
                "answerOptions": [
                    { "text": "met, met", "isCorrect": true, "rationale": "Correct. 'Met' is both the simple past and past participle of 'meet'." },
                    { "text": "meeted, meeted", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "meet, met", "isCorrect": false, "rationale": "The simple past is 'met'." },
                    { "text": "met, meet", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to encounter someone or something."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'pay'?",
                "answerOptions": [
                    { "text": "paid, paid", "isCorrect": true, "rationale": "Correct. 'Paid' is both the simple past and past participle of 'pay'." },
                    { "text": "payed, payed", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "pay, paid", "isCorrect": false, "rationale": "The simple past is 'paid'." },
                    { "text": "paid, pay", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to give money for something."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'read'?",
                "answerOptions": [
                    { "text": "read, read", "isCorrect": true, "rationale": "Correct. The forms of 'read' are the same, though the pronunciation changes." },
                    { "text": "readed, readed", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "read, red", "isCorrect": false, "rationale": "The spelling is the same for all forms." },
                    { "text": "red, read", "isCorrect": false, "rationale": "The order is inverted, and the spelling is consistent." }
                ],
                "hint": "The spelling remains the same for all three forms, but the pronunciation changes for the past forms."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'run'?",
                "answerOptions": [
                    { "text": "ran, run", "isCorrect": true, "rationale": "Correct. This is a special case where the past participle ('run') returns to the infinitive form." },
                    { "text": "runned, runned", "isCorrect": false, "rationale": "As an irregular verb, it does not end in '-ed' to form the past." },
                    { "text": "ran, ran", "isCorrect": false, "rationale": "Although the simple past is 'ran', the past participle is different." },
                    { "text": "run, ran", "isCorrect": false, "rationale": "You have inverted the order of the verb forms." }
                ],
                "hint": "This verb is a bit tricky because its past participle is identical to its base form."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'say'?",
                "answerOptions": [
                    { "text": "said, said", "isCorrect": true, "rationale": "Correct. 'Said' is both the simple past and past participle of 'say'." },
                    { "text": "sayed, sayed", "isCorrect": false, "rationale": "This verb is irregular and does not take the '-ed' ending." },
                    { "text": "says, saying", "isCorrect": false, "rationale": "These are present tense and present participle forms." },
                    { "text": "say, said", "isCorrect": false, "rationale": "The simple past is 'said', and the past participle is also 'said'." }
                ],
                "hint": "This verb is about speaking words."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'sell'?",
                "answerOptions": [
                    { "text": "sold, sold", "isCorrect": true, "rationale": "Correct. 'Sold' is both the simple past and past participle of 'sell'." },
                    { "text": "selled, selled", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "sell, sold", "isCorrect": false, "rationale": "The simple past is 'sold'." },
                    { "text": "sold, sell", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to exchange something for money."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'send'?",
                "answerOptions": [
                    { "text": "sent, sent", "isCorrect": true, "rationale": "Correct. 'Sent' is both the simple past and past participle of 'send'." },
                    { "text": "sended, sended", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "send, sent", "isCorrect": false, "rationale": "The simple past is 'sent'." },
                    { "text": "sent, send", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to cause something to go to a destination."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'sit'?",
                "answerOptions": [
                    { "text": "sat, sat", "isCorrect": true, "rationale": "Correct. 'Sat' is both the simple past and past participle of 'sit'." },
                    { "text": "sitted, sitted", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "sit, sat", "isCorrect": false, "rationale": "The simple past is 'sat'." },
                    { "text": "sat, sit", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to rest your body on a chair or the ground."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'speak'?",
                "answerOptions": [
                    { "text": "spoke, spoken", "isCorrect": true, "rationale": "Correct. 'Spoke' is the simple past and 'spoken' is the past participle of 'speak'." },
                    { "text": "speaked, speaked", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "speak, spoke", "isCorrect": false, "rationale": "The past participle is 'spoken'." },
                    { "text": "spoken, spoke", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to converse or communicate verbally."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'spend'?",
                "answerOptions": [
                    { "text": "spent, spent", "isCorrect": true, "rationale": "Correct. 'Spent' is both the simple past and past participle of 'spend'." },
                    { "text": "spended, spended", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "spend, spent", "isCorrect": false, "rationale": "The simple past is 'spent'." },
                    { "text": "spent, spend", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to use time or money."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'stand'?",
                "answerOptions": [
                    { "text": "stood, stood", "isCorrect": true, "rationale": "Correct. 'Stood' is both the simple past and past participle of 'stand'." },
                    { "text": "standed, standed", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "stand, stood", "isCorrect": false, "rationale": "The simple past is 'stood'." },
                    { "text": "stood, stand", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to be upright on your feet."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'teach'?",
                "answerOptions": [
                    { "text": "taught, taught", "isCorrect": true, "rationale": "Correct. 'Taught' is both the simple past and past participle of 'teach'." },
                    { "text": "teached, teached", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "teach, taught", "isCorrect": false, "rationale": "The simple past is 'taught'." },
                    { "text": "taught, teach", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to impart knowledge or skills."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'understand'?",
                "answerOptions": [
                    { "text": "understood, understood", "isCorrect": true, "rationale": "Correct. 'Understood' is both the simple past and past participle of 'understand', following the pattern of 'stand'." },
                    { "text": "understanded, understanded", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "understand, understood", "isCorrect": false, "rationale": "The simple past is 'understood'." },
                    { "text": "understood, understand", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb is similar to 'stand' in its irregular conjugation."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'win'?",
                "answerOptions": [
                    { "text": "won, won", "isCorrect": true, "rationale": "Correct. 'Won' is both the simple past and past participle of 'win'." },
                    { "text": "winned, winned", "isCorrect": false, "rationale": "This verb is irregular." },
                    { "text": "win, won", "isCorrect": false, "rationale": "The simple past is 'won'." },
                    { "text": "won, win", "isCorrect": false, "rationale": "The order is inverted." }
                ],
                "hint": "This verb means to achieve victory."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'begin'?",
                "answerOptions": [
                    { "text": "began, begun", "isCorrect": true, "rationale": "Correct. 'Began' is the simple past and 'begun' is the past participle, showing a vowel change from 'a' to 'u'." },
                    { "text": "began, began", "isCorrect": false, "rationale": "This option uses the simple past form twice. The past participle has a different vowel." },
                    { "text": "begin, began", "isCorrect": false, "rationale": "This option confounds the base form with the simple past form. The past participle is different." },
                    { "text": "begun, began", "isCorrect": false, "rationale": "The order is inverted. 'Began' is the simple past, which comes first." }
                ],
                "hint": "This verb follows a vowel change pattern similar to 'sing, sang, sung'."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'swim'?",
                "answerOptions": [
                    { "text": "swam, swum", "isCorrect": true, "rationale": "Correct. The vowel change from 'i' to 'a' and then to 'u' is characteristic of this group of verbs." },
                    { "text": "swimmed, swimmed", "isCorrect": false, "rationale": "This verb is irregular and does not form its past by adding '-ed'." },
                    { "text": "swam, swam", "isCorrect": false, "rationale": "The past participle is different from the simple past; look for the vowel change to 'u'." },
                    { "text": "swum, swam", "isCorrect": false, "rationale": "Remember that the simple past usually uses the vowel 'a' in this pattern." }
                ],
                "hint": "Think about the action of moving in water. The vowel pattern is i-a-u."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'ring'?",
                "answerOptions": [
                    { "text": "ringed, ringed", "isCorrect": false, "rationale": "This is an irregular verb; it does not follow the rule of adding '-ed'." },
                    { "text": "rang, rung", "isCorrect": true, "rationale": "Correct. 'Rang' is the simple past and 'rung' is the past participle, following the i-a-u pattern." },
                    { "text": "rang, rang", "isCorrect": false, "rationale": "The past participle form generally changes the vowel to 'u' in this type of verb." },
                    { "text": "rung, rang", "isCorrect": false, "rationale": "You have inverted the order of the simple past and the past participle." }
                ],
                "hint": "The sound of a phone or a bell follows this conjugation pattern."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'sink'?",
                "answerOptions": [
                    { "text": "sank, sunk", "isCorrect": true, "rationale": "Correct. The verb follows the i-a-u vowel change pattern for the past and participle." },
                    { "text": "sank, sanken", "isCorrect": false, "rationale": "The '-en' ending is not correct for this participle; the change is only in the vowel." },
                    { "text": "sinked, sinked", "isCorrect": false, "rationale": "This verb is irregular and does not form its past by adding the suffix '-ed'." },
                    { "text": "sunk, sank", "isCorrect": false, "rationale": "The order of the simple past and the past participle is inverted." }
                ],
                "hint": "Imagine a ship sinking into the ocean; the conjugation follows the i-a-u pattern."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'fly'?",
                "answerOptions": [
                    { "text": "flied, flied", "isCorrect": false, "rationale": "This verb does not follow regular conjugation. Its past forms are unique." },
                    { "text": "flew, flown", "isCorrect": true, "rationale": "Correct. This verb has a distinct vowel change pattern, but 'flew' and 'flown' are the correct forms." },
                    { "text": "flow, flown", "isCorrect": false, "rationale": "'Flow' is a different verb with regular conjugation ('flowed')." },
                    { "text": "flew, flew", "isCorrect": false, "rationale": "The past participle of this verb ends with the suffix '-n'." }
                ],
                "hint": "Although it doesn't follow the i-a-u pattern, think about how the vowel sound changes for the action of a bird."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'shrink'?",
                "answerOptions": [
                    { "text": "shrank, shrunk", "isCorrect": true, "rationale": "Correct. This verb perfectly follows the i-a-u vowel change pattern." },
                    { "text": "shrinked, shrinked", "isCorrect": false, "rationale": "The conjugation of this verb is irregular and is not formed by adding '-ed'." },
                    { "text": "shrunk, shrank", "isCorrect": false, "rationale": "You have inverted the order. 'Shrank' is the simple past form." },
                    { "text": "shrank, shrank", "isCorrect": false, "rationale": "The past participle requires a vowel change to 'u'." }
                ],
                "hint": "Think about what happens to clothes if you wash them in very hot water."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'spring'?",
                "answerOptions": [
                    { "text": "sprang, sprung", "isCorrect": true, "rationale": "Correct. The change from vowel 'i' to 'a' and then to 'u' is the correct pattern here." },
                    { "text": "sprung, sprang", "isCorrect": false, "rationale": "The order of the forms is inverted." },
                    { "text": "springed, springed", "isCorrect": false, "rationale": "This is an irregular verb and is not conjugated by adding '-ed'." },
                    { "text": "sprang, sprang", "isCorrect": false, "rationale": "The past participle form has a different vowel than the simple past." }
                ],
                "hint": "This verb, meaning to jump or sprout, follows the same pattern as 'ring' and 'sing'."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'stink'?",
                "answerOptions": [
                    { "text": "stank, stunk", "isCorrect": true, "rationale": "Correct. This verb describes a bad smell and follows the i-a-u conjugation pattern." },
                    { "text": "stinked, stinked", "isCorrect": false, "rationale": "Being an irregular verb, it does not use the '-ed' ending." },
                    { "text": "stunk, stank", "isCorrect": false, "rationale": "You have inverted the simple past and past participle forms." },
                    { "text": "stank, stank", "isCorrect": false, "rationale": "The past participle is formed with the vowel 'u'." }
                ],
                "hint": "To describe something that smelled bad in the past, this i-a-u pattern is used."
            },
            {
                "question": "What is the simple past and past participle form of the verb 'drive'?",
                "answerOptions": [
                    { "text": "drived, drived", "isCorrect": false, "rationale": "This verb is irregular and does not conjugate by adding '-ed'." },
                    { "text": "drove, driven", "isCorrect": true, "rationale": "Correct. This verb changes its vowel and adds an '-n' ending in the participle." },
                    { "text": "drove, drove", "isCorrect": false, "rationale": "The past participle form is different; look for the one ending in '-n'." },
                    { "text": "driven, drove", "isCorrect": false, "rationale": "The order of the simple past and past participle forms is inverted." }
                ],
                "hint": "Similar to 'write' (wrote, written), this verb follows a similar pattern for its participle."
            }
        ];

        // Phrasal verbs data
        const phrasalVerbs = [
            {
                verb: "break down",
                meaning: "To stop functioning (machine, vehicle), or to collapse emotionally.",
                example: "My car broke down on the way to work. / She broke down in tears.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/e/e0/Broken_down_car.jpg/320px-Broken_down_car.jpg" // Car broken down
            },
            {
                verb: "call off",
                meaning: "To cancel something.",
                example: "They called off the meeting due to bad weather.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/c/c5/Cancelled_stamp.png/320px-Cancelled_stamp.png" // Cancelled stamp
            },
            {
                verb: "come across",
                meaning: "To find or meet something/someone by chance.",
                example: "I came across an old friend at the supermarket.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a2/Surprise_encounter.jpg/320px-Surprise_encounter.jpg" // People meeting by chance
            },
            {
                verb: "get along with",
                meaning: "To have a friendly relationship with someone.",
                example: "Do you get along with your new colleagues?",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/b/b3/Two_people_shaking_hands.jpg/320px-Two_people_shaking_hands.jpg" // People shaking hands
            },
            {
                verb: "give up",
                meaning: "To stop trying, to surrender.",
                example: "Don't give up on your dreams!",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/f/f9/Surrender_flag.svg/320px-Surrender_flag.svg.png" // White flag of surrender
            },
            {
                verb: "look for",
                meaning: "To search for something.",
                example: "I'm looking for my keys.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/e/e5/Lost_keys.jpg/320px-Lost_keys.jpg" // Lost keys
            },
            {
                verb: "put off",
                meaning: "To postpone something.",
                example: "Don't put off until tomorrow what you can do today.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/b/b1/Clock_and_calendar.jpg/320px-Clock_and_calendar.jpg" // Clock and calendar (representing delay)
            },
            {
                verb: "take off",
                meaning: "To leave the ground (plane), or to remove clothes.",
                example: "The plane took off on time. / Please take off your shoes.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Airplane_takeoff.jpg/320px-Airplane_takeoff.jpg" // Airplane taking off
            },
            {
                verb: "turn down",
                meaning: "To refuse an offer or to decrease the volume.",
                example: "He turned down the job offer. / Please turn down the music.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/c/c8/Volume_knob_down.svg/320px-Volume_knob_down.svg.png" // Volume knob turned down
            },
            {
                verb: "work out",
                meaning: "To exercise, or to solve a problem.",
                example: "I work out at the gym every day. / We need to work out a solution.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/0/0b/Person_working_out_at_gym.jpg/320px-Person_working_out_at_gym.jpg" // Person working out
            },
            // Additional Phrasal Verbs
            {
                verb: "bring up",
                meaning: "To mention a topic, or to raise a child.",
                example: "Don't bring up that topic again. / My grandparents brought me up.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a2/Woman_talking_at_a_meeting.jpg/320px-Woman_talking_at_a_meeting.jpg" // Woman talking at a meeting
            },
            {
                verb: "carry out",
                meaning: "To perform or complete a task.",
                example: "The team carried out the instructions perfectly.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/b/b4/Task_completion.jpg/320px-Task_completion.jpg" // Person completing a task
            },
            {
                verb: "find out",
                meaning: "To discover information.",
                example: "I need to find out when the train leaves.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1e/Magnifying_glass_on_text.jpg/320px-Magnifying_glass_on_text.jpg" // Magnifying glass on text
            },
            {
                verb: "get over",
                meaning: "To recover from an illness or a difficult experience.",
                example: "It took her a long time to get over the flu.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/6/69/Person_recovering_from_illness.jpg/320px-Person_recovering_from_illness.jpg" // Person recovering
            },
            {
                verb: "go on",
                meaning: "To continue, or to happen.",
                example: "Please go on with your story. / What's going on here?",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/c/c8/Continue_sign.svg/320px-Continue_sign.svg.png" // Continue sign
            },
            {
                verb: "hold on",
                meaning: "To wait for a short time.",
                example: "Hold on a minute, I'll be right back.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4b/Person_waiting.jpg/320px-Person_waiting.jpg" // Person waiting
            },
            {
                verb: "look after",
                meaning: "To take care of someone or something.",
                example: "Can you look after my cat while I'm away?",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a4/Person_caring_for_a_pet.jpg/320px-Person_caring_for_a_pet.jpg" // Person caring for a pet
            },
            {
                verb: "make up",
                meaning: "To invent a story, or to reconcile after an argument.",
                example: "He made up an excuse for being late. / They made up after their fight.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/b/b3/Two_people_shaking_hands.jpg/320px-Two_people_shaking_hands.jpg" // People reconciling (same as get along, but implies prior conflict)
            },
            {
                verb: "pass out",
                meaning: "To faint, or to distribute something.",
                example: "He passed out from the heat. / Please pass out the flyers.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/e/e0/Person_fainting.jpg/320px-Person_fainting.jpg" // Person fainting
            },
            {
                verb: "point out",
                meaning: "To draw attention to something.",
                example: "She pointed out the mistake in the report.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/f/f6/Pointing_finger.svg/320px-Pointing_finger.svg.png" // Pointing finger
            },
            {
                verb: "set up",
                meaning: "To arrange or establish something.",
                example: "We need to set up the new office equipment.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/e/e3/Setting_up_equipment.jpg/320px-Setting_up_equipment.jpg" // Setting up equipment
            },
            {
                verb: "show up",
                meaning: "To arrive or appear.",
                example: "He didn't show up for the meeting.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a2/Person_arriving.jpg/320px-Person_arriving.jpg" // Person arriving
            },
            {
                verb: "take on",
                meaning: "To accept a responsibility or challenge.",
                example: "She decided to take on the new project.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/d/d7/Person_taking_on_challenge.jpg/320px-Person_taking_on_challenge.jpg" // Person taking on a challenge
            },
            {
                verb: "turn off",
                meaning: "To switch off a light or appliance.",
                example: "Please turn off the lights when you leave.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/f/f4/Light_switch_off.svg/320px-Light_switch_off.svg.png" // Light switch off
            },
            {
                verb: "turn on",
                meaning: "To switch on a light or appliance.",
                example: "Can you turn on the TV?",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4c/Light_switch_on.svg/320px-Light_switch_on.svg.png" // Light switch on
            },
            {
                verb: "look up",
                meaning: "To search for information in a dictionary or reference book.",
                example: "I need to look up this word in the dictionary.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/8c/Dictionary_lookup.jpg/320px-Dictionary_lookup.jpg" // Person looking up word in dictionary
            },
            {
                verb: "give back",
                meaning: "To return something to its owner.",
                example: "Please give me back my book.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/b/b5/Hand_giving_back_item.jpg/320px-Hand_giving_back_item.jpg" // Hand giving back an item
            },
            {
                verb: "put on",
                meaning: "To dress oneself in something.",
                example: "Put on your coat, it's cold outside.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/e/e1/Person_putting_on_coat.jpg/320px-Person_putting_on_coat.jpg" // Person putting on a coat
            },
            {
                verb: "take out",
                meaning: "To remove something from somewhere, or to go on a date.",
                example: "Take out the trash. / He took her out to dinner.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a2/Taking_out_trash.jpg/320px-Taking_out_trash.jpg" // Person taking out trash
            },
            {
                verb: "grow up",
                meaning: "To mature or become an adult.",
                example: "I want to be a doctor when I grow up.",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/2/22/Child_growing_into_adult.jpg/320px-Child_growing_into_adult.jpg" // Child growing into adult
            }
        ];

        // Phrasal Verbs Fill in the Blanks data
        const fillInBlanksQuestions = [
            {
                sentence: "She had to ___ her trip because of the bad weather.",
                options: ["call off", "put off", "take off", "look for"],
                correctAnswer: "call off",
                hint: "This phrasal verb means to cancel something."
            },
            {
                sentence: "My car ___ on the highway, so I had to call for help.",
                options: ["put off", "break down", "get along with", "give up"],
                correctAnswer: "break down",
                hint: "This phrasal verb refers to a machine ceasing to function."
            },
            {
                sentence: "I need to ___ my old photos; I know they are somewhere.",
                options: ["turn down", "come across", "look for", "work out"],
                correctAnswer: "look for",
                hint: "This phrasal verb means to search."
            },
            {
                sentence: "It's important to ___ your differences and work as a team.",
                options: ["give up", "call off", "work out", "break down"],
                correctAnswer: "work out",
                "hint": "This phrasal verb means to resolve a problem or situation."
            },
            {
                sentence: "Don't ___ studying until the last minute!",
                options: ["take off", "put off", "turn down", "get along with"],
                correctAnswer: "put off",
                hint: "This phrasal verb means to postpone."
            },
            {
                sentence: "Could you please ___ the music? It's too loud.",
                options: ["turn on", "turn off", "turn down", "turn up"],
                correctAnswer: "turn down",
                hint: "This phrasal verb means to reduce the volume."
            },
            {
                "sentence": "The plane will ___ in 30 minutes.",
                "options": ["take off", "put off", "call off", "break down"],
                "correctAnswer": "take off",
                "hint": "This phrasal verb means to leave the ground (for an aircraft)."
            },
            {
                "sentence": "I couldn't ___ how to solve the puzzle.",
                "options": ["give up", "find out", "get over", "look up"],
                "correctAnswer": "find out",
                "hint": "This phrasal verb means to discover information."
            },
            {
                "sentence": "She's trying to ___ her fear of heights.",
                "options": ["get along with", "get over", "break down", "give up"],
                "correctAnswer": "get over",
                "hint": "This phrasal verb means to recover from something difficult."
            },
            {
                "sentence": "What's ___? Why is everyone so quiet?",
                "options": ["going on", "carrying out", "making up", "showing up"],
                "correctAnswer": "going on",
                "hint": "This phrasal verb means 'what is happening?'"
            },
            {
                "sentence": "Please ___ for a moment; I need to check something.",
                "options": ["carry out", "hold on", "pass out", "point out"],
                "correctAnswer": "hold on",
                "hint": "This phrasal verb means to wait."
            },
            {
                "sentence": "Can you ___ my plants while I'm on vacation?",
                "options": ["look for", "look after", "look up", "look out"],
                "correctAnswer": "look after",
                "hint": "This phrasal verb means to take care of."
            },
            {
                "sentence": "He had to ___ an excuse for not doing his homework.",
                "options": ["make up", "bring up", "set up", "take on"],
                "correctAnswer": "make up",
                "hint": "This phrasal verb means to invent a story."
            },
            {
                "sentence": "The volunteers helped ___ the food to the needy.",
                "options": ["pass out", "give back", "put on", "take out"],
                "correctAnswer": "pass out",
                "hint": "This phrasal verb means to distribute."
            },
            {
                "sentence": "I need to ___ the meaning of this word in the dictionary.",
                "options": ["look for", "look after", "look up", "look out"],
                "correctAnswer": "look up",
                "hint": "This phrasal verb means to search for information."
            }
        ];

        // New Phrasal Verb Quiz Questions
        const phrasalVerbQuizQuestions = [
            {
                question: "Which phrasal verb means 'to cancel something'?",
                options: ["call off", "put off", "take off", "give up"],
                correctAnswer: "call off",
                hint: "Think about stopping an event before it happens."
            },
            {
                question: "Which phrasal verb means 'to stop functioning (for a machine or vehicle)'?",
                options: ["break down", "work out", "turn off", "set up"],
                correctAnswer: "break down",
                hint: "Imagine a car that suddenly stops working."
            },
            {
                question: "Which phrasal verb means 'to find or meet someone/something by chance'?",
                options: ["look for", "come across", "find out", "point out"],
                correctAnswer: "come across",
                hint: "It implies an unexpected discovery."
            },
            {
                question: "Which phrasal verb means 'to have a friendly relationship with someone'?",
                options: ["get over", "get along with", "make up", "show up"],
                correctAnswer: "get along with",
                hint: "It describes how well people interact."
            },
            {
                question: "Which phrasal verb means 'to stop trying; to surrender'?",
                options: ["hold on", "give up", "carry out", "bring up"],
                correctAnswer: "give up",
                hint: "Don't do this with your dreams!"
            },
            {
                question: "Which phrasal verb means 'to search for something'?",
                options: ["look after", "look up", "look for", "take out"],
                correctAnswer: "look for",
                hint: "You do this when you lose your keys."
            },
            {
                question: "Which phrasal verb means 'to postpone something'?",
                options: ["put on", "put off", "take off", "turn down"],
                correctAnswer: "put off",
                hint: "Don't do this with your homework!"
            },
            {
                question: "Which phrasal verb means 'to leave the ground (for a plane) or to remove clothes'?",
                options: ["turn on", "take on", "take off", "grow up"],
                correctAnswer: "take off",
                hint: "It has two common meanings, one related to aviation and another to clothing."
            },
            {
                question: "Which phrasal verb means 'to refuse an offer or to decrease the volume'?",
                options: ["turn up", "turn off", "turn down", "point out"],
                correctAnswer: "turn down",
                hint: "You do this to the music when it's too loud."
            },
            {
                question: "Which phrasal verb means 'to exercise, or to solve a problem'?",
                options: ["work out", "set up", "pass out", "find out"],
                correctAnswer: "work out",
                hint: "You do this at the gym, or with a difficult situation."
            },
            {
                question: "Which phrasal verb means 'to mention a topic, or to raise a child'?",
                options: ["bring up", "carry out", "go on", "hold on"],
                correctAnswer: "bring up",
                hint: "It can mean to introduce a subject in conversation."
            },
            {
                question: "Which phrasal verb means 'to perform or complete a task'?",
                options: ["make up", "point out", "carry out", "show up"],
                correctAnswer: "carry out",
                hint: "You do this with instructions or plans."
            },
            {
                question: "Which phrasal verb means 'to discover information'?",
                options: ["look up", "find out", "get over", "give back"],
                correctAnswer: "find out",
                hint: "You do this when you want to learn something new."
            },
            {
                question: "Which phrasal verb means 'to recover from an illness or a difficult experience'?",
                options: ["get along with", "get over", "break down", "give up"],
                correctAnswer: "get over",
                hint: "It takes time to do this after a bad cold."
            },
            {
                question: "Which phrasal verb means 'to continue, or to happen'?",
                options: ["go on", "hold on", "set up", "take on"],
                correctAnswer: "go on",
                hint: "You might say this to someone to encourage them to keep talking."
            }
        ];


        let currentQuestionIndex = 0;
        let score = 0;
        let quizActive = false; // To prevent multiple clicks during feedback for irregular verbs quiz

        let currentFillInBlanksIndex = 0;
        let fillInBlanksScore = 0;
        let fibGameActive = false; // To prevent multiple clicks during feedback for fill in the blanks game

        let currentPhrasalVerbQuizIndex = 0;
        let phrasalVerbQuizScore = 0;
        let pvQuizActive = false; // To prevent multiple clicks during feedback for phrasal verb quiz

        // We will shuffle the quiz questions at the start
        let shuffledIrregularQuizQuestions = [];
        let shuffledFillInBlanksQuestions = [];
        let shuffledPhrasalVerbQuizQuestions = [];

        const questionDisplay = document.getElementById('question-display');
        const answerOptionsContainer = document.getElementById('answer-options');
        const feedbackMessage = document.getElementById('feedback-message');
        const hintDisplay = document.getElementById('hint-display');
        const showHintButton = document.getElementById('show-hint-button');
        const nextQuestionButton = document.getElementById('next-question-button');
        const restartQuizButton = document.getElementById('restart-quiz-button');

        const tabQuizButton = document.getElementById('tab-quiz');
        const tabPhrasalVerbsButton = document.getElementById('tab-phrasal-verbs');
        const tabFillInBlanksButton = document.getElementById('tab-fill-in-blanks');
        const tabPhrasalVerbQuizButton = document.getElementById('tab-phrasal-verb-quiz');

        const quizSection = document.getElementById('quiz-section');
        const phrasalVerbsSection = document.getElementById('phrasal-verbs-section');
        const fillInBlanksSection = document.getElementById('fill-in-blanks-section');
        const phrasalVerbQuizSection = document.getElementById('phrasal-verb-quiz-section');

        const phrasalVerbsList = document.getElementById('phrasal-verbs-list');

        const fibQuestionDisplay = document.getElementById('fib-question-display');
        const fibAnswerOptionsContainer = document.getElementById('fib-answer-options');
        const fibFeedbackMessage = document.getElementById('fib-feedback-message');
        const fibHintDisplay = document.getElementById('fib-hint-display');
        const fibShowHintButton = document.getElementById('fib-show-hint-button');
        const fibNextQuestionButton = document.getElementById('fib-next-question-button');
        const fibRestartQuizButton = document.getElementById('fib-restart-quiz-button');

        const pvQuizQuestionDisplay = document.getElementById('pv-quiz-question-display');
        const pvQuizImageDisplay = document.getElementById('pv-quiz-image-display');
        const pvQuizAnswerOptionsContainer = document.getElementById('pv-quiz-answer-options');
        const pvQuizFeedbackMessage = document.getElementById('pv-quiz-feedback-message');
        const pvQuizHintDisplay = document.getElementById('pv-quiz-hint-display');
        const pvQuizShowHintButton = document.getElementById('pv-quiz-show-hint-button');
        const pvQuizNextQuestionButton = document.getElementById('pv-quiz-next-question-button');
        const pvQuizRestartQuizButton = document.getElementById('pv-quiz-restart-quiz-button');


        // Function to shuffle an array (Fisher-Yates algorithm)
        function shuffleArray(array) {
            for (let i = array.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [array[i], array[j]] = [array[j], array[i]];
            }
        }

        // --- Irregular Verbs Quiz Functions ---
        function initializeQuiz() {
            shuffledIrregularQuizQuestions = [...allIrregularVerbs]; // Copy all verbs
            shuffleArray(shuffledIrregularQuizQuestions); // Shuffle them
            currentQuestionIndex = 0;
            score = 0;
            displayQuestion();
        }

        function displayQuestion() {
            quizActive = true;
            const currentQuestion = shuffledIrregularQuizQuestions[currentQuestionIndex];
            questionDisplay.textContent = currentQuestion.question;
            answerOptionsContainer.innerHTML = ''; // Clear previous options
            feedbackMessage.textContent = ''; // Clear feedback
            hintDisplay.textContent = ''; // Clear hint
            showHintButton.classList.remove('hidden');
            nextQuestionButton.classList.add('hidden');
            restartQuizButton.classList.add('hidden');

            // Shuffle answer options for the current question
            const shuffledOptions = [...currentQuestion.answerOptions];
            shuffleArray(shuffledOptions);

            shuffledOptions.forEach(option => {
                const button = document.createElement('button');
                button.textContent = option.text;
                button.classList.add(
                    'answer-button',
                    'bg-blue-200', 'text-blue-800', 'font-semibold', 'py-3', 'px-4',
                    'rounded-lg', 'shadow-md', 'hover:bg-blue-300', 'transition-colors',
                    'duration-200', 'text-lg', 'text-left', 'truncate'
                );
                button.onclick = () => checkAnswer(option, button);
                answerOptionsContainer.appendChild(button);
            });
        }

        function checkAnswer(selectedOption, clickedButton) {
            if (!quizActive) return; // Prevent multiple clicks

            quizActive = false; // Disable further clicks for this question

            const allButtons = document.querySelectorAll('#answer-options .answer-button');
            allButtons.forEach(button => {
                button.disabled = true; // Disable all buttons after an answer is selected
                if (button.textContent === selectedOption.text) {
                    if (selectedOption.isCorrect) {
                        button.classList.remove('bg-blue-200', 'hover:bg-blue-300');
                        button.classList.add('bg-green-500', 'text-white');
                        feedbackMessage.textContent = 'Correct! ' + selectedOption.rationale;
                        feedbackMessage.classList.remove('text-red-600');
                        feedbackMessage.classList.add('text-green-600');
                        score++;
                    } else {
                        button.classList.remove('bg-blue-200', 'hover:bg-blue-300');
                        button.classList.add('bg-red-500', 'text-white');
                        feedbackMessage.textContent = 'Incorrect. ' + selectedOption.rationale;
                        feedbackMessage.classList.remove('text-green-600');
                        feedbackMessage.classList.add('text-red-600');
                        // Highlight the correct answer
                        const currentQuestion = shuffledIrregularQuizQuestions[currentQuestionIndex];
                        const correctOptionText = currentQuestion.answerOptions.find(opt => opt.isCorrect).text;
                        allButtons.forEach(btn => {
                            if (btn.textContent === correctOptionText) {
                                btn.classList.remove('bg-blue-200');
                                btn.classList.add('bg-green-400', 'text-white', 'border-2', 'border-green-700');
                            }
                        });
                    }
                }
            });

            nextQuestionButton.classList.remove('hidden');
            showHintButton.classList.add('hidden'); // Hide hint button after answer
        }

        function nextQuestion() {
            currentQuestionIndex++;
            if (currentQuestionIndex < shuffledIrregularQuizQuestions.length) {
                displayQuestion();
            } else {
                showResults();
            }
        }

        function showResults() {
            questionDisplay.textContent = `Quiz Completed! Your score is ${score} out of ${shuffledIrregularQuizQuestions.length}.`;
            answerOptionsContainer.innerHTML = '';
            feedbackMessage.textContent = 'Congratulations on finishing the quiz!';
            feedbackMessage.classList.remove('text-green-600', 'text-red-600');
            feedbackMessage.classList.add('text-blue-700');
            hintDisplay.textContent = '';
            nextQuestionButton.classList.add('hidden');
            showHintButton.classList.add('hidden');
            restartQuizButton.classList.remove('hidden');
        }

        function restartQuiz() {
            initializeQuiz(); // Re-initialize to shuffle and restart
        }

        function showHint() {
            const currentQuestion = shuffledIrregularQuizQuestions[currentQuestionIndex];
            hintDisplay.textContent = 'Hint: ' + currentQuestion.hint;
        }

        // Event Listeners for Irregular Verbs Quiz Buttons
        showHintButton.addEventListener('click', showHint);
        nextQuestionButton.addEventListener('click', nextQuestion);
        restartQuizButton.addEventListener('click', restartQuiz);

        // --- Phrasal Verbs List Functions ---
        function displayPhrasalVerbs() {
            phrasalVerbsList.innerHTML = '';
            phrasalVerbs.forEach((pv, index) => {
                const pvItem = document.createElement('div');
                pvItem.classList.add('bg-white', 'p-4', 'rounded-lg', 'shadow-sm', 'border', 'border-gray-200', 'flex', 'flex-col', 'md:flex-row', 'items-center', 'space-y-4', 'md:space-y-0', 'md:space-x-4');
                
                pvItem.innerHTML = `
                    <img src="${pv.image}" alt="Image for ${pv.verb}" class="w-32 h-24 object-cover rounded-md shadow-sm" onerror="this.onerror=null;this.src='https://placehold.co/150x100/CCCCCC/000000?text=Image+Error';">
                    <div class="flex-grow text-center md:text-left">
                        <h3 class="text-xl font-bold text-purple-800 mb-2">${pv.verb}</h3>
                        <p class="text-gray-700 mb-2"><strong>Meaning:</strong> <span id="meaning-${index}" class="hidden">${pv.meaning}</span></p>
                        <p class="text-gray-600 italic"><strong>Example:</strong> <span id="example-${index}" class="hidden">${pv.example}</span></p>
                        <button class="toggle-meaning-button mt-3 bg-purple-500 text-white px-4 py-2 rounded-full text-sm font-semibold hover:bg-purple-600 transition-colors duration-200" data-index="${index}">
                            Show Meaning and Example
                        </button>
                    </div>
                `;
                phrasalVerbsList.appendChild(pvItem);
            });

            // Add event listeners for toggle buttons
            document.querySelectorAll('.toggle-meaning-button').forEach(button => {
                button.addEventListener('click', (event) => {
                    const index = event.target.dataset.index;
                    const meaningSpan = document.getElementById(`meaning-${index}`);
                    const exampleSpan = document.getElementById(`example-${index}`);
                    if (meaningSpan.classList.contains('hidden')) {
                        meaningSpan.classList.remove('hidden');
                        exampleSpan.classList.remove('hidden');
                        event.target.textContent = 'Hide Meaning and Example';
                    } else {
                        meaningSpan.classList.add('hidden');
                        exampleSpan.classList.add('hidden');
                        event.target.textContent = 'Show Meaning and Example';
                    }
                });
            });
        }

        // --- Phrasal Verbs Fill in the Blanks Game Functions ---
        function initializeFillInBlanksGame() {
            shuffledFillInBlanksQuestions = [...fillInBlanksQuestions]; // Copy all questions
            shuffleArray(shuffledFillInBlanksQuestions); // Shuffle them
            currentFillInBlanksIndex = 0;
            fillInBlanksScore = 0;
            displayFillInBlanksQuestion();
        }

        function displayFillInBlanksQuestion() {
            fibGameActive = true;
            const currentQuestion = shuffledFillInBlanksQuestions[currentFillInBlanksIndex];
            fibQuestionDisplay.textContent = currentQuestion.sentence;
            fibAnswerOptionsContainer.innerHTML = ''; // Clear previous options
            fibFeedbackMessage.textContent = ''; // Clear feedback
            fibHintDisplay.textContent = ''; // Clear hint
            fibShowHintButton.classList.remove('hidden');
            fibNextQuestionButton.classList.add('hidden');
            fibRestartQuizButton.classList.add('hidden');

            // Shuffle answer options
            const shuffledOptions = [...currentQuestion.options];
            shuffleArray(shuffledOptions);

            shuffledOptions.forEach(option => {
                const button = document.createElement('button');
                button.textContent = option;
                button.classList.add(
                    'fib-answer-button',
                    'bg-teal-200', 'text-teal-800', 'font-semibold', 'py-3', 'px-4',
                    'rounded-lg', 'shadow-md', 'hover:bg-teal-300', 'transition-colors',
                    'duration-200', 'text-lg', 'text-left', 'truncate'
                );
                button.onclick = () => checkFillInBlanksAnswer(option, button);
                fibAnswerOptionsContainer.appendChild(button);
            });
        }

        function checkFillInBlanksAnswer(selectedOption, clickedButton) {
            if (!fibGameActive) return;

            fibGameActive = false;

            const allButtons = document.querySelectorAll('#fib-answer-options .fib-answer-button');
            allButtons.forEach(button => {
                button.disabled = true;
                if (button.textContent === selectedOption) {
                    const currentQuestion = shuffledFillInBlanksQuestions[currentFillInBlanksIndex];
                    if (selectedOption === currentQuestion.correctAnswer) {
                        button.classList.remove('bg-teal-200', 'hover:bg-teal-300');
                        button.classList.add('bg-green-500', 'text-white');
                        fibFeedbackMessage.textContent = 'Correct! The phrasal verb fits perfectly. ';
                        fibFeedbackMessage.classList.remove('text-red-600');
                        fibFeedbackMessage.classList.add('text-green-600');
                        fillInBlanksScore++;
                    } else {
                        button.classList.remove('bg-teal-200', 'hover:bg-teal-300');
                        button.classList.add('bg-red-500', 'text-white');
                        fibFeedbackMessage.textContent = 'Incorrect. The correct answer was "' + currentQuestion.correctAnswer + '".';
                        fibFeedbackMessage.classList.remove('text-green-600');
                        fibFeedbackMessage.classList.add('text-red-600');
                        // Highlight the correct answer
                        allButtons.forEach(btn => {
                            if (btn.textContent === currentQuestion.correctAnswer) {
                                btn.classList.remove('bg-teal-200');
                                btn.classList.add('bg-green-400', 'text-white', 'border-2', 'border-green-700');
                            }
                        });
                    }
                }
            });

            fibNextQuestionButton.classList.remove('hidden');
            fibShowHintButton.classList.add('hidden');
        }

        function nextFillInBlanksQuestion() {
            currentFillInBlanksIndex++;
            if (currentFillInBlanksIndex < shuffledFillInBlanksQuestions.length) {
                displayFillInBlanksQuestion();
            } else {
                showFillInBlanksResults();
            }
        }

        function showFillInBlanksResults() {
            fibQuestionDisplay.textContent = `Game Completed! Your score is ${fillInBlanksScore} out of ${shuffledFillInBlanksQuestions.length}.`;
            fibAnswerOptionsContainer.innerHTML = '';
            fibFeedbackMessage.textContent = 'Great job finishing the Fill in the Blanks game!';
            fibFeedbackMessage.classList.remove('text-green-600', 'text-red-600');
            fibFeedbackMessage.classList.add('text-teal-700');
            fibHintDisplay.textContent = '';
            fibNextQuestionButton.classList.add('hidden');
            fibShowHintButton.classList.add('hidden');
            fibRestartQuizButton.classList.remove('hidden');
        }

        function restartFillInBlanks() {
            initializeFillInBlanksGame(); // Re-initialize to shuffle and restart
        }

        function showFillInBlanksHint() {
            const currentQuestion = shuffledFillInBlanksQuestions[currentFillInBlanksIndex];
            fibHintDisplay.textContent = 'Hint: ' + currentQuestion.hint;
        }

        // Event Listeners for Fill in the Blanks Game Buttons
        fibShowHintButton.addEventListener('click', showFillInBlanksHint);
        fibNextQuestionButton.addEventListener('click', nextFillInBlanksQuestion);
        fibRestartQuizButton.addEventListener('click', restartFillInBlanks);

        // --- Phrasal Verbs Quiz Functions (New Game) ---
        function initializePhrasalVerbQuiz() {
            shuffledPhrasalVerbQuizQuestions = [...phrasalVerbQuizQuestions]; // Copy all questions
            shuffleArray(shuffledPhrasalVerbQuizQuestions); // Shuffle them
            currentPhrasalVerbQuizIndex = 0;
            phrasalVerbQuizScore = 0;
            displayPhrasalVerbQuizQuestion();
        }

        function displayPhrasalVerbQuizQuestion() {
            pvQuizActive = true;
            const currentQuestion = shuffledPhrasalVerbQuizQuestions[currentPhrasalVerbQuizIndex];
            pvQuizQuestionDisplay.textContent = currentQuestion.question;
            pvQuizAnswerOptionsContainer.innerHTML = ''; // Clear previous options
            pvQuizFeedbackMessage.textContent = ''; // Clear feedback
            pvQuizHintDisplay.textContent = ''; // Clear hint
            pvQuizShowHintButton.classList.remove('hidden');
            pvQuizNextQuestionButton.classList.add('hidden');
            pvQuizRestartQuizButton.classList.add('hidden');

            // Display image if available (find from phrasalVerbs list)
            const pvInList = phrasalVerbs.find(pv => pv.verb === currentQuestion.correctAnswer);
            if (pvInList && pvInList.image) {
                pvQuizImageDisplay.innerHTML = `<img src="${pvInList.image}" alt="Image for ${pvInList.verb}" class="w-48 h-32 object-cover rounded-md shadow-md" onerror="this.onerror=null;this.src='https://placehold.co/150x100/CCCCCC/000000?text=Image+Error';">`;
            } else {
                pvQuizImageDisplay.innerHTML = ''; // Clear image if not found
            }

            // Shuffle answer options
            const shuffledOptions = [...currentQuestion.options];
            shuffleArray(shuffledOptions);

            shuffledOptions.forEach(option => {
                const button = document.createElement('button');
                button.textContent = option;
                button.classList.add(
                    'pv-quiz-answer-button',
                    'bg-pink-200', 'text-pink-800', 'font-semibold', 'py-3', 'px-4',
                    'rounded-lg', 'shadow-md', 'hover:bg-pink-300', 'transition-colors',
                    'duration-200', 'text-lg', 'text-left', 'truncate'
                );
                button.onclick = () => checkPhrasalVerbQuizAnswer(option, button);
                pvQuizAnswerOptionsContainer.appendChild(button);
            });
        }

        function checkPhrasalVerbQuizAnswer(selectedOption, clickedButton) {
            if (!pvQuizActive) return;

            pvQuizActive = false;

            const allButtons = document.querySelectorAll('#pv-quiz-answer-options .pv-quiz-answer-button');
            allButtons.forEach(button => {
                button.disabled = true;
                if (button.textContent === selectedOption) {
                    const currentQuestion = shuffledPhrasalVerbQuizQuestions[currentPhrasalVerbQuizIndex];
                    if (selectedOption === currentQuestion.correctAnswer) {
                        button.classList.remove('bg-pink-200', 'hover:bg-pink-300');
                        button.classList.add('bg-green-500', 'text-white');
                        pvQuizFeedbackMessage.textContent = 'Correct! That\'s the right phrasal verb.';
                        pvQuizFeedbackMessage.classList.remove('text-red-600');
                        pvQuizFeedbackMessage.classList.add('text-green-600');
                        phrasalVerbQuizScore++;
                    } else {
                        button.classList.remove('bg-pink-200', 'hover:bg-pink-300');
                        button.classList.add('bg-red-500', 'text-white');
                        pvQuizFeedbackMessage.textContent = 'Incorrect. The correct answer was "' + currentQuestion.correctAnswer + '".';
                        pvQuizFeedbackMessage.classList.remove('text-green-600');
                        pvQuizFeedbackMessage.classList.add('text-red-600');
                        // Highlight the correct answer
                        allButtons.forEach(btn => {
                            if (btn.textContent === currentQuestion.correctAnswer) {
                                btn.classList.remove('bg-pink-200');
                                btn.classList.add('bg-green-400', 'text-white', 'border-2', 'border-green-700');
                            }
                        });
                    }
                }
            });

            pvQuizNextQuestionButton.classList.remove('hidden');
            pvQuizShowHintButton.classList.add('hidden');
        }

        function nextPhrasalVerbQuizQuestion() {
            currentPhrasalVerbQuizIndex++;
            if (currentPhrasalVerbQuizIndex < shuffledPhrasalVerbQuizQuestions.length) {
                displayPhrasalVerbQuizQuestion();
            } else {
                showPhrasalVerbQuizResults();
            }
        }

        function showPhrasalVerbQuizResults() {
            pvQuizQuestionDisplay.textContent = `Phrasal Verbs Quiz Completed! Your score is ${phrasalVerbQuizScore} out of ${shuffledPhrasalVerbQuizQuestions.length}.`;
            pvQuizAnswerOptionsContainer.innerHTML = '';
            pvQuizImageDisplay.innerHTML = ''; // Clear image
            pvQuizFeedbackMessage.textContent = 'Great job finishing the Phrasal Verbs Quiz!';
            pvQuizFeedbackMessage.classList.remove('text-green-600', 'text-red-600');
            pvQuizFeedbackMessage.classList.add('text-pink-700');
            pvQuizHintDisplay.textContent = '';
            pvQuizNextQuestionButton.classList.add('hidden');
            pvQuizShowHintButton.classList.add('hidden');
            pvQuizRestartQuizButton.classList.remove('hidden');
        }

        function restartPhrasalVerbQuiz() {
            initializePhrasalVerbQuiz(); // Re-initialize to shuffle and restart
        }

        function showPhrasalVerbQuizHint() {
            const currentQuestion = shuffledPhrasalVerbQuizQuestions[currentPhrasalVerbQuizIndex];
            pvQuizHintDisplay.textContent = 'Hint: ' + currentQuestion.hint;
        }

        // Event Listeners for Phrasal Verbs Quiz Buttons
        pvQuizShowHintButton.addEventListener('click', showPhrasalVerbQuizHint);
        pvQuizNextQuestionButton.addEventListener('click', nextPhrasalVerbQuizQuestion);
        pvQuizRestartQuizButton.addEventListener('click', restartPhrasalVerbQuiz);


        // --- Tab switching logic ---
        function showTab(tabId) {
            document.querySelectorAll('.tab-content').forEach(section => {
                section.classList.add('hidden');
            });
            document.querySelectorAll('.tab-button').forEach(button => {
                button.classList.remove('bg-blue-600', 'text-white', 'bg-purple-600', 'bg-teal-600', 'bg-pink-600');
                button.classList.add('bg-gray-300', 'text-gray-800');
            });

            if (tabId === 'quiz-section') {
                quizSection.classList.remove('hidden');
                tabQuizButton.classList.remove('bg-gray-300', 'text-gray-800');
                tabQuizButton.classList.add('bg-blue-600', 'text-white');
                initializeQuiz(); // Initialize and shuffle irregular verbs quiz questions
            } else if (tabId === 'phrasal-verbs-section') {
                phrasalVerbsSection.classList.remove('hidden');
                tabPhrasalVerbsButton.classList.remove('bg-gray-300', 'text-gray-800');
                tabPhrasalVerbsButton.classList.add('bg-purple-600', 'text-white');
                displayPhrasalVerbs(); // Display phrasal verbs when entering section
            } else if (tabId === 'fill-in-blanks-section') {
                fillInBlanksSection.classList.remove('hidden');
                tabFillInBlanksButton.classList.remove('bg-gray-300', 'text-gray-800');
                tabFillInBlanksButton.classList.add('bg-teal-600', 'text-white');
                initializeFillInBlanksGame(); // Initialize and shuffle fill in the blanks questions
            } else if (tabId === 'phrasal-verb-quiz-section') {
                phrasalVerbQuizSection.classList.remove('hidden');
                tabPhrasalVerbQuizButton.classList.remove('bg-gray-300', 'text-gray-800');
                tabPhrasalVerbQuizButton.classList.add('bg-pink-600', 'text-white');
                initializePhrasalVerbQuiz(); // Initialize and shuffle phrasal verb quiz questions
            }
        }

        tabQuizButton.addEventListener('click', () => showTab('quiz-section'));
        tabPhrasalVerbsButton.addEventListener('click', () => showTab('phrasal-verbs-section'));
        tabFillInBlanksButton.addEventListener('click', () => showTab('fill-in-blanks-section'));
        tabPhrasalVerbQuizButton.addEventListener('click', () => showTab('phrasal-verb-quiz-section'));

        // Initial load
        window.onload = () => {
            showTab('quiz-section'); // Show quiz section by default
        };
    </script>
</body>
</html>
