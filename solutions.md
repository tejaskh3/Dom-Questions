

## Solution 1

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Light Bulb Toggle</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
            text-align: center;
            background-color: #f5f5f5;
            transition: background-color 0.3s ease;
        }
        
        .dark-mode {
            background-color: #333;
            color: white;
        }
        
        h1 {
            margin-bottom: 30px;
        }
        
        .bulb-container {
            margin: 40px auto;
            position: relative;
            width: 100px;
            height: 150px;
        }
        
        .bulb {
            width: 80px;
            height: 80px;
            background-color: #f1c40f;
            border-radius: 50%;
            position: absolute;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            box-shadow: 0 0 50px rgba(241, 196, 15, 0.5);
            transition: all 0.3s ease;
        }
        
        .bulb.off {
            background-color: #95a5a6;
            box-shadow: none;
        }
        
        .bulb-base {
            width: 30px;
            height: 40px;
            background-color: #7f8c8d;
            position: absolute;
            top: 80px;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 0 0 5px 5px;
        }
        
        button {
            padding: 10px 20px;
            background-color: #3498db;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            transition: background-color 0.3s;
        }
        
        button:hover {
            background-color: #2980b9;
        }
        
        .switch-status {
            margin-top: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body id="body">
    <h1>Light Bulb Toggle</h1>
    <p>Click the button to turn the light bulb on or off</p>
    
    <div class="bulb-container">
        <div id="bulb" class="bulb off"></div>
        <div class="bulb-base"></div>
    </div>
    
    <button id="toggleButton">Turn On</button>
    
    <p id="status" class="switch-status">Status: Off</p>
    
    <script>
        const toggleButton = document.getElementById('toggleButton');
        const bulb = document.getElementById('bulb');
        const body = document.getElementById('body');
        const status = document.getElementById('status');
        
        toggleButton.addEventListener('click', function() {
            bulb.classList.toggle('off');
            
            body.classList.toggle('dark-mode');
            if (bulb.classList.contains('off')) {
                toggleButton.textContent = 'Turn On';
                status.textContent = 'Status: Off';
            } else {
                toggleButton.textContent = 'Turn Off';
                status.textContent = 'Status: On';
            }
        });
    </script>
</body>
</html>
```



## Solution for question 2

```html

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Change Text Color</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
            text-align: center;
        }
        h1 {
            transition: color 0.3s ease;
        }
        .color-buttons {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin: 20px 0;
        }
        button {
            padding: 10px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            color: white;
        }
        #redButton {
            background-color: #e74c3c;
        }
        #greenButton {
            background-color: #2ecc71;
        }
        #blueButton {
            background-color: #3498db;
        }
        #purpleButton {
            background-color: #9b59b6;
        }
        #resetButton {
            background-color: #34495e;
        }
    </style>
</head>
<body>
    <h1 id="mainHeading">Change My Color!</h1>
    <p>Click a button to change the text color:</p>
    
    <div class="color-buttons">
        <button id="redButton">Red</button>
        <button id="greenButton">Green</button>
        <button id="blueButton">Blue</button>
        <button id="purpleButton">Purple</button>
        <button id="resetButton">Reset</button>
    </div>
    
    <script>
        // get reference to the heading
        const heading = document.getElementById('mainHeading');
        
        // get references to all buttons
        const redButton = document.getElementById('redButton');
        const greenButton = document.getElementById('greenButton');
        const blueButton = document.getElementById('blueButton');
        const purpleButton = document.getElementById('purpleButton');
        const resetButton = document.getElementById('resetButton');
        
        // add event listeners for each button
        redButton.addEventListener('click', function() {
            heading.style.color = '#e74c3c';
        });
        
        greenButton.addEventListener('click', function() {
            heading.style.color = '#2ecc71';
        });
        
        blueButton.addEventListener('click', function() {
            heading.style.color = '#3498db';
        });
        
        purpleButton.addEventListener('click', function() {
            heading.style.color = '#9b59b6';
        });
        
        resetButton.addEventListener('click', function() {
            heading.style.color = 'black';
        });
    </script>
