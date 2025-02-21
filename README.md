# Unresponsive Node.js Server

This repository demonstrates a common issue in Node.js where a long-running synchronous operation blocks the event loop, causing the server to become unresponsive.  The `server.js` file shows the problematic code, while `server-fixed.js` provides a solution using asynchronous operations.

## Problem

The original code executes a `while` loop that keeps the CPU busy for 5 seconds. This synchronous operation blocks the event loop, preventing Node.js from handling other requests during this time.  Any incoming requests will be queued but won't be processed until the loop completes, leading to an unresponsive server.

## Solution

The solution involves refactoring the long-running task to use asynchronous operations.  This allows Node.js to continue processing other requests concurrently.