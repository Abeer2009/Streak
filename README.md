# Long Way Out: APK project

Easiest (no installs): 
1. Create a new empty GitHub repo and upload everything in this folder (keep the .github folder).
2. Open the repo's Actions tab. The "Build APK" workflow runs on push (or click Run workflow).
3. When it finishes (about 5 min), download the "LongWayOut-debug-apk" artifact, unzip, and send app-debug.apk to your phone.
4. On Android, open the APK and allow "install unknown apps" for your file manager or browser.

Local build (needs Node 20, JDK 17, Android Studio):
    npm install
    npx cap add android
    npx cap sync android
    cd android && ./gradlew assembleDebug
APK lands in android/app/build/outputs/apk/debug/app-debug.apk

The game itself is www/index.html. Edit it, push again, and a new APK builds.

## Mini-games and admin controls

The daily mission can be set to Asteroid Dodge, Alien Pong, Star Catcher, or a daily rotation from the local Admin panel. The panel also lets you set the current streak, replay today’s mission, and reset the device back to onboarding. These controls are local prototype tools and do not require a server.