</body>
</html>
```




## Solution for question 3

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Real-time Form Input Display</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
        }
        .form-group {
            margin-bottom: 15px;
        }
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }
        input, textarea, select {
            width: 100%;
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        .preview-card {
            margin-top: 30px;
            border: 1px solid #ddd;
            border-radius: 8px;
            padding: 20px;
            background-color: #f9f9f9;
        }
        h2 {
            margin-top: 0;
            color: #2c3e50;
        }
        .profile-info p {
            margin: 5px 0;
        }
        .profile-info strong {
            color: #34495e;
        }
    </style>
</head>
<body>
    <h1>Profile Form</h1>
    <p>Enter your information below to see it displayed in real-time:</p>
    
    <div class="form-container">
        <div class="form-group">
            <label for="nameInput">Name:</label>
            <input type="text" id="nameInput" placeholder="Enter your name">
        </div>
        
        <div class="form-group">
            <label for="jobInput">Job Title:</label>
            <input type="text" id="jobInput" placeholder="Enter your job title">
        </div>
        
        <div class="form-group">
            <label for="ageInput">Age:</label>
            <input type="number" id="ageInput" min="18" max="120" placeholder="Enter your age">
        </div>
        
        <div class="form-group">
            <label for="bioInput">Bio:</label>
            <textarea id="bioInput" rows="4" placeholder="Tell us about yourself"></textarea>
        </div>
    </div>
    
    <div class="preview-card">
        <h2>Profile Preview</h2>
        <div class="profile-info">
            <p><strong>Name:</strong> <span id="nameDisplay">Not provided</span></p>
            <p><strong>Job Title:</strong> <span id="jobDisplay">Not provided</span></p>
            <p><strong>Age:</strong> <span id="ageDisplay">Not provided</span></p>
            <p><strong>Bio:</strong> <span id="bioDisplay">Not provided</span></p>
        </div>
    </div>
    
    <script>
        // Get references to all input elements
        const nameInput = document.getElementById('nameInput');
        const jobInput = document.getElementById('jobInput');
        const ageInput = document.getElementById('ageInput');
        const bioInput = document.getElementById('bioInput');
        
        // Get references to all display elements
        const nameDisplay = document.getElementById('nameDisplay');
        const jobDisplay = document.getElementById('jobDisplay');
        const ageDisplay = document.getElementById('ageDisplay');
        const bioDisplay = document.getElementById('bioDisplay');
        
        // Add event listeners for real-time updates
        nameInput.addEventListener('input', function() {
            nameDisplay.textContent = this.value || 'Not provided';
        });
        
        jobInput.addEventListener('input', function() {
            jobDisplay.textContent = this.value || 'Not provided';
        });
        
        ageInput.addEventListener('input', function() {
            ageDisplay.textContent = this.value || 'Not provided';
        });
        
        bioInput.addEventListener('input', function() {
            bioDisplay.textContent = this.value || 'Not provided';
        });
    </script>
</body>
</html>
```

