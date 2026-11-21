# SnapFind — Local Browser Edition

A consent-first event photo finder. The organizer indexes approved event photos; a participant uploads their own selfie; the browser compares face descriptors and shows possible matches.

## Important
- This is a **local browser app**, not a hosted multi-user service.
- Photos and face descriptors stay in IndexedDB on the current browser/device. They are not uploaded to a SnapFind server.
- The organizer and participants must use the **same browser profile/device** for this local edition.
- Face matching is approximate. It can produce false matches or miss real matches.
- Use only with explicit permission from people whose photos are included. Do not use for surveillance, attendance tracking, or identifying non-consenting people.
- Delete the local event gallery after the event using the Organizer Gallery tab.
- Browser storage is not a secure production database. Do not put sensitive/private images into this prototype.

## Run it
1. Extract `snapfind-final.zip`.
2. Open a terminal in the extracted folder.
3. Run a local web server:
   - Python: `python -m http.server 8000`
4. Open `http://localhost:8000` in Chrome or Edge.
5. Internet is required the first time to load the face-matching library and model files from jsDelivr.
6. In **Organizer gallery**, enter an event code, choose approved photos, tick the permission checkbox, and click **Index approved photos**.
7. In **Find my photos**, enter the same event code, upload your own selfie, tick the consent checkbox, and search.

## To make it available online
Deploy the extracted folder as a static site on a hosting provider that supports HTTPS (for example, GitHub Pages, Netlify, or Vercel). This does not create shared storage: each visitor's browser still has its own local gallery. A real public event service needs a secure backend, participant opt-in, access control, encrypted storage, deletion workflow, and a privacy notice. Do not publish private event photos in a public static folder.
