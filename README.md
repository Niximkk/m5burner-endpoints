# 🚀 M5Burner Hidden Endpoints Documentation
## PATCHED 🙂
By sniffing requests I discovered that the [M5Burner](https://docs.m5stack.com/en/download) application from [M5Stack](https://m5stack.com/) is not secure at all! Here are some endpoints that can be exploited to create, edit and delete projects (on any account 🙃).

## ⭐ Endpoints

### 📄 GET Requests

1. **Get All Firmwares**
   - **URL:** `http://m5burner-api-fc-hk-cdn.m5stack.com/api/firmware`
   - **Description:** Returns a JSON object containing all firmwares uploaded to M5Burner.
   - **Parameters:** None

2. **Get User-Specific Firmwares**
   - **URL:** `https://m5burner-api.m5stack.com/api/admin/firmware?username=<username>`
   - **Description:** Returns a JSON object containing all firmwares for a specific user.
   - **Parameters:**
     - `username` : User's username (e.g., `masterbudz01`, `ImNix`)

3. **Get Comment Count for Each Firmware**
   - **URL:** `https://m5burner-api.m5stack.com/api/firmware/comments`
   - **Description:** Returns a JSON object containing the comment counts for each firmware.
   - **Parameters:** None

### 📄 PUT Requests

1. **Publish/Unpublish Firmware**
   - **URL:** `http://m5burner-api.m5stack.com/api/admin/firmware/<firmwareId>/publish/<firmwareVersion>.bin/<publishOrUnpublish>`
   - **Description:** Publishes or unpublishes an existing firmware on M5Burner.
   - **Parameters:**
     - `firmwareId` : Firmware ID, found in the JSON from the first request.
     - `firmwareVersion` : Firmware version file name, found in the JSON from the first request.
     - `publishOrUnpublish` : 1 to publish or 0 to unpublish.

### 📄 POST Requests

1. **Increase Download Counter**
   - **URL:** `http://m5burner-api.m5stack.com/api/admin/firmware/download/<firmwareId>`
   - **Description:** Increases the 'downloads' count by 1.
   - **Parameters:**
     - `firmwareId` : Firmware ID, found in the JSON from the first request.

2. **Add a comment**
   - **URL:** `http://m5burner-api.m5stack.com/api/firmware/comment/<firmwareId>`
   - **Description:** Add a comment to any firmware.
   - **Body (JSON):**
     ```json
      {
        "content": "YourComment",
        "user": "UserName"
      }
     ```
   - **Parameters:**
     - `firmwareId` : Firmware ID, found in the JSON from the first request.

3. **Upload Firmware**
   - **URL:** `http://m5burner-api.m5stack.com/api/admin/firmware`
   - **Description:** Uploads a new firmware to M5Burner.
   - **Body (form-data):**
     - `name` : Firmware name
     - `description` : Firmware description
     - `category` : Firmware platform
     - `author` : Firmware author
     - `version` : Firmware version
     - `github` : Firmware GitHub link
     - `cover` : Firmware cover image (File)
     - `firmware` : Firmware file (File)
   - **Parameters:** None

4. **Delete Firmware**
   - **URL:** `http://m5burner-api.m5stack.com/api/admin/firmware/remove/<firmwareId>`
   - **Description:** Deletes any firmware from M5Burner.
   - **Body (JSON):**
     ```json
     {
       "version": "versionName"
     }
     ```
   - **Parameters:**
     - `firmwareId` : Firmware ID, found in the JSON from the first request.

5. **Edit Firmware**
   - **URL:** `http://m5burner-api.m5stack.com/api/admin/firmware/<firmwareId>/version/<firmwareVersion>.bin`
   - **Description:** Edits an existing firmware on M5Burner.
   - **Body (form-data):**
     - `name` : Firmware name
     - `description` : Firmware description
     - `category` : Firmware platform
     - `author` : Firmware author
     - `version` : Firmware version
     - `github` : Firmware GitHub link
     - `cover` : Firmware cover image (File)
     - `firmware` : Firmware file (File)
   - **Parameters:**
     - `firmwareId` : Firmware ID, found in the JSON from the first request.
     - `firmwareVersion` : Firmware version file name, found in the JSON from the first request.

---

**As Gabe Newell once said... Thanks, and have fun! ;3!**