## Solution 4

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Task List Application</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f7f9fc;
        }
        
        h1 {
            color: #2c3e50;
            text-align: center;
            margin-bottom: 30px;
        }
        
        .task-form {
            display: flex;
            margin-bottom: 20px;
        }
        
        .task-input {
            flex: 1;
            padding: 10px;
            font-size: 16px;
            border: 1px solid #ddd;
            border-radius: 4px 0 0 4px;
        }
        
        .add-button {
            padding: 10px 15px;
            background-color: #3498db;
            color: white;
            border: none;
            border-radius: 0 4px 4px 0;
            cursor: pointer;
            font-size: 16px;
        }
        
        .add-button:hover {
            background-color: #2980b9;
        }
        
        .task-list {
            list-style: none;
            padding: 0;
        }
        
        .task-item {
            display: flex;
            align-items: center;
            padding: 12px 15px;
            background-color: white;
            border-radius: 4px;
            margin-bottom: 10px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            animation: fadeIn 0.3s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(-10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .task-text {
            flex: 1;
            margin-left: 10px;
        }
        
        .complete-checkbox {
            width: 18px;
            height: 18px;
            cursor: pointer;
        }
        
        .task-item.completed .task-text {
            text-decoration: line-through;
            color: #95a5a6;
        }
        
        .delete-button {
            background-color: #e74c3c;
            color: white;
            border: none;
            border-radius: 4px;
            padding: 5px 10px;
            cursor: pointer;
            font-size: 14px;
            opacity: 0.8;
            transition: opacity 0.2s;
        }
        
        .delete-button:hover {
            opacity: 1;
        }
        
        .empty-list {
            text-align: center;
            color: #7f8c8d;
            font-style: italic;
            padding: 20px;
        }
        
        .task-stats {
            display: flex;
            justify-content: space-between;
            margin-top: 20px;
            color: #7f8c8d;
            font-size: 14px;
        }
    </style>
</head>
<body>
    <h1>Task List</h1>
    
    <div class="task-form">
        <input type="text" id="taskInput" class="task-input" placeholder="Add a new task...">
        <button id="addButton" class="add-button">Add</button>
    </div>
    
    <ul id="taskList" class="task-list">
        <li class="empty-list">No tasks yet. Add one above!</li>
    </ul>
    
    <div class="task-stats">
        <span id="totalTasks">Total tasks: 0</span>
        <span id="completedTasks">Completed: 0</span>
    </div>
    
    <script>
        const taskInput = document.getElementById('taskInput');
        const addButton = document.getElementById('addButton');
        const taskList = document.getElementById('taskList');
        const totalTasksSpan = document.getElementById('totalTasks');
        const completedTasksSpan = document.getElementById('completedTasks');
        
        // Task counters
        let totalTasks = 0;
        let completedTasks = 0;
        
        function addTask() {
            const taskText = taskInput.value.trim();
            
            if (taskText !== '') {
                //  empty list message if it exists
                const emptyListMessage = document.querySelector('.empty-list');
                if (emptyListMessage) {
                    emptyListMessage.remove();
                }
                
                // task item
                const taskItem = document.createElement('li');
                taskItem.className = 'task-item';
                
                // checkbox
                const checkbox = document.createElement('input');
                checkbox.type = 'checkbox';
                checkbox.className = 'complete-checkbox';
                checkbox.addEventListener('change', function() {
                    if (this.checked) {
                        taskItem.classList.add('completed');
                        completedTasks++;
                    } else {
                        taskItem.classList.remove('completed');
                        completedTasks--;
                    }
                    updateStats();
                });
                
                //  task text
                const taskTextSpan = document.createElement('span');
                taskTextSpan.className = 'task-text';
                taskTextSpan.textContent = taskText;
                
                //  delete button
                const deleteButton = document.createElement('button');
                deleteButton.className = 'delete-button';
                deleteButton.textContent = 'Delete';
                deleteButton.addEventListener('click', function() {
                    if (checkbox.checked) {
                        completedTasks--;
                    }
                    taskItem.remove();
                    totalTasks--;
                    updateStats();
                    
                    // Show empty list message if no tasks
                    if (totalTasks === 0) {
                        const emptyListItem = document.createElement('li');
                        emptyListItem.className = 'empty-list';
                        emptyListItem.textContent = 'No tasks yet. Add one above!';
                        taskList.appendChild(emptyListItem);
                    }
                });
                
                // append elements to task item
                taskItem.appendChild(checkbox);
                taskItem.appendChild(taskTextSpan);
                taskItem.appendChild(deleteButton);
                

                taskList.appendChild(taskItem);
                
                taskInput.value = '';
                taskInput.focus();
                
                totalTasks++;
                updateStats();
            }
        }
        
        // update statistics
        function updateStats() {
            totalTasksSpan.textContent = `Total tasks: ${totalTasks}`;
            completedTasksSpan.textContent = `Completed: ${completedTasks}`;
        }
        
        addButton.addEventListener('click', addTask);
        taskInput.addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                addTask();
            }
        });
    </script>
