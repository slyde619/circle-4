---
layout: two-cols
class: gap-8
---

# Forms

<v-clicks>

- **Form handling:** Capturing and processing user input
- **Key concepts:** form submission, validation, data collection
- **Project example:** User registration with validation

</v-clicks>

::right::

```js {all|1-5|6-11|12-17|18-23|all}
// Simple form validation code
function checkForm() {
  const email = document.getElementById('email').value;
  const password = document.getElementById('password').value;
  
  if (email === '') {
    document.getElementById('emailError').textContent = 
      'Please enter your email';
    return false;
  }
  
  if (!email.includes('@')) {
    document.getElementById('emailError').textContent = 
      'Email must contain @';
    return false;
  }
  
  if (password.length < 6) {
    document.getElementById('passwordError').textContent = 
      'Password must be at least 6 characters';
    return false;
  }
  
  return true;
}
```