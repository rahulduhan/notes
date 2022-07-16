```html
<!DOCTYPE html>

<html lang="en">

  

<head>

<meta charset="UTF-8">

<meta name="author" content="XDRD">

<meta name="description" content="OS Form">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<link rel="stylesheet" href="styles.css" />

<style>

:root {

--color-white: #FFFEFB;

--color-black: #2D2D2D;

--color-off-white: #f7f7f7;

--color-pastal-green: #baffc9;

--color-pastal-yellow: #ffffba;

--color-pastal-blue: #bae1ff;

}

  

header {

text-align: center;

}

  

h1 {

color: var(--color-pastal-green);

}

  

#description {

color: var(--color-pastal-blue)

}

  

body {

background-color: var(--color-black);

color: var(--color-pastal-yellow)

}

</style>

  

<title>OS Form</title>

</head>

  

<body>

<header>

<h1 id="title">OS Form</h1>

<p id="description"> Thank you for taking the time to help us improve the platform</p>

</header>

<main>

<form id="survey-form">

<fieldset>

<label class="label-input" id="name-label">Name</label>

<input type="text" name="name" id="name" placeholder="Enter your name" required/>

<br>

<label class="label-input" id="email-label">Email</label>

<input type="email" name="email" id="email" placeholder="Enter your email" required/>

<br>

<label class="label-input" id="number-label" >Age</label>

<input type="number" name="name" id="number" placeholder="Enter age" required min="16" max="120"/>

<br>

<select id="dropdown" name="terminal" required>

<option disabled selected value>What terminal do you prefer?</option>

<option value="st">st - Simple Terminal</option>

<option value="alacritty">Alacritty</option>

</select>

<p>Which disto do you prefer</p>

<label><input type="radio" name="distro" value="arch"checked/>Arch btw</label>

<label><input type="radio" name="distro" value="void"/>Void</label>

<label><input type="radio" name="distro" value="gentoo"/>Gentoo</label>

<label><input type="radio" name="distro" value="lfs"/>LFS</label>

<p>You must agree to these facts</p>

<label><input type="checkbox" name="facts" value="mac" required />Macos is trash checked</label>

<label><input type="checkbox" name="facts" value="windows" required />Windows is creepy</label>

<label><input type="checkbox" name="facts" value="ubuntu" required />Ubuntu is sus</label>

<label>Comment

<textarea name="message" rows="3" cols="40" placeholder="leave a message"></textarea>

</label>

<input type="submit" id="submit" value="submit">

</form>

</main>

<footer>

</footer>

</body>

</html>
```