</body>
</html>
```

## Solution 5


```html 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Carousel</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f9f9f9;
            color: #333;
        }
        
        h1 {
            text-align: center;
            margin-bottom: 30px;
            color: #2c3e50;
        }
        
        .carousel-container {
            position: relative;
            width: 100%;
            height: 400px;
            overflow: hidden;
            border-radius: 8px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.15);
        }
        
        .carousel-track {
            display: flex;
            transition: transform 0.5s ease-in-out;
            height: 100%;
        }
        
        .carousel-slide {
            min-width: 100%;
            height: 100%;
            background-position: center;
            background-size: cover;
            background-repeat: no-repeat;
        }
        
        .carousel-caption {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            background-color: rgba(0,0,0,0.5);
            color: white;
            padding: 15px;
            text-align: center;
        }
        
        .carousel-nav {
            display: flex;
            justify-content: center;
            margin-top: 15px;
        }
        
        .carousel-indicator {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background-color: #bbb;
            margin: 0 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .carousel-indicator.active {
            background-color: #3498db;
        }
        
        .carousel-button {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background-color: rgba(255,255,255,0.7);
            border: none;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            font-size: 18px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0.7;
            transition: opacity 0.3s;
        }
        
        .carousel-button:hover {
            opacity: 1;
        }
        
        .prev-button {
            left: 10px;
        }
        
        .next-button {
            right: 10px;
        }
        
        .auto-play-control {
            display: flex;
            justify-content: center;
            align-items: center;
            margin-top: 15px;
        }
        
        .auto-play-button {
            background-color: #3498db;
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 4px;
            cursor: pointer;
            margin: 0 10px;
        }
        
        .auto-play-button:hover {
            background-color: #2980b9;
        }
    </style>
</head>
<body>
    <h1>Image Carousel</h1>
    
    <div class="carousel-container" id="carousel">
        <div class="carousel-track" id="carouselTrack">
            <!-- Images will be added dynamically -->
        </div>
        
        <div class="carousel-caption" id="caption"></div>
        
        <button class="carousel-button prev-button" id="prevButton">←</button>
        <button class="carousel-button next-button" id="nextButton">→</button>
    </div>
    
    <div class="carousel-nav" id="carouselNav">
        <!-- Indicators will be added dynamically -->
    </div>
    
    <div class="auto-play-control">
        <button class="auto-play-button" id="autoPlayButton">Start Auto Play</button>
        <span id="timerDisplay"></span>
    </div>
    
    <script>
        // Image data
        const images = [
            {
                url: "https://plus.unsplash.com/premium_photo-1666863909125-3a01f038e71f?q=80&w=1986&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
                caption: "Beautiful Mountain Landscape"
            },
            {
                url: "https://plus.unsplash.com/premium_photo-1690576837108-3c8343a1fc83?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
                caption: "Ocean Sunset View"
            },
            {
                url: "https://images.unsplash.com/photo-1473448912268-2022ce9509d8?q=80&w=2041&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
                caption: "Autumn Forest Path"
            },
            {
                url: "https://plus.unsplash.com/premium_photo-1680466057202-4aa3c6329758?q=80&w=2138&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
                caption: "Urban City Skyline"
            }
        ];
        
        // Get DOM elements
        const carouselTrack = document.getElementById('carouselTrack');
        const caption = document.getElementById('caption');
        const prevButton = document.getElementById('prevButton');
        const nextButton = document.getElementById('nextButton');
        const carouselNav = document.getElementById('carouselNav');
        const autoPlayButton = document.getElementById('autoPlayButton');
        const timerDisplay = document.getElementById('timerDisplay');
        
        // Set up variables
        let currentIndex = 0;
        let autoPlayInterval;
        let timer = 5;
        
        // Initialize carousel
        function initCarousel() {
            // Create slides
            images.forEach((image, index) => {
                // Create slide
                const slide = document.createElement('div');
                slide.className = 'carousel-slide';
                slide.style.backgroundImage = `url(${image.url})`;
                carouselTrack.appendChild(slide);
                
                // Create indicator
                const indicator = document.createElement('div');
                indicator.className = 'carousel-indicator';
                if (index === 0) {
                    indicator.classList.add('active');
                }
                indicator.addEventListener('click', () => {
                    goToSlide(index);
                });
                carouselNav.appendChild(indicator);
            });
            
            // Set initial caption
            caption.textContent = images[0].caption;
        }
        
        // Go to specific slide
        function goToSlide(index) {
            currentIndex = index;
            updateCarousel();
        }
        
        // Update carousel display
        function updateCarousel() {
            // Update track position
            carouselTrack.style.transform = `translateX(-${currentIndex * 100}%)`;
            
            // Update caption
            caption.textContent = images[currentIndex].caption;
            
            // Update indicators
            const indicators = document.querySelectorAll('.carousel-indicator');
            indicators.forEach((indicator, index) => {
                if (index === currentIndex) {
                    indicator.classList.add('active');
                } else {
                    indicator.classList.remove('active');
                }
            });
            
            // Reset timer if auto-play is active
            if (autoPlayInterval) {
                timer = 5;
                updateTimerDisplay();
            }
        }
        
        // Go to next slide
        function nextSlide() {
            currentIndex = (currentIndex + 1) % images.length;
            updateCarousel();
        }
        
        // Go to previous slide
        function prevSlide() {
            currentIndex = (currentIndex - 1 + images.length) % images.length;
            updateCarousel();
        }
        
        // Toggle auto play
        function toggleAutoPlay() {
            if (autoPlayInterval) {
                // Stop auto play
                clearInterval(autoPlayInterval);
                autoPlayInterval = null;
                autoPlayButton.textContent = 'Start Auto Play';
                timerDisplay.textContent = '';
            } else {
                // Start auto play
                timer = 5;
                updateTimerDisplay();
                autoPlayButton.textContent = 'Stop Auto Play';
                autoPlayInterval = setInterval(() => {
                    timer--;
                    updateTimerDisplay();
                    if (timer <= 0) {
                        nextSlide();
                    }
                }, 1000);
            }
        }
        
        // Update timer display
        function updateTimerDisplay() {
            if (autoPlayInterval) {
                timerDisplay.textContent = `Next slide in ${timer}s`;
            }
        }
        
        // Add event listeners
        prevButton.addEventListener('click', prevSlide);
        nextButton.addEventListener('click', nextSlide);
        autoPlayButton.addEventListener('click', toggleAutoPlay);
        
        // Initialize carousel
        initCarousel();
    </script>
</body>
</html>
```



## Solution 6

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Enhanced Digital & Analog Clock</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            background: linear-gradient(135deg, #1e3c72, #2a5298);
            color: white;
            padding: 20px;
        }

        .container {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 30px;
            background: rgba(255, 255, 255, 0.1);
            padding: 30px;
            border-radius: 20px;
            backdrop-filter: blur(10px);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
        }

        h2 {
            font-size: 2.5rem;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .clock {
            width: 300px;
            height: 300px;
            position: relative;
            background: rgba(255, 255, 255, 0.1);
            border: 10px solid rgba(255, 255, 255, 0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 0 30px rgba(0, 0, 0, 0.1);
        }

        .clock::before {
            content: '';
            position: absolute;
            width: 15px;
            height: 15px;
            background: white;
            border-radius: 50%;
            z-index: 10;
        }

        .clock .number {
            position: absolute;
            width: 100%;
            height: 100%;
            text-align: center;
            transform: rotate(var(--rotation));
            font-size: 1.5rem;
            padding: 18px;
        }

        .clock .number span {
            display: inline-block;
            transform: rotate(calc(var(--rotation) * -1));
        }

        .hand {
            position: absolute;
            bottom: 50%;
            transform-origin: bottom;
            border-radius: 4px;
            transform: translateX(-50%) rotate(0deg);
            transition: transform 0.2s cubic-bezier(0.4, 2.08, 0.55, 0.44);
        }

        .hour {
            width: 8px;
            height: 30%;
            background: #ff9800;
            left: 50%;
        }

        .minute {
            width: 6px;
            height: 40%;
            background: #03a9f4;
            left: 50%;
        }

        .second {
            width: 4px;
            height: 45%;
            background: #f44336;
            left: 50%;
        }

        .digital-clock {
            font-size: 3.5rem;
            font-weight: bold;
            padding: 20px 40px;
            background: rgba(0, 0, 0, 0.4);
            border-radius: 15px;
            min-width: 300px;
            text-align: center;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .date {
            font-size: 1.2rem;
            margin-top: 10px;
            opacity: 0.8;
        }

        @media (min-width: 768px) {
            .container {
                flex-direction: row;
                gap: 50px;
            }
        }
    </style>
</head>
<body>
    <h2>Enhanced Clock</h2>

    <div class="container">
        <div class="clock">
            <div class="hand hour"></div>
            <div class="hand minute"></div>
            <div class="hand second"></div>
        </div>

        <div>
            <div class="digital-clock">00:00:00</div>
            <div class="date"></div>
        </div>
    </div>

    <script>
        const digitalClock = document.querySelector('.digital-clock');
        const dateDisplay = document.querySelector('.date');
        const hourHand = document.querySelector('.hour');
        const minuteHand = document.querySelector('.minute');
        const secondHand = document.querySelector('.second');
        const clock = document.querySelector('.clock');

        // add clock numbers
        for (let i = 1; i <= 12; i++) {
            const number = document.createElement('div');
            number.className = 'number';
            number.style.setProperty('--rotation', `${i * 30}deg`);
            number.innerHTML = `<span>${i}</span>`;
            clock.appendChild(number);
        }

        function updateTime() {
            const now = new Date();
            const hours = now.getHours();
            const minutes = now.getMinutes();
            const seconds = now.getSeconds();

            // update Digital Clock
            digitalClock.textContent = `${String(hours).padStart(2, '0')}:${String(minutes).padStart(2, '0')}:${String(seconds).padStart(2, '0')}`;

            // update Date
            const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
            dateDisplay.textContent = now.toLocaleDateString(undefined, options);

            // update Analog Clock
            const hourDeg = (hours % 12) * 30 + minutes * 0.5;
            const minuteDeg = minutes * 6 + seconds * 0.1;
            const secondDeg = seconds * 6;

            hourHand.style.transform = `translateX(-50%) rotate(${hourDeg}deg)`;
            minuteHand.style.transform = `translateX(-50%) rotate(${minuteDeg}deg)`;
            secondHand.style.transform = `translateX(-50%) rotate(${secondDeg}deg)`;
        }

        setInterval(updateTime, 1000);
        updateTime();
    </script>
</body>
</html>
```

## Solution 7

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Slick Accordion</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }

        body {
            min-height: 100vh;
            display: grid;
            place-items: center;
            background: #f0f2f5;
        }

        .container {
            width: 90%;
            max-width: 600px;
            background: white;
            padding: 2rem;
            border-radius: 12px;
            box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
        }

        h2 {
            color: #1a1a1a;
            margin-bottom: 1.5rem;
            font-size: 1.5rem;
            text-align: center;
        }

        .accordion-item {
            background: white;
            margin-bottom: 1rem;
            border-radius: 8px;
            overflow: hidden;
            border: 1px solid #e1e1e1;
        }

        .accordion-button {
            width: 100%;
            padding: 1rem;
            background: #4a90e2;
            color: white;
            border: none;
            text-align: left;
            display: flex;
            justify-content: space-between;
            align-items: center;
            cursor: pointer;
            transition: 0.3s ease;
        }

        .accordion-button:hover {
            background: #357abd;
        }

        .accordion-content {
            max-height: 0;
            padding: 0 1rem;
            background: white;
            overflow: hidden;
            transition: all 0.3s ease-out;
        }

        .accordion-content p {
            padding: 1rem 0;
            color: #666;
            line-height: 1.5;
        }

        .arrow {
            transition: transform 0.3s ease;
        }

        .active .arrow {
            transform: rotate(180deg);
        }

        .active .accordion-content {
            max-height: 200px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Simple Accordion</h2>
        <div class="accordion">
            <div class="accordion-item">
                <button class="accordion-button">
                    About Us
                    <span class="arrow">↓</span>
                </button>
                <div class="accordion-content">
                    <p>We are a company dedicated to creating amazing web experiences. Our team works tirelessly to bring you the best solutions.</p>
                </div>
            </div>

            <div class="accordion-item">
                <button class="accordion-button">
                    Services
                    <span class="arrow">↓</span>
                </button>
                <div class="accordion-content">
                    <p>We offer web design, development, and consulting services to help your business grow online.</p>
                </div>
            </div>

            <div class="accordion-item">
                <button class="accordion-button">
                    Contact
                    <span class="arrow">↓</span>
                </button>
                <div class="accordion-content">
                    <p>Get in touch with us through email or phone. We're always happy to help with your projects.</p>
                </div>
            </div>
        </div>
    </div>

    <script>
        const accordionItems = document.querySelectorAll('.accordion-item');
        
        accordionItems.forEach(item => {
            const button = item.querySelector('.accordion-button');
            
            button.addEventListener('click', () => {
                const isActive = item.classList.contains('active');
                accordionItems.forEach(item => item.classList.remove('active'));
                
                if (!isActive) {
                    item.classList.add('active');
                }
            });
        });
    </script>
</body>
</html>
```


## Solution 8

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Shopping Cart</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .products {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .product {
            border: 1px solid #ddd;
            padding: 15px;
            border-radius: 8px;
            text-align: center;
        }

        .product img {
            width: 100%;
            max-width: 150px;
            height: auto;
        }

        .cart {
            border: 1px solid #ddd;
            padding: 20px;
            border-radius: 8px;
        }

        .cart-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px 0;
            border-bottom: 1px solid #eee;
        }

        .quantity-controls {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        button {
            padding: 5px 10px;
            cursor: pointer;
        }

        .empty-cart {
            text-align: center;
            color: #666;
            padding: 20px;
        }
    </style>
</head>
<body>
    <h1>Simple Shop</h1>
    
    <div class="products">
        <div class="product">
            <img src="https://imgs.search.brave.com/Q8N1hgmCdmKvrapcnNXYFu1xDCgiw1XzYJiQ7ory7VI/rs:fit:500:0:0:0/g:ce/aHR0cHM6Ly90NC5m/dGNkbi5uZXQvanBn/LzA5LzkxLzcxLzg5/LzM2MF9GXzk5MTcx/ODk0M19EVlo5RzJD/SG40NjJlaVVnMmpH/dklCQzNycDNrOElT/WS5qcGc" alt="Product 1">
            <h3>T-Shirt</h3>
            <p>$19.99</p>
            <button onclick="addToCart('T-Shirt', 19.99)">Add to Cart</button>
        </div>
        <div class="product">
            <img src="https://imgs.search.brave.com/icgN7FZcrVNjzmbtHY3-JQYUCgEqOqu6i44LsdXMtNw/rs:fit:500:0:0:0/g:ce/aHR0cHM6Ly93d3cu/d2hpdGVob3VzZWJs/YWNrbWFya2V0LmNv/bS9fYXNzZXRzL2Nt/cy92My9hc3NldHMv/Ymx0NmFkMTM5ZjRm/ZTE4YTE1Yi9ibHRh/ZWM5NzhkMzI0NWEx/ODYxLzY3NDVkMTgw/N2RiNGExNDc2YmVj/NWUyOS80XygxNCku/anBnP2ltd2lkdGg9/Mzg0MCZxdWFsaXR5/PTgw" alt="Product 2">
            <h3>Jeans</h3>
            <p>$49.99</p>
            <button onclick="addToCart('Jeans', 49.99)">Add to Cart</button>
        </div>
        <div class="product">
            <img src="https://assets.adidas.com/images/w_766,h_766,f_auto,q_auto,fl_lossy,c_fill,g_auto/1728c1f21fbc41868170e24edb30777e_9366/samba-og-shoes.jpg" alt="Product 3">
            <h3>Sneakers</h3>
            <p>$79.99</p>
            <button onclick="addToCart('Sneakers', 79.99)">Add to Cart</button>
        </div>
        <div class="product">
            <img src="https://imgs.search.brave.com/5-_HHr1WiVcP9Gxiikg5Pqomy0orJVtFXTEwiovOfx0/rs:fit:500:0:0:0/g:ce/aHR0cHM6Ly9tZWRp/YS5nZXR0eWltYWdl/cy5jb20vaWQvMTcz/NjI0NDEwL3Bob3Rv/L25ldy15ZWFycy1o/YXQuanBnP3M9NjEy/eDYxMiZ3PTAmaz0y/MCZjPXdBMTF6N1NT/VlhwSjUwakxaQUNF/UzdoWU44SWY4cW5a/eFRVV3lRM1Q4b0k9" alt="Product 4">
            <h3>Hat</h3>
            <p>$24.99</p>
            <button onclick="addToCart('Hat', 24.99)">Add to Cart</button>
        </div>
    </div>

    <div class="cart">
        <h2>Shopping Cart</h2>
        <div id="cart-items">
            <div class="empty-cart">Cart is empty</div>
        </div>
        <div id="cart-total">
            <h3>Total: $0.00</h3>
        </div>
    </div>

    <script>
        let cart = {};
        
        function addToCart(name, price) {
            if (cart[name]) {
                cart[name].quantity++;
            } else {
                cart[name] = {
                    price: price,
                    quantity: 1
                };
            }
            updateCart();
        }

        function removeFromCart(name) {
            delete cart[name];
            updateCart();
        }

        function updateQuantity(name, delta) {
            cart[name].quantity += delta;
            if (cart[name].quantity <= 0) {
                removeFromCart(name);
            }
            updateCart();
        }

        function updateCart() {
            const cartItems = document.getElementById('cart-items');
            const cartTotal = document.getElementById('cart-total');
            let total = 0;

            if (Object.keys(cart).length === 0) {
                cartItems.innerHTML = '<div class="empty-cart">Cart is empty</div>';
                cartTotal.innerHTML = '<h3>Total: $0.00</h3>';
                return;
            }

            let html = '';
            for (let name in cart) {
                const item = cart[name];
                const subtotal = item.price * item.quantity;
                total += subtotal;

                html += `
                    <div class="cart-item">
                        <span>${name}</span>
                        <div class="quantity-controls">
                            <button onclick="updateQuantity('${name}', -1)">-</button>
                            <span>${item.quantity}</span>
                            <button onclick="updateQuantity('${name}', 1)">+</button>
                            <span>$${subtotal.toFixed(2)}</span>
                            <button onclick="removeFromCart('${name}')">Remove</button>
                        </div>
                    </div>
                `;
            }

            cartItems.innerHTML = html;
            cartTotal.innerHTML = `<h3>Total: $${total.toFixed(2)}</h3>`;
        }
    </script>
</body>
</html>
```

## Solution 9

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sliding Menu</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
        }

        .panel {
            position: fixed;
            top: 0;
            right: -360px; 
            width: 300px;
            height: 100%;
            background: #f1f1f1;
            transition: all 0.3s ease;
            padding: 20px;
            box-shadow: -2px 0 5px rgba(0,0,0,0.2);
        }

        .panel.active {
            right: 0; 
        }

        .toggle-btn {
            padding: 10px 20px;
            background: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            margin: 20px;
            font-size: 16px;
        }

        .toggle-btn:hover {
            background: #45a049;
        }

        .close-btn {
            position: absolute;
            top: 10px;
            right: 10px;
            padding: 5px 10px;
            background: #ff4444;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        .close-btn:hover {
            background: #ff0000;
        }

        .menu-item {
            padding: 15px;
            margin: 5px 0;
            background: white;
            cursor: pointer;
            border-radius: 4px;
            transition: background 0.2s;
        }

        .menu-item:hover {
            background: #e0e0e0;
        }

        .content {
            padding: 20px;
        }
    </style>
