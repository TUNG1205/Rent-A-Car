# Rent-A-Car
An Android app for browsing and renting cars with a credit system. Features include favourites, search &amp; sort, dark mode toggle, Intents, and in-memory data handling with real-time credit validation.

Iteration 1.1.0 – Car Model, Sequential Display & Renting with Credit Balance
Date: 28/09/2025
Task:
•	Create an in-memory Car model class with attributes: name, model, year, rating, kilometres, daily rental cost, and image.
•	Implement Parcelable so Car objects can be passed between activities.
•	Build UI and logic to display 5 cars one at a time, with details shown under each image, and a “Next” button to cycle through them.
•	Add a Rent button that launches a second activity (RentActivity) using Intents.
•	Pass the selected Car object to RentActivity and display full details with daily cost.
•	Allow the user to select rental days, calculate total cost, and enforce a starting balance of 500 credits.
•	Deduct rental cost on confirm, block rentals that exceed balance, and update balance display on return to main screen.
Time Spent: ~12–13 hours total
Challenges / Bugs & Fixes:
•	Problem: Using @Parcelize caused build errors initially.
Fix: Enabled kotlin-parcelize plugin in Gradle and corrected imports.
•	Problem: String concatenation warnings in car details.
Fix: Moved all UI text into strings.xml with placeholders.
•	Problem: Car extra returned null when launching RentActivity.
Fix: Confirmed Car.kt was Parcelable and used correct key with putExtra/getParcelableExtra.
•	Problem: Balance did not refresh after renting.
Fix: Implemented ActivityResultLauncher and updated MainActivity on return.
•	Problem: Negative balance possible if too many days selected.
Fix: Added validation to block confirm if total cost exceeds balance.
•	Problem: Layout gaps and inconsistent image frame sizes caused button jumps.
Fix: Fixed image height and tightened constraints in activity_main.xml; wrapped activity_rent.xml in ScrollView for smaller screens.
Result:
•	The app fully meets the first two first iteration issues:
•	Car Model & Sequential Display – cars are represented in a Parcelable class, displayed one at a time, and cycled with a Next button.
•	Renting Flow & Credit Balance – cars can be rented via a second activity, balance is updated and displayed on the main screen, and invalid rentals are blocked with clear feedback.

Iteration 1.2.0 – Availability Updates & Non-TextView Widgets
Date: 29/09/2025
Task:
•	Introduce non-TextView widgets as required by the assignment.
•	Add an availability Chip to display whether the current car is “Available” or “Unavailable.”
•	Add a Switch (“Show available only”) that filters the car list so the Next button skips cars already rented.
•	Update car availability status dynamically when a rental is confirmed.
•	Disable the Rent button when a car is marked as unavailable.
•	Time Spent: ~5 hours
Challenges / Bugs & Fixes:
•	Problem: Car status did not refresh after returning from RentActivity.
Fix: On successful rental, the current index is added to the unavailable set and showCarAt() refreshes UI.
•	Problem: Next button cycled into unavailable cars when filter was ON.
Fix: Added moveToNextAvailable() method that skips indices in unavailable.
•	Problem: Switch and Chip overlapped with other UI in early layout.
Fix: Adjusted constraints so they align neatly with the balance label and car image.
Result:
This iteration satisfies both Non-TextView Widgets and Availability Updates Issues. The app now clearly communicates car status with a Chip, prevents renting unavailable cars, and gives the user control to only browse available cars via a Switch filter.
