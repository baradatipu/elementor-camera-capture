# elementor-camera-capture
Elementor Webcam Capture - Custom camera widget to capture photos with geolocation and embed them into Elementor forms by replacing the default file upload field.
# 📸 Elementor Camera Capture with Location Integration

This widget allows users to capture a photo via their device camera, auto-embed geolocation info (latitude, longitude, address, time, accuracy), and upload it into an Elementor form file upload field.

---

## ✅ Features

- Camera capture (mobile & desktop)
- Auto location fetch (GPS coordinates)
- Address conversion using OpenCage API
- Time & accuracy overlay on photo
- File auto-upload into Elementor form
- Optional hidden input for location metadata

---

## 🧩 Requirements

- WordPress site
- [WP Coder – Code Snippets + HTML, CSS, JS and PHP Injection Plugin](https://wordpress.org/plugins/wp-coder/) (for injecting code)
- Elementor Pro Plugin

---

## ⚙️ How to Use

### 1. Add HTML + JS Using WPCode Plugin

1. Go to: `WP Admin > WP Coder >  Add New > Select HTML Tab`
2. Write Title of Code Snippet above
3. Paste the full HTML + JS code from `elementor-webcam-capture.html`
4. Save and **Activate**
5. Copy the generated shortcode (example: `[wpcode id="123"]`)

---

### 2. Add the Shortcode to Elementor

1. Open your Elementor page with a form.
2. Add a **Shortcode** widget above the form.
3. Paste your copied WPCode shortcode:
   ```
   [wpcode id="123"]
   ```

---

### 3. Update Elementor Form

#### ➤ Add File Upload Field

- Drag a File Upload field to your form.
- Set **Field ID** to something like:
  ```
  field_a51b627
  ```

Update the script to match this ID:
```js
const fileInput = document.querySelector('#form-field-field_a51b627');
```

> Replace `field_a51b627` with your own Elementor file field ID.

#### ➤ Optional: Add Hidden Field for Geo Info

- Add a **Hidden** field in the form
- Set its name to:
  ```
  geo_info
  ```

The script auto-fills this field with:
```
Address: ..., Coordinates: lat,long, Time: ..., Accuracy: ±xxm
```

---

## 🌐 Geolocation API (OpenCage)

This widget uses the [OpenCage Data API](https://opencagedata.com/api) to convert GPS to human-readable address.

### How to Get Your API Key

1. Visit: https://opencagedata.com/
2. Sign up (free plan available)
3. Copy your API key
4. Replace this line in the JS:

```js
const key = 'YOUR_API_KEY_HERE';
```

---

## 🔐 Privacy Note

- Geolocation and camera access require user permission.
- Use over HTTPS to ensure browser access to location/camera.
- Data is not stored unless Elementor handles it (email, webhook, DB).

---

## 📦 Summary Table

| Feature      | Description                              |
|--------------|------------------------------------------|
| 📷 Camera     | Uses browser media API to take photo     |
| 📍 Location   | Captures GPS coordinates (lat/lon)       |
| 🗺️ Address    | Uses OpenCage API to get full address     |
| 🕒 Timestamp  | Adds readable date-time footer            |
| 📤 Upload     | Injects image file into Elementor form   |
| 🧾 Metadata   | Fills hidden input with full location info|

---

## 💡 Example Setup

| Field Type   | Label             | Elementor Field ID     |
|--------------|------------------|-------------------------|
| File Upload  | Upload Photo     | `field_a51b627`         |
| Hidden       | Location Details | `geo_info`              |

---

## 📁 Files in Repo

| File               | Description                                |
|--------------------|--------------------------------------------|
| `README.md`        | This guide                                  |
| `camera-widget.html` | Full widget code (HTML + JS, for WPCode)   |

---

## 🛠️ Customization

- Change camera resolution via:
  ```js
  width: { ideal: 1920 }, height: { ideal: 1080 }
  ```
- Style buttons using inline styles or classes
- You can also integrate this into a theme or convert it into a full WP plugin

---

## 👨‍💻 Credits

Created for easy Elementor camera capture + location tagging.  
Use and modify freely. Just give credit if reusing publicly.  
🙏 Respect user consent and privacy.
