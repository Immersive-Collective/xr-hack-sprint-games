Here is an example of a manifest file tailored for a WebXR app that will be installed as an APK using ADB:

```json
{
  "name": "My WebXR App",
  "short_name": "WebXR",
  "start_url": "/index.html",
  "display": "standalone",
  "orientation": "landscape",
  "background_color": "#000000",
  "theme_color": "#000000",
  "description": "A WebXR application",
  "icons": [
    {
      "src": "/images/icon-192x192.png",
      "sizes": "192x192",
      "type": "image/png"
    },
    {
      "src": "/images/icon-512x512.png",
      "sizes": "512x512",
      "type": "image/png"
    }
  ]
}
```

To use this manifest file:

1. Save it as `manifest.json` in the root directory of your WebXR app.
2. Ensure the `start_url` points to the main HTML file of your WebXR app.
3. Update the `icons` paths to point to your icon files.
4. Customize `name`, `short_name`, `description`, `background_color`, and `theme_color` as needed.

## Steps to Install the APK

1. **Install Bubblewrap CLI globally:**
    ```sh
    npm i -g @bubblewrap/cli
    ```

2. **Initialize Bubblewrap project:**
    ```sh
    bubblewrap init --manifest="https://your-webxr-app.com/manifest.json"
    ```

3. **Build the TWA:**
    ```sh
    bubblewrap build
    ```

4. **Connect your Android device via USB and ensure USB debugging is enabled.**

5. **Install the APK on your device using ADB:**
    ```sh
    bubblewrap install
    ```

Replace `https://your-webxr-app.com/manifest.json` with the URL of your WebXR app manifest file. This process will generate and install an APK of your WebXR app as a Trusted Web Activity on your device.