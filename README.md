# Usman AI Ride Finder — Android prototype source

This is an **experimental Android Studio source project**, not a finished or tested APK.

## What it currently attempts
- User starts a screen-capture session after Android's explicit MediaProjection consent.
- ML Kit OCR runs locally on captured frames (no image upload/network code).
- A floating pop-up may appear when simple fare and kilometre patterns are detected.
- Fuel estimate uses the supplied values: 15 km/L and Rs 370/L = Rs 24.67/km.
- It never taps, accepts, bids on, or otherwise controls a ride.

## Important limitations
- OCR and fare/distance parsing are heuristic and may misread the inDrive screen. The prototype may combine unrelated kilometre values and must not be trusted for financial decisions.
- It does not obtain rides earlier, increase ride availability, or guarantee a profitable recommendation.
- Screen capture and overlay behavior vary by Android version / Vivo Funtouch OS. Android Studio build and device testing are still required.
- Use only while parked. Do not interact with the phone while driving.
- Before using screen capture with inDrive, check its current terms and obtain any required permission. Do not use this prototype to bypass app restrictions or capture protected content.

## Build
1. Open this folder in Android Studio (Giraffe or newer; Android Gradle Plugin 8.7.3).
2. Allow Gradle sync and install the Android SDK platform 35 if prompted.
3. Build > Build APK(s).
4. Install the debug APK on a test device. Grant overlay permission, then press Start screen analysis and approve Android's screen-capture prompt.

## Next engineering steps before real use
- Compile and test on Vivo Y200 / Android version in use.
- Validate the inDrive screen layout and OCR output with permission.
- Replace heuristic parsing with robust, user-reviewed ride-field extraction and a configurable minimum profit rule.
- Add an explicit stop control in the persistent notification and privacy indicators.
