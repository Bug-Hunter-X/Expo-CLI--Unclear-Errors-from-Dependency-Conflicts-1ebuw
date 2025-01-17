# Expo CLI: Unclear Errors from Dependency Conflicts

This repository demonstrates a common but difficult-to-debug issue in Expo CLI projects involving dependency conflicts or missing peer dependencies.  The problem often manifests as cryptic error messages during build or start commands, making it challenging to pinpoint the root cause.

## The Problem

Expo projects rely heavily on a properly configured `package.json` file.  Inconsistencies in dependencies (versions, missing peer dependencies) can lead to unexpected failures. The standard Expo CLI error messages aren't always sufficient to trace back to the conflicting packages.

## Reproduction

The `bug.js` file illustrates a simplified project setup that demonstrates the problem (see instructions below for setting up the project).  It will initially fail.  The solution is in `bugSolution.js`.

## Solution

The `bugSolution.js` file provides a corrected `package.json` addressing the dependency conflict.  Careful review of package.json, particularly its `dependencies` and `peerDependencies` sections, is crucial.

## How to Reproduce

1.  Clone this repository.
2.  Navigate to the project directory.
3.  Install the dependencies (as stated in bug.js package.json): `npm install`
4.  Attempt to start the Expo project using: `expo start` (This should fail.)
5.  Replace `bug.js`'s `package.json` file with the one from `bugSolution.js`
6.  Re-run `npm install` and `expo start`. (This should work.)

## Note

The specific dependencies involved in this issue can vary.  The example demonstrates a common scenario, but the pattern of unclear errors from dependency issues persists.