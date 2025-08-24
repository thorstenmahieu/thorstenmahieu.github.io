---
layout: page
title: Contact
---


## Feedback
Send me a message or feedback 🤗

<form 
    action="https://formspree.io/f/movazowz"
    method="POST"
    >
  
  <label for="name">Name:</label>
  <input type="text" id="name" name="name" required>

  <label for="email">Email:</label>
  <input type="email" id="email" name="email" required>

  <label for="message">Message:</label>
  <textarea id="message" name="message" required></textarea>

  <button type="submit">Send Feedback</button>
</form>

<style>
    form {
    display: flex;
    flex-direction: column;
    max-width: 300px;
    margin: 0 auto;
    }
    label, input, textarea, button {
    margin-bottom: 10px;
    }
    textarea {
    height: 100px;
    }
</style>