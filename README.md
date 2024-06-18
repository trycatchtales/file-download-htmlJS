
# File Download with Progress Bar

This project demonstrates how to create a stylish file download button with a progress bar using HTML, CSS, and JavaScript. When the button is clicked, the progress bar fills up, indicating the download progress, and then triggers the download of a file.

## Demo

![Demo](demo.gif)

## How It Works

1. **HTML**: Sets up the structure with a button and a progress bar.
2. **CSS**: Styles the button and progress bar for a clean and polished look.
3. **JavaScript**: Handles the progress bar animation and triggers the file download.

## Getting Started

### Prerequisites

- A web browser
- Basic knowledge of HTML, CSS, and JavaScript

### Installation

1. Clone the repository or download the ZIP file.
   ```sh
   git clone https://github.com/yourusername/file-download-progress-bar.git
   ```

2. Open the `index.html` file in your web browser to see the demo in action.

### Code Explanation

#### HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Download File with Progress Bar</title>
<style>
  body {
    font-family: 'Arial', sans-serif;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    margin: 0;
    background-color: #f7f7f7;
  }

  .progress-container {
    width: 50%;
    background-color: #ddd;
    border-radius: 20px;
    box-shadow: 0 4px 8px rgba(0,0,0,0.1);
    overflow: hidden; /* Ensures the inner bar stays within the rounded corners */
  }

  .progress-bar {
    width: 0%;
    height: 30px;
    background: linear-gradient(to right, #4CAF50, #81C784);
    text-align: center;
    line-height: 30px;
    color: white;
    transition: width 1s ease-in-out;
  }

  button {
    padding: 10px 20px;
    margin-bottom: 20px;
    border: none;
    border-radius: 5px;
    background-color: #4CAF50;
    color: white;
    cursor: pointer;
    font-size: 16px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.2);
  }

  button:hover {
    background-color: #45a049;
  }
</style>
</head>
<body>

<button onclick="startDownload()">Download File</button>
<div class="progress-container">
  <div class="progress-bar" id="progressBar">0%</div>
</div>

<script>
function startDownload() {
  const progressBar = document.getElementById('progressBar');
  let progress = 0;
  
  const interval = setInterval(() => {
    progress += 10;
    progressBar.style.width = `${progress}%`;
    progressBar.textContent = `${progress}%`;

    if (progress >= 100) {
      clearInterval(interval);
      triggerDownload('sample.txt'); // Update this to your file's URL
      resetProgressBar(progressBar);
    }
  }, 1000);
}

function triggerDownload(filename) {
  const a = document.createElement('a');
  a.href = filename;
  a.download = filename;
  document.body.appendChild(a);
  a.click();
  document.body.removeChild(a);
}

function resetProgressBar(progressBar) {
  setTimeout(() => {
    progressBar.style.width = '0%';
    progressBar.textContent = '0%';
  }, 2000);
}
</script>

</body>
</html>
```

### Usage

1. **HTML**: Create a button and a progress bar inside a `div` with the class `progress-container`.
2. **CSS**: Style the button and progress bar to make them look polished and visually appealing.
3. **JavaScript**: Implement the `startDownload` function to handle the progress bar animation and trigger the file download.

### Customization

- Update the `triggerDownload` function to point to the file you want to download by replacing `'sample.txt'` with your file URL.
- Adjust the progress bar increment speed by changing the interval duration in the `setInterval` function.

### Contributing

Feel free to fork the repository and make your own enhancements. Pull requests are welcome!



### Contact

Instagram , YouTube - [@trycatchtales]

Project Link: [https://github.com/yourusername/file-download-progress-bar](https://github.com/trycatchtales/file-download-htmlJS)
