---
layout: home
---
Hi, I'm Jack Stevenson. As of 2025, I'm a scientist on the loose. Until 2025, I was a graduate student and then a postdoc in the [Shokat lab](https://shokatlab.ucsf.edu) at UCSF, where I worked mostly on developing small molecule cancer drugs. I like usable science: thorough protocols, clear writing, and reproducible data analysis.

This website is intended for sharing resources I find useful. Check out some of my favorite tools on my [Resources page]({{ site.url }}/resources).

<br><br><br>

Suggestions?

Think I should be different? Think this website should be different? I want to know about it.
<!-- HTML Form with embedded CSS -->
<style>
  #my-form-status {
    margin-left: 10px;
    padding: 5px;
    opacity: 0;
    transition: opacity 0.5s ease-in-out;
  }
  #my-form-status.visible {
    opacity: 1;
  }
</style>

<form id="my-form" action="https://formspree.io/f/xovazawa" method="POST">
  <label for="name">Name (optional):</label>
  <input type="text" id="name" name="name">
  <br>
  <label for="email">Email (optional):</label>
  <input type="email" id="email" name="email">
  <br>
  <label for="message">Message:</label>
  <textarea id="message" name="message" required></textarea>

  <div style="display: flex; align-items: center;">
    <button type="submit">Ship it</button>
    <span id="my-form-status"></span>
  </div>
</form>

<!-- JavaScript for form handling -->
<script>
  document.addEventListener('DOMContentLoaded', function() {
    var form = document.getElementById("my-form");
    var status = document.getElementById("my-form-status");
    var statusTimeout;
    
    function updateStatus(message, isError = false) {
      clearTimeout(statusTimeout);
      status.textContent = message;
      status.style.color = isError ? "red" : "green";
      status.classList.add('visible');
      
      statusTimeout = setTimeout(() => {
        status.classList.remove('visible');
      }, 2000);
    }
    
    async function handleSubmit(event) {
      event.preventDefault();
      updateStatus("Sending...");
      
      var data = new FormData(event.target);
      try {
        let response = await fetch(event.target.action, {
          method: form.method,
          body: data,
          headers: {
              'Accept': 'application/json'
          }
        });
        
        let result = await response.json();
        
        if (response.ok) {
          updateStatus("Sent");
          form.reset();
        } else {
          updateStatus(result.errors ? result.errors.map(error => error.message).join(", ") : "Form error. Please send an email instead. ", true);
        }
      } catch (error) {
        updateStatus("Form error. Please send an email instead. " + error.message, true);
      }
    }
    
    form.addEventListener("submit", handleSubmit);
  });
</script>