# 10 DOM Questions

## Note
- For each question, please follow all the requirements. These are mandatory, though you may add additional features
- You may customize the UI differently as long as it meets all requirements
- Any creative solutions are welcome
- Use only HTML, CSS, and JavaScript (no frameworks or libraries)


## Question 1: Light Bulb Toggle

### Demo 

https://github.com/user-attachments/assets/68894f84-0a05-42de-97cc-243f6928e1fa

### Requirements:
- Create a webpage with a light bulb image or representation
- Implement a button that toggles the light bulb on and off
- When the bulb is on, it should be yellow/gold(or any other color) with a glow effect
- When the bulb is off, it should be gray with no glow
- The button text should update based on the current state (Turn On/Turn Off)
- Implement a dark mode effect for the page when the bulb is off


## Question 2: Change Text Color

### Demo 

https://github.com/user-attachments/assets/accc2233-8898-407e-963c-b83dcf2e93e0

### Requirements:

- Create a webpage with a heading that says "Change My Color!"
- Include 5 buttons: Red, Green, Blue, Purple(or any 4 colors you want) and Reset 
- When a color button is clicked, the heading's text color should change to that color
- The Reset button should change the text color back to black


## Question 3: Real-time Form Input Display

### Demo 

https://github.com/user-attachments/assets/2da9e4ba-2cbd-4b14-b5a9-1e7422f52cc9

### Requirements:
- Create a profile form with the following fields:
  - Name (text input)
  - Job Title (text input)
  - Age (number input)
  - Bio (textarea)
- Create a "Profile Preview" section that displays the entered information
- The preview should update in real-time as the user types
- If a field is empty, the preview should display "Not provided"

## Question 4: Task Management 

### Demo:

https://github.com/user-attachments/assets/4380c857-7c77-44bc-bbd5-bdcafcbedba2


### Requirements:

1. Task Management
   - Users should be able to add a new task by typing into an input field and clicking the "Add" button or pressing "Enter"
   - Each task should be displayed in a list with a checkbox and a delete button
   - Tasks should be removable by clicking the "Delete" button

2. Task Completion
   - Users should be able to mark tasks as completed by clicking the checkbox next to a task
   - Completed tasks should be visually distinguished (e.g., strikethrough text and different text color)
   - Users should be able to uncheck a completed task, reverting it to an incomplete state

3. Task List State
   - If there are no tasks, a message ("No tasks yet. Add one above!") should be displayed
   - Once a task is added, this message should disappear
   - If all tasks are deleted, the message should reappear

4. Task Statistics
   - The application should display the total number of tasks
   - The application should display the number of completed tasks
   - The statistics should update dynamically when tasks are added, completed, or deleted

## Question 5: Image Carousel Application 

### Demo:

https://github.com/user-attachments/assets/100ba10c-928e-4341-a899-c3ba2450c36b


### Requirements:

1. Image Display
   - The application should display a set of images in a carousel format
   - Only one image should be visible at a time
   - Each image should have a corresponding caption displayed at the bottom

2. Navigation Controls
   - Users should be able to navigate through the images using:
     - A "Next" button to move to the next image
     - A "Previous" button to move to the previous image
     - Clicking on an indicator to jump to a specific image

3. Automatic Slideshow
   - The application should support an auto-play mode where images cycle automatically
   - Users should be able to start and stop the auto-play mode using a button
   - A timer should be displayed, showing how many seconds remain before the next image transition

4. Indicators
   - There should be navigation dots (indicators) below the carousel
   - The active image's indicator should be highlighted
   - Clicking on an indicator should jump to the corresponding image


## Question 6: Enhanced Clock

### Demo

https://github.com/user-attachments/assets/1306c917-90bd-472f-ad83-92339f8ddf0e


### Requirements 
Requirements:

1. Digital Clock Display
   - Application should show current time in hours:minutes:seconds format
   - Time should update every second
   - Numbers should be padded with leading zeros (e.g., 01:05:08)
   - Display should use a clear, readable font

2. Analog Clock Face
   - Clock should display a circular face with numbers 1-12
   - Three hands should be present for hours, minutes, and seconds
   - Each hand should have distinct styling:
     - Hour hand: shortest and thickest
     - Minute hand: medium length and thickness
     - Second hand: longest and thinnest
   - Center point should be marked with a dot

3. Hand Movement
   - Second hand should move every second (6 degrees per second)
   - Minute hand should move smoothly (6 degrees per minute)
   - Hour hand should account for both hours and minutes in its position
   - Hands should rotate smoothly without jumping

4. Date Display
   - Current date should be shown below the clock
   - Date format should include day, month, and year


## Question 7: Accordion

### Demo

https://github.com/user-attachments/assets/d2e76751-36a2-4d22-bcce-ead498cb1695

### Requirements

1. Accordion Structure
   - Container should display multiple collapsible sections
   - Each section should have a header and content area 
   - Only one section should be open at a time
   - Sections should be visually separated

2. Section Headers
   - Headers should be clickable buttons
   - Each header should display:
     - Section title on the left
     - Dropdown arrow (▼) on the right
   - Headers should have hover effects
   - Arrow should rotate when section is open

3. Content Display
   - Content should be hidden by default
   - Content should appear with a fade-in animation
   - Content should have different styling from headers
   - Content area should adjust to text length

4. Interaction Behavior
   - Clicking a closed section should:
     - Open that section
     - Close any previously open section
   - Clicking an open section should:
     - Close that section
   - Only one section can be active at a time


## Question 8: Simple Shopping Cart


### Demo

https://github.com/user-attachments/assets/3d5de91d-cad7-4923-806a-df68c0e2ff53


### Requirements:

1. Product Display
   - Display at least 4 products with:
     - Product name
     - Price
     - "Add to Cart" button
   - Each product should have a simple image (can use placeholder images)

2. Cart Functionality
   - Users should be able to:
     - Add items to cart
     - Remove items from cart
     - Adjust quantity of items (increase/decrease)
   - Cart should show:
     - List of added items with their quantities
     - Individual item subtotals
     - Cart total


## Question 9: Sliding Menu

### Demo

https://github.com/user-attachments/assets/5f8400fe-5b84-4b2f-931b-0ab6c3ee728a

### Requirements:

1. Menu Structure
   - Create slide-out menu panel from right side
   - Panel should contain at least 4 menu items
   - Include a clear navigation hierarchy 
   - Menu panel should have a header/title
   - Include close button in top right corner

2. Interaction Features
   - Toggle button to open menu
   - Close button to dismiss menu
   - Click on menu items should:
     - Show which item was clicked through an alert message
     - Close the menu automatically
   - Click outside menu should close it
   - Prevent menu from being partially visible when closed

3. UX
   - Smooth transitions
   - No content shifting when menu opens/closes
   - Clear visual feedback on interactions
   - Proper cursor indicators for clickable elements
   - No scrolling issues when menu is open


# Question 10: 
## Question: Interactive Memory Card Game

### Requirements:
1. Create a memory matching card game where:
   - Display a 4x4 grid of cards (8 pairs)
   - Cards should flip when clicked
   - Match pairs to win
   - Track moves and time

2. Game Features:
   - Cards should shuffle on game start
   - Show victory message when all pairs are matched through a alert message 
   - Include restart button
   - Display score based on moves and time taken

3. Emojis(optional)
   - use any emojis or use below ones 
   - Use these 8 emojis for the cards: '🐶', '🐱', '🐭', '🐹', '🐰', '🦊', '🐻', '🐼'
