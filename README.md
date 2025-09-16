# Rent-A-Car
An Android app for browsing and renting cars with a credit system. Features include favourites, search &amp; sort, dark mode toggle, Intents, and in-memory data handling with real-time credit validation.

Iteration 1.0.0 – Car Model & Sequential Display
Date: 16/09/2025
Task:
- Create an in-memory Car model class with attributes: name, model, year, rating, kilometres, daily rental cost, and image.
- Implement Parcelable so that cars can later be passed between fragments.
- Build UI and logic to display 5 cars one at a time, with details shown under each image, and a “Next” button to cycle through them.
- Time Spent: 6 hours total
Outcome:
- Car.kt successfully created with all required attributes, manual Parcelable implementation 
- Updated fragment_first.xml with ImageView, TextView, and Next button.
- Implemented FirstFragment.kt to hold a list of 5 cars (using AI generated images), track currentIndex, and cycle cars with the button.
- Verified that car details (name, model, year, rating, km, cost) and images update correctly.
Challenges / Bugs & Fixes:
- Problem: Tried using @Parcelize but it caused build errors because the plugin wasn’t enabled.
Fix: Implemented Parcelable manually with CREATOR instead.
- Problem: Binding IDs didn’t match XML (initially used different names).
Fix: Synced IDs (carImage, carDetails, nextButton) across XML and Kotlin.
Result: First app screen displays cars sequentially as required by the spec: “Each vehicle should be displayed one at a time; a Next button is needed to progress.”
