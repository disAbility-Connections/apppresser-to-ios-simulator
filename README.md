# appresser-to-ios-simulator
Documentation on how to compile for the iOS Simulator to take screenshots

`npm i -g cordova-cli`

`npm i -g ionic`

Install [phonegap](http://docs.phonegap.com/getting-started/1-install-phonegap/desktop/)

Download the source files from https://myapppresser.com/ by going to your App Dashboard and clicking General -> Download latest build ZIP

`phonegap create ./app-directory`

Then copy in your files that you downloaded above.

The files

- `config.xml`
- `icon.png`
- `splash.png`

Should all go to the root. Everything else goes under `./www`

Replace/Overwrite as necessary.

Make sure that all the file paths in `config.xml` match up with what they should. You will likely need to update them.

Double check the Plugin entry for `cordova-sqlite-evcore-extbuild-free` to ensure it isn't trying to use a Git Repository. It should be updated to `<plugin source="npm" name="cordova-sqlite-evcore-extbuild-free" spec="0.9.10" />` or something similar to prevent errors.

Run `cordova build ios --buildFlag="-UseModernBuildSystem=0"` to build the Application. It should appear under `./platforms/ios/build/emulator/` as a `.app` file.

Run the iOS Simulator and open your desired Hardware Type (Likely iPhone 6s for 5.5" and iPad Pro (2nd Gen) for 12.9") and drag-and-drop the `.app` file into the window after it has loaded to install the application.