</head>
<body>
    <div class="content">
        <h1>Main Content</h1>
        <button class="toggle-btn">Open Menu</button>
        <p>Click the button to open the sliding menu</p>
    </div>

    <div class="panel">
        <button class="close-btn">X</button>
        <h2>Menu Items</h2>
        <div class="menu-item">Home</div>
        <div class="menu-item">About</div>
        <div class="menu-item">Services</div>
        <div class="menu-item">Contact</div>
    </div>

    <script>

        const toggleBtn = document.querySelector('.toggle-btn');
        const panel = document.querySelector('.panel');
        const closeBtn = document.querySelector('.close-btn');
        const menuItems = document.querySelectorAll('.menu-item');


        toggleBtn.addEventListener('click', () => {
            panel.classList.add('active');
        });


        closeBtn.addEventListener('click', () => {
            panel.classList.remove('active');
        });


        menuItems.forEach(item => {
            item.addEventListener('click', () => {
                alert('You clicked: ' + item.textContent);
                panel.classList.remove('active');
            });
        });

        document.addEventListener('click', (e) => {
            if (!panel.contains(e.target) && !toggleBtn.contains(e.target)) {
                panel.classList.remove('active');
            }
        });
    </script>
</body>
</html>
```

## Solution 10

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Memory Card Game</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            background: #f0f0f0;
        }

        .game-container {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
            margin: 20px;
            perspective: 1000px;
        }

        .card {
            width: 100px;
            height: 100px;
            position: relative;
            transform-style: preserve-3d;
            transition: transform 0.5s;
            cursor: pointer;
        }

        .card.flipped {
            transform: rotateY(180deg);
        }

        .card-front, .card-back {
            position: absolute;
            width: 100%;
            height: 100%;
            backface-visibility: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2em;
            border-radius: 8px;
        }

        .card-front {
            background: #2196F3;
            color: white;
        }

        .card-back {
            background: white;
            transform: rotateY(180deg);
            border: 2px solid #2196F3;
        }

        .stats {
            margin: 20px;
            text-align: center;
        }

        button {
            padding: 10px 20px;
            font-size: 1em;
            cursor: pointer;
            background: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
        }
    </style>
</head>
<body>
    <h1>Memory Game</h1>
    <div class="stats">
        <p>Moves: <span id="moves">0</span></p>
        <p>Time: <span id="time">0:00</span></p>
    </div>
    <div class="game-container" id="gameContainer"></div>
    <button onclick="restartGame()">Restart Game</button>

    <script>
        const emojis = ['🐶', '🐱', '🐭', '🐹', '🐰', '🦊', '🐻', '🐼'];
        let cards = [...emojis, ...emojis];
        let moves = 0;
        let timer = 0;
        let timerInterval;
        let flippedCards = [];
        let matchedPairs = 0;

        function shuffleCards() {
            for (let i = cards.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [cards[i], cards[j]] = [cards[j], cards[i]];
            }
        }

        function createCard(emoji, index) {
            const card = document.createElement('div');
            card.className = 'card';
            card.dataset.index = index;
            
            card.innerHTML = `
                <div class="card-front">?</div>
                <div class="card-back">${emoji}</div>
            `;
            
            card.addEventListener('click', () => flipCard(card));
            return card;
        }

        function flipCard(card) {
            if (flippedCards.length === 2 || card.classList.contains('flipped') || 
                card.classList.contains('matched')) return;

            card.classList.add('flipped');
            flippedCards.push(card);

            if (flippedCards.length === 2) {
                moves++;
                document.getElementById('moves').textContent = moves;
                checkMatch();
            }
        }

        function checkMatch() {
            const [card1, card2] = flippedCards;
            const match = cards[card1.dataset.index] === cards[card2.dataset.index];

            if (match) {
                card1.classList.add('matched');
                card2.classList.add('matched');
                matchedPairs++;
                if (matchedPairs === 8) endGame();
            } else {
                setTimeout(() => {
                    card1.classList.remove('flipped');
                    card2.classList.remove('flipped');
                }, 1000);
            }

            flippedCards = [];
        }

        function startTimer() {
            timerInterval = setInterval(() => {
                timer++;
                const minutes = Math.floor(timer / 60);
                const seconds = timer % 60;
                document.getElementById('time').textContent = 
                    `${minutes}:${seconds.toString().padStart(2, '0')}`;
            }, 1000);
        }

        function endGame() {
            clearInterval(timerInterval);
            setTimeout(() => {
                alert(`Congratulations! You won in ${moves} moves and ${timer} seconds!`);
            }, 500);
        }

        function restartGame() {
            clearInterval(timerInterval);
            timer = 0;
            moves = 0;
            matchedPairs = 0;
            flippedCards = [];
            document.getElementById('moves').textContent = '0';
            document.getElementById('time').textContent = '0:00';
            
            shuffleCards();
            const gameContainer = document.getElementById('gameContainer');
            gameContainer.innerHTML = '';
            cards.forEach((emoji, index) => {
                gameContainer.appendChild(createCard(emoji, index));
            });
            startTimer();
        }

        restartGame();
    </script>
</body>
</html>
```