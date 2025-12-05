# T-K-Logistics-Tracking-portal-Dashboard
T K Logistics Client Portal

A modern, responsive single-page application (SPA) built with React and Tailwind CSS for clients of T K Logistics to track temperature-sensitive food shipments and manage their cargo history.

Features

Public Shipment Tracking: Look up any shipment status using a 12-character Tracking ID (e.g., TK-2024-1234).

Real-time Status: Displays a step-by-step timeline, including crucial Temperature Control Status.

Client Dashboard: (Requires simulated authentication/unique Session ID) Provides key metrics and a searchable/sortable table of all past and current shipments associated with the user's ID.

Persistent Data Storage: Uses Firebase Firestore for real-time synchronization and data persistence.

Technology Stack

Frontend: React (Hooks, Functional Components)

Styling: Tailwind CSS (Fully responsive, mobile-first design)

Icons: lucide-react

Database: Firebase Firestore

Authentication: Firebase Auth (using custom tokens/anonymous sign-in)

Data Structure (Firestore)

All shipment data is stored publicly to allow for global tracking, following the path specified in the prompt:

Collection Path: /artifacts/{appId}/public/data/shipments

Document ID: Shipment Tracking ID (e.g., TK-2024-1234)

Each document contains key details like id, product, origin, destination, tempControl, status, and a detailed timeline array. Dashboard functionality uses the clientId field to filter records belonging to the authenticated user.

Running the Application

This application is designed to run within the Canvas environment, which automatically provides the necessary Firebase configuration and authentication tokens:

Initialization: The app uses global variables (__app_id, __firebase_config, __initial_auth_token) to initialize Firebase services.

Authentication: It attempts to sign in anonymously or via a custom token to establish a session ID (userId).

Client Login (Demo): Clicking the "Client Login" button simulates a client authentication event by changing the userId format, automatically redirecting the user to the Dashboard view.

Tracking: Use one of the mock IDs (e.g., TK-2024-1234) to test the tracking feature.
