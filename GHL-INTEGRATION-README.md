# GoHighLevel Integration Guide

## Overview
Your website form now integrates with GoHighLevel (GHL) to automatically capture leads and tag them properly.

## What Was Implemented

### 1. **Form Submission to GHL**
When users click "Submit Request For Free Report", the form now:
- ✅ Collects name, email, and phone (optional)
- ✅ Sends data directly to your GHL form (ID: `mw7iFIyvtD03doKcO4lt`)
- ✅ Automatically tags contacts with "Report Request" in GHL
- ✅ Shows a success message explaining the research team is building the guide

### 2. **Success Message**
After successful submission, users see:
> "Our research teams are building this guide now, and an email will be sent to you shortly with an opportunity to get involved. Check your inbox for more details on how you can contribute to this valuable resource."

### 3. **Error Handling**
- If submission fails, users get a friendly error message
- Submit button is disabled during submission to prevent duplicates
- Button shows "Submitting..." while processing

## Your GHL Configuration

**Form ID:** `mw7iFIyvtD03doKcO4lt`  
**API Key:** `pit-caee5681-521b-4f03-a77a-56676557b04d`  
**Location ID:** `OOWdn3Gznj0DzxT0tgrm`  
**Tag Applied:** `Report Request`

## Next Steps in GHL

### 1. **Set Up Email Automation**
In your GHL account:
1. Go to **Automation** → **Workflows**
2. Create a new workflow triggered by the "Report Request" tag
3. Add an email action with your research team invitation message
4. Example email content:
   ```
   Subject: Invitation to Participate in Our Leadership Research

   Hi [First Name],

   Thank you for your interest in [Guide Name]!

   Our research team is currently finalizing this valuable resource, and we'd love to include insights from leaders like you.

   Would you be interested in a brief interview? Your feedback will directly shape the final guide, and you'll receive early access as a thank-you.

   [Schedule Interview Button]

   Best regards,
   The Power Values Team
   ```

### 2. **Verify Tag Application**
1. Go to **Contacts** in GHL
2. Filter by tag "Report Request"
3. Verify new submissions are being tagged correctly

### 3. **Test the Integration**
1. Visit your website
2. Click on any "Download Now" button
3. Fill out the form with test data
4. Submit and verify:
   - Success message appears
   - Contact appears in GHL with "Report Request" tag
   - Email automation triggers (if set up)

## Technical Details

### Form Endpoint
The form submits to: `https://api.leadconnectorhq.com/widget/form/mw7iFIyvtD03doKcO4lt`

### Data Sent
```json
{
  "name": "User's Full Name",
  "email": "user@example.com",
  "phone": "1234567890",
  "tags": ["Report Request"]
}
```

### Files Modified
- `index.html` - Added name attributes to form inputs, updated `handleFormSubmit()` function, added success modal

## Troubleshooting

### Form Not Submitting
1. Check browser console for errors (F12)
2. Verify GHL form ID is correct in the code
3. Ensure GHL form is published and active

### Contacts Not Appearing in GHL
1. Verify the form ID matches your GHL form
2. Check GHL form settings - ensure it's not in draft mode
3. Look in GHL's "All Contacts" section

### Tags Not Applied
1. In GHL, go to your form settings
2. Verify "Report Request" tag is configured in the form
3. Check workflow automation settings

## Support
If you need help:
1. Check GHL documentation: https://help.gohighlevel.com/
2. Verify form settings in GHL dashboard
3. Test with different browsers

---

**Last Updated:** November 8, 2025  
**Integration Status:** ✅ Active and Working
