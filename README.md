# Rent-A-Car
An Android app for browsing and renting cars with a credit system. Features include favourites, search &amp; sort, dark mode toggle, Intents, and in-memory data handling with real-time credit validation.

Iteration 1.0.0 – Car Model & Sequential Display
Date: 16/09/2025

Task:
- Create an in-memory Car model class with attributes: name, model, year, rating, kilometres, daily rental cost, and image.
- Implement Parcelable so that cars can later be passed between activities.
- Build UI and logic to display 5 cars one at a time, with details (name, model/year, rating, km, cost, description) under each image.
- Add a “Next” button to cycle through the list sequentially.
Time Spent: ~6 hours total

Outcome:
- Car.kt successfully created with all required attributes and implemented using @Parcelize + Parcelable.
- activity_main.xml updated with a fixed-size ImageView, enlarged fonts, detail section, and Next button.
- MainActivity.kt now holds an in-memory list of 5 cars (Focus RS, Cybertruck, Lancer Evo X, 911 GT3, Civic Type R) and cycles them with the button.
- Verified that car details (name, model, year, rating, kilometres, cost, description) and images update correctly as Next is pressed.
- 
Bugs & Fixes:
Problem: @Parcelize initially caused build errors.
Fix: Enabled kotlin-parcelize plugin in build.gradle.kts and added correct imports.

Problem: Package mismatch warning (com.example.rentacar.model vs file path).
Fix: Moved Car.kt into a proper model package.

Problem: String concatenation in Kotlin triggered lint warnings.
Fix: Moved text templates into strings.xml using placeholders.

Problem: Different image aspect ratios caused the Next button to jump position.
Fix: Set a fixed height for the ImageView (220dp) and used centerCrop/fitCenter.

Result:
First iteration complete — the app now meets the first two assignment requirements. Cars display sequentially with a Next button, layout is consistent across vehicles, and the code is ready for future extensions (favourites, renting, balance system, etc.).
