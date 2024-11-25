# Custom Countdown

This project showcases an interactive and responsive countdown timer, built as part of the course "JavaScript Web Projects: 20 Projects to Build Your Portfolio" by Zero To Mastery. Users can create a custom countdown with a title and a specific date, which dynamically updates and persists across sessions.

## Table of contents

- [Custom Countdown](#custom-countdown)
  - [Table of contents](#table-of-contents)
  - [Overview](#overview)
    - [Screenshot](#screenshot)
    - [Links](#links)
  - [My process](#my-process)
    - [Built with](#built-with)
    - [What I learned](#what-i-learned)
    - [Useful resources](#useful-resources)
  - [Author](#author)
  - [Acknowledgments](#acknowledgments)

## Overview

This project includes the following features:
- A form to input a title and select a date for the countdown.
- A live countdown timer that dynamically updates days, hours, minutes, and seconds.
- A "Complete" screen displayed when the countdown reaches zero.
- Persistent storage using localStorage to save and restore countdowns across sessions.
- Reset functionality to clear the countdown and start anew.
- A responsive design with a video background for a modern look.

### Screenshot

![](./screenshot.png)

### Links

- Live Site URL: [DT Code](https://custom-countdown.dtcode.se/)

## My process

### Built with

- HTML5: For semantic structure.
- CSS3: For responsive styling.
  - Flexbox for layout.
  - Custom properties (CSS variables) for consistent theming.
  - Media queries for mobile optimization.
- JavaScript (ES6+): For interactivity and functionality.
  - DOM manipulation.
  - Event handling.
  - LocalStorage for data persistence.
  - Dynamic updates with setInterval.

### What I learned

In this project, I gained experience with:
- Handling form inputs and validation for user data.
- Using setInterval for real-time updates in JavaScript.
- Creating persistent applications using localStorage to save and retrieve data.
- Manipulating the DOM dynamically to update countdown elements.
- Combining CSS overlays and video backgrounds for an engaging user interface.

Example code for updating the countdown dynamically:

```js
function updateDOM() {
    countdownActive = setInterval(() => {
        const now = new Date().getTime();
        const distance = countdownValue - now;

        const days = Math.floor(distance / day);
        const hours = Math.floor((distance % day) / hour);
        const minutes = Math.floor((distance % hour) / minute);
        const seconds = Math.floor((distance % minute) / second);

        // Hide Input and display countdown
        inputContainer.hidden = true;

        if (distance < 0) {
            // If countdown is complete
            countdownEl.hidden = true;
            clearInterval(countdownActive);
            completeElInfo.textContent = `${countdownTitle} finished on ${countdownDate}`;
            completeEl.hidden = false;
        } else {
            // Update countdown display
            countdownElTitle.textContent = `${countdownTitle}`;
            timeElements[0].textContent = `${days}`;
            timeElements[1].textContent = `${hours}`;
            timeElements[2].textContent = `${minutes}`;
            timeElements[3].textContent = `${seconds}`;
            completeEl.hidden = true;
            countdownEl.hidden = false;
        }
    }, second);
}
```

### Useful resources

- [MDN Web Docs: setInterval](https://developer.mozilla.org/en-US/docs/Web/API/Window/setInterval) - Helped with implementing real-time updates.
- [MDN Web Docs: LocalStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage) - Assisted in saving and restoring countdown data.
- [Google Fonts](https://fonts.google.com/) - Provided modern typography for the design.

## Author

- GitHub - [@dantvi](https://github.com/dantvi)
- LinkedIn - [@danieltving](https://www.linkedin.com/in/danieltving/)

## Acknowledgments

Special thanks to Zero To Mastery for the hands-on course that guided the creation of this project. Additional thanks to MDN Web Docs for their detailed and accessible documentation.
