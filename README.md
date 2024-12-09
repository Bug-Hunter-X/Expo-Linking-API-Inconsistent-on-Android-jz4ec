# Expo Linking API Inconsistency on Android

This repository demonstrates a bug in Expo's `Linking` API on Android where `Linking.addEventListener` for deep links fails to trigger reliably when the app is in the background or not already running.  The issue is specifically related to Android and may not be reproducible on iOS.

## Bug Description
The `Linking.addEventListener` is correctly set up, but it fails to fire a callback function when a deep link is tapped, preventing the app from handling the link appropriately.

## Solution
The solution involves using the `Linking.getInitialURLAsync` function to check for any URLs passed to the application immediately on start-up, handling any initial deep links before the app fully boots.