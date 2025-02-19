

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

