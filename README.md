# HubSpot Integration Frontend Documentation

## Overview

The `HubspotIntegration` component is a React-based UI component that allows users to connect their application to HubSpot using OAuth 2.0. It handles the OAuth flow, including opening the authorization window, polling for completion, and storing the retrieved credentials.

This component is built using:

- **React** for the UI.
- **Material-UI (MUI)** for styling and components.
- **Axios** for making HTTP requests to the backend.

## Backend Integration

The frontend interacts with the backend through the following endpoints:

POST /integrations/hubspot/authorize

Initiates the OAuth flow and returns the authorization URL.

POST /integrations/hubspot/credentials

Fetches the OAuth credentials after the flow is complete.

## Flow

User clicks the "Connect to HubSpot" button.

Frontend sends a request to /integrations/hubspot/authorize to get the authorization URL.

A new window opens with the HubSpot authorization page.

After the user completes the OAuth flow, the window closes.

Frontend polls for the window closure and fetches credentials from /integrations/hubspot/credentials.

Credentials are stored in the parent component's state.

## Error Handling

If the OAuth flow fails, an error message is displayed using alert.

If the credentials are not found, the user is notified.
