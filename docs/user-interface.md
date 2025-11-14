# Secret Santa User Interface Documentation

This guide covers the user interface for the Secret Santa plugin, including creating events, adding the block to your site, changing states, and assigning Secret Santa participants.

## Table of Contents

1. [Creating Events via the Secret Santa Menu](#creating-events-via-the-secret-santa-menu)
2. [Adding the Event Block to Posts/Pages](#adding-the-event-block-to-postspages)
3. [Changing the Block's Status](#changing-the-blocks-status)
4. [Assigning Elves via Users → Secret Santa](#assigning-elves-via-users--secret-santa)

---

## Creating Events via the Secret Santa Menu

Events in the Secret Santa plugin are managed through WordPress's custom post type system. To create a new event:

### Step 1: Access Secret Santa Posts

1. Log in to your WordPress admin dashboard
2. Navigate to **Secret Santa** in the left sidebar menu
3. You'll see a list of existing Secret Santa posts (participants)

### Step 2: Create or Manage Events

Events are managed through the **Event** taxonomy:

1. In the Secret Santa section, look for **Event** in the left sidebar (or right sidebar when editing a post)
2. Click on **Event** to view all existing events
3. To create a new event:
   - Enter a new event name (e.g., "holidays-2024", "summer-exchange-2024")
   - Click **Add New Event**
4. Event names are automatically converted to URL-friendly slugs (lowercase with hyphens)

**Best Practices for Event Names:**
- Use descriptive names that include the year or season
- Use lowercase and hyphens for consistency (e.g., "holidays-2024")
- Keep names short and memorable

**Note:** Events are what separate different gift exchanges. Each event can have its own participants and assignments.

---

## Adding the Event Block to Posts/Pages

Once you have created an event, you can add the Secret Santa block to any post or page to allow users to interact with the gift exchange.

### Step 1: Open the Block Editor

1. Navigate to **Posts → Add New** or **Pages → Add New** (or edit an existing post/page)
2. You'll be in the WordPress Block Editor (Gutenberg)

### Step 2: Add the Secret Santa Block

1. Click the **+** (Add block) button in the editor
2. Search for "Holiday Gift Exchange" in the block search
3. Click on the **Holiday Gift Exchange** block to add it to your content

Alternatively:
- Type `/holiday` in the editor and select the block from the suggestions
- Find it under the **Common** category in the block inserter

### Step 3: Configure the Block

After adding the block, you'll see the block configuration interface:

**Event Selection:**
1. You'll see a field labeled "Event:"
2. Start typing the name of your event (e.g., "holidays-2024")
3. Select the event from the autocomplete suggestions
4. You can only select one event per block

**Note:** Only events that have been created in the Secret Santa taxonomy will appear in the suggestions.

---

## Changing the Block's Status

The Secret Santa block has four different states that control what users see and can do. The state determines the current phase of the gift exchange.

### Understanding the Four States

1. **State 1: Signups Open!**
   - Users can sign up for the gift exchange
   - Participants can enter their shipping address and country
   - Participants can update their information or remove themselves from the exchange

2. **State 2: Signups Closed, working on assignments!**
   - Signups are closed
   - Users can see if they're signed up
   - Administrators work on assigning Secret Santas in the background

3. **State 3: Please send your gifts!**
   - Participants can see who they're sending to
   - Shows recipient's shipping address and country
   - Participants can send anonymous messages to their recipient
   - Participants can also message their Secret Santa (the person sending to them)

4. **State 4: The Great Unmasking!**
   - The big reveal
   - Participants can see who sent them their gift
   - Participants can still see who they sent to

### How to Change the State

1. Select the Secret Santa block in your post/page
2. Look for the button that shows **Current State:** followed by the current state name
3. Click this button to open the state picker dropdown
4. Select the desired state from the list:
   - Signups Open!
   - Signups Closed, working on assignments!
   - Please send your gifts!
   - The Great Unmasking!
5. The currently selected state will be highlighted in the dropdown
6. Click on any state to change to it
7. Update or publish your post/page to save the changes

**Important Notes:**
- You can change the state at any time by editing the post/page
- State changes take effect immediately after you update the post
- Make sure to transition through states in order for the best user experience
- Don't skip directly to State 4 without completing assignments in State 2

### Recommended State Progression

```
State 1 (Signups Open) 
    ↓ (Close signups when ready)
State 2 (Working on assignments)
    ↓ (After assignments are made)
State 3 (Send gifts)
    ↓ (After gift exchange period)
State 4 (The reveal)
```

---

## Assigning Elves via Users → Secret Santa

Once participants have signed up (during State 1 or 2), administrators need to assign who sends to whom. This is done through the Secret Santa admin page.

### Step 1: Access the Secret Santa Admin Page

1. Log in to WordPress as an administrator
2. Navigate to **Users → Secret Santa** in the admin menu
3. You'll see the Secret Santa administration interface

### Step 2: Select Your Event

If you have multiple events:

1. Look for the **Events:** section at the top of the page
2. Click on the event name you want to manage
3. The page will reload showing participants for that event

### Step 3: View Current Participants

The page displays a table with three columns:

- **Receiving From:** Who is sending a gift to this person (empty until assignments are made)
- **User:** The participant's information (avatar, name, address, country)
- **Shipping To:** Who this person will send a gift to (empty until assignments are made)

Each participant is shown as a card with:
- Their avatar/profile picture
- Display name
- Shipping address
- Country

### Step 4: Assign Elves Automatically

The easiest way to assign Secret Santas is using the automatic assignment feature:

1. Click the **Assign Elves** button at the top of the page
2. The system will automatically:
   - Shuffle all participants randomly
   - Assign each person to send to another person
   - Ensure everyone is included in a complete circle (everyone sends and receives)
   - Display the proposed assignments in the table
3. Review the assignments to make sure they look good
4. The button will change to **Accept assignments and save**
5. Click **Accept assignments and save** to finalize the assignments
6. You'll see a confirmation message showing how many assignments were saved

**Important Notes:**
- You need at least 3 participants to make assignments
- If you click "Assign Elves" again, it will create a new random assignment
- Assignments create a complete circle, so everyone sends to someone and receives from someone
- Once saved, assignments are stored and linked to each participant's Secret Santa post

### Step 5: Manual Adjustment (Advanced)

If you need to manually adjust assignments after automatic assignment:

1. Assignments are stored in the post meta for each participant
2. You can edit individual Secret Santa posts through **Secret Santa** menu
3. Look for the "secret-santa :: shipping_to" meta field
4. Change the value to the recipient's username

**Note:** Manual adjustment requires care to ensure the assignment circle remains complete.

### Assignment Best Practices

- **Run assignments during State 2** (Signups Closed, working on assignments)
- **Review assignments** before saving to catch any issues
- **Consider geographic locations** if shipping costs are a concern (though automatic assignment doesn't account for this)
- **Save a backup** of assignments in case you need to reference them later
- **Transition to State 3** after assignments are complete so participants can see their recipients

---

## Workflow Summary

Here's a complete workflow for running a Secret Santa gift exchange:

1. **Setup Phase**
   - Create a new event (e.g., "holidays-2024")
   - Create a post or page for the exchange
   - Add the Holiday Gift Exchange block to the page
   - Select your event in the block
   - Set the block to State 1 (Signups Open)
   - Publish the page

2. **Signup Phase**
   - Participants visit the page and sign up
   - They enter their shipping address and country
   - They can update their information until signups close

3. **Assignment Phase**
   - Change the block to State 2 (Signups Closed)
   - Go to Users → Secret Santa
   - Select your event
   - Click "Assign Elves" to generate assignments
   - Review and click "Accept assignments and save"

4. **Gift Exchange Phase**
   - Change the block to State 3 (Please send your gifts)
   - Participants can now see who they're sending to
   - Participants ship their gifts and can send anonymous messages

5. **Reveal Phase**
   - After gifts are received, change to State 4 (The Great Unmasking)
   - Participants can see who sent them their gift
   - Participants can thank their Secret Santa

---

## Troubleshooting

### Event doesn't appear in block autocomplete
- Make sure you've created the event through the Event taxonomy
- Try refreshing the page editor
- Check that the event has been properly saved

### Can't assign elves
- Ensure you have at least 3 participants signed up
- Verify you're logged in as an administrator
- Check that participants have completed their signup (address and country)

### Participants can't see their assignments
- Verify the block is set to State 3 or State 4
- Confirm assignments were saved in Users → Secret Santa
- Make sure participants are logged in

### Changes don't appear on the frontend
- Remember to click "Update" or "Publish" after making changes in the editor
- Clear any caching plugins if changes don't appear immediately
- Verify the correct event is selected in the block

---

## Additional Information

### Multiple Events

You can run multiple gift exchanges simultaneously by creating different events. Each event:
- Has its own set of participants
- Has its own assignments
- Can be displayed on different pages with different blocks
- Can be in different states

### Shortcode Alternative

While the block is the recommended method, you can also use the legacy shortcode:

```
[holiday-gift-exchange event="holidays-2024" state="1"]
```

Replace:
- `event` with your event slug
- `state` with the current state number (1-4)

### Customization

The plugin supports filters and hooks for customization:
- `secret-santa_get_sign_up_defaults` - Pre-populate user information
- `secret-santa_message_sender` - Customize messaging method (e.g., Slack instead of email)
- `secret-santa_message_recipient` - Customize anonymous messaging
- `secret-santa_shipping_to_additional_details` - Add custom fields to recipient display

See the main plugin file for more details on available hooks and filters.
