# Flowchart for System Process

This flowchart illustrates the **Property Booking process** in the Airbnb Clone backend.

### Steps in the Flow:
1. User logs in.
2. User searches for a property.
3. System checks property availability.
   - If unavailable → notify user.
   - If available → proceed.
4. User selects dates and confirms booking.
5. System processes payment through payment gateway.
   - If payment fails → notify user.
   - If payment succeeds → save booking.
6. System sends booking confirmation.
7. Process ends.