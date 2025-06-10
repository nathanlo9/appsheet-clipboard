# ADR 001: Use of JavaScript and HTML for Clipboard App

## Status
Accepted

## Context
The project is a small utility that enables a Google AppSheet app to write text to the user's clipboard. The primary requirements are:
- Simple and lightweight implementation
- Compatibility with web browsers
- Ability to be invoked via a URL with parameters

Given these requirements, the choice of technology needed to support client-side execution and interaction with the clipboard API.

## Decision
We decided to implement the application using JavaScript and HTML. JavaScript provides direct access to the Clipboard API and allows for dynamic interaction with the browser. HTML serves as the container for the script and provides the necessary structure for deployment.

## Consequences
- The app is lightweight and easy to deploy as a static HTML file.
- It can be hosted on any web server or embedded in other applications.
- The solution is limited to environments where JavaScript is enabled and supported.
- No server-side processing is required, reducing complexity and cost.

## Date
2024-10-10

## Participants
Nathan Lockard
