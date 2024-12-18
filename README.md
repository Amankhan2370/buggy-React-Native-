const sortUsersByScore = (users) => {
  return [...users].sort((a, b) => b.score - a.score);
};

Explanation of Fixes;
1. Refactored Sorting Logic:
What was done: A separate function called sortUsersByScore was created to handle sorting the users by their scores in descending order.
Why it's helpful: Breaking this out into its own function makes the code easier to read and maintain. Instead of cramming the sorting logic directly in your main code, you’ve made it reusable and cleaner. It takes the input (users) and gives back a properly sorted list.
2. Avoided State Mutation: 
What was done: Instead of directly modifying the original users array (which could mess up how React tracks changes), you created a copy of the array using the spread operator ([...users]) before sorting.
Why it's important: React works best when you don’t change (or "mutate") the original state directly. By copying the array, React can clearly see what’s changed when you update the state later. This ensures the app updates properly and avoids potential bugs.
3. Updated State with Sorted Array: 
What was done: After sorting the copied array, the users state was updated with the newly sorted array.
Why it matters: React’s setState (or equivalent) is designed to take a new version of the state and re-render the UI accordingly. By providing the sorted array as the new state, React knows what’s different and updates the UI correctly. This avoids breaking React's rules about managing state.


