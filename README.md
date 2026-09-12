# Localeats-food-delivery
A mobile food-delivery platform that connects customers with small local restaurants and delivery drivers.

C:\src\flutter\bin\flutter.bat create .

## Android app with Capacitor

The Android app uses the same hosted website and PHP API as the browser version.
This means accounts, logins, and the database remain shared between the website and the app.

### First-time setup

1. Install Node.js LTS from https://nodejs.org/.
2. Open PowerShell in this folder.
3. Install the Capacitor packages:

	```powershell
	npm install
	```

4. Start the PHP website so the Android emulator can reach it. For local testing, use a PHP/XAMPP server and make sure the site is available at:

	```text
	http://localhost:8000/LocalEats.html
	```

5. Add Android and open it in Android Studio:

	```powershell
	npm run android:add
	npm run android:open
	```

The default emulator URL is `http://10.0.2.2:8000/LocalEats.html`, which maps to the computer's `localhost`. If the website is hosted online, build with its HTTPS URL instead:

```powershell
$env:LOCALEATS_APP_URL = 'https://your-domain.example/LocalEats.html'
npm run android:sync
npm run android:open
```

For a physical Android phone, use an HTTPS hosting URL. Do not use `127.0.0.1` in the app because that points to the phone itself. The browser and Android app must both use the same hosted PHP backend for shared accounts and logins.
