#Event handling
#Buttn click
<button id="myButton">Click Me!</button>

<script>
  document.getElementById("myButton").addEventListener("click", function() {
    this.textContent = "You clicked me!";
  });
</script>

#Hover effect
<button id="hoverButton">Hover Over Me!</button>

<script>
  const button = document.getElementById("hoverButton");
  
  button.addEventListener("mouseover", function() {
    this.style.backgroundColor = "lightblue";
  });

  button.addEventListener("mouseout", function() {
    this.style.backgroundColor = "";
  });
</script>

#keypresses detection
<input type="text" id="inputField" placeholder="Type something..." />

<script>
  document.getElementById("inputField").addEventListener("keydown", function(event) {
    if (event.key === "Enter") {
      alert("You pressed Enter!");
    }
  });
</script>

#Long Press
<button id="doubleClickButton">Double Click Me!</button>

<script>
  const button = document.getElementById("doubleClickButton");

  // Double click
  button.addEventListener("dblclick", function() {
    alert("Double-clicked!");
  });

  // Long press detection
  let pressTimer;
  button.addEventListener("mousedown", function() {
    pressTimer = setTimeout(function() {
      alert("Long Pressed!");
    }, 2000); // 2 seconds
  });

  button.addEventListener("mouseup", function() {
    clearTimeout(pressTimer);
  });
</script>

# Interactive elements
#Button that changes color
<button id="colorButton">Change Color</button>

<script>
  document.getElementById("colorButton").addEventListener("click", function() {
    this.style.backgroundColor = "green";
    this.textContent = "Color Changed!";
  });
</script>

#Image gallery
<img id="galleryImage" src="image1.jpg" alt="Image" width="300" />
<button id="nextImage">Next Image</button>

<script>
  const images = ["image1.jpg", "image2.jpg", "image3.jpg"];
  let currentIndex = 0;

  document.getElementById("nextImage").addEventListener("click", function() {
    currentIndex = (currentIndex + 1) % images.length;
    document.getElementById("galleryImage").src = images[currentIndex];
  });
</script>

# Accordion-Style Content
<button class="accordion">Section 1</button>
<div class="panel">
  <p>This is the first section of content.</p>
</div>

<script>
  document.querySelectorAll(".accordion").forEach(button => {
    button.addEventListener("click", function() {
      const panel = this.nextElementSibling;
      panel.style.display = (panel.style.display === "block") ? "none" : "block";
    });
  });
</script>

#Form validation
# Required Field Check
<form id="myForm">
  <input type="text" id="username" required placeholder="Enter your username">
  <button type="submit">Submit</button>
</form>

<script>
  document.getElementById("myForm").addEventListener("submit", function(event) {
    const username = document.getElementById("username").value;
    if (!username) {
      alert("Username is required!");
      event.preventDefault(); // Prevent form submission
    }
  });
</script>

#Email Format Validation
<form id="emailForm">
  <input type="email" id="email" placeholder="Enter your email" required>
  <button type="submit">Submit</button>
</form>

<script>
  document.getElementById("emailForm").addEventListener("submit", function(event) {
    const email = document.getElementById("email").value;
    const emailPattern = /^[^ ]+@[^ ]+\.[a-z]{2,3}$/;
    if (!emailPattern.test(email)) {
      alert("Please enter a valid email address.");
      event.preventDefault();
    }
  });
</script>

# Password Length Validation
<form id="passwordForm">
  <input type="password" id="password" placeholder="Enter password" required>
  <button type="submit">Submit</button>
</form>

<script>
  document.getElementById("passwordForm").addEventListener("submit", function(event) {
    const password = document.getElementById("password").value;
    if (password.length < 8) {
      alert("Password must be at least 8 characters long.");
      event.preventDefault();
    }
  });
</script>

# Real-Time Feedback
<input type="text" id="feedbackField" placeholder="Type here..." />
<span id="feedbackMessage"></span>

<script>
  document.getElementById("feedbackField").addEventListener("input", function() {
    const feedbackMessage = document.getElementById("feedbackMessage");
    if (this.value.length < 5) {
      feedbackMessage.textContent = "Keep typing...";
      feedbackMessage.style.color = "red";
    } else {
      feedbackMessage.textContent = "Looks good!";
      feedbackMessage.style.color = "green";
    }
  });
</script>




