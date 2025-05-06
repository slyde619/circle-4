---
layout: two-cols
---

# Promises and Async

<v-clicks>

- **Promises:** Objects representing eventual completion or failure of an async operation
- **.then() vs. async/await:** Two ways to handle asynchronous code
- **Challenge:** Managing multiple API calls and state updates

</v-clicks>

::right::

```js {all|1-6|8-14|all}
// Before: Promise chains
function fetchUserData(userId) {
  return fetch(`/api/users/${userId}`)
    .then(response => response.json())
    .then(user => fetch(`/api/posts?userId=${user.id}`))
    .then(response => response.json());
}

// After: Async/await
async function fetchUserData(userId) {
  const userResponse = await fetch(`/api/users/${userId}`);
  const user = await userResponse.json();
  const postsResponse = await fetch(`/api/posts?userId=${user.id}`);
  return await postsResponse.json();
}
```