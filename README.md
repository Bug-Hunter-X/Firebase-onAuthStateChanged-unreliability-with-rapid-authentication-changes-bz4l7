# Firebase onAuthStateChanged Unreliability with Rapid Authentication Changes

This repository demonstrates an uncommon bug in the Firebase Authentication SDK where the `onAuthStateChanged` listener may not reliably trigger when the authentication state changes rapidly. This often occurs due to quick successive sign-in/sign-out attempts or network instability.  The `unreliableAuth.js` file shows this problem, while `reliableAuth.js` offers a solution.

## Problem:

Rapid authentication state changes can cause the listener to miss events, leading to UI inconsistencies and unexpected application behavior. The `unreliableAuth.js` file showcases this issue. 

## Solution:

The `reliableAuth.js` file provides a solution using debouncing. The debounce function ensures that the listener only fires after a short delay, preventing multiple rapid calls and resolving the issue. This ensures that only the most recent authentication state triggers an update.