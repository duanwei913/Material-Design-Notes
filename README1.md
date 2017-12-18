#### Navigation

- Usage
	- Communicate relationship & context
	Group content into logical and relatable chunk that show clear relationship between items.
	
	- Illuminate actions
	Guide users from one scene to the next using paths that encourage specific choices or freer exploration
	
	- Focus attention
	Tailor your app’s navigation to promote important content and tasks
	
- Define your navigation
To determine the type of navigation best suited to your app, identify your app’s users, typical paths they might take through your app, and actions you want them to perform

	- Take inventory
	Identify your app’s users and their potential roles, such as consumer, business owner, or journalist. Identify the most common tasks they may want to perform
	
	- Prioritize
	Assign priority levels of high, medium, or low to common user tasks. Give prominence in the UI to paths and destinations with high priority levels and frequent use. Adjust priority levels as user needs change over time.
	
	- Sequence
	Identify the different paths that users take through your app and use those paths to define your navigation:
	
		- List frequent destinations prominently in your navigation
		- Group related tasks together and use those groupings to structure your navigation
		
	- Deconstruct
	Divide complex, broad, or vague use cases into smaller activities. These smaller tasks may be frequently used, more easily understood, or better meet user goals.
	> For example, dividing search into smaller activities that differentiate searching by name, location, or popularity may reveal the need to surface those smaller activities as part of navigation
	
- Clarify the difference between back button and up button
	- **The button on left top of the screen** is up button, it navigates upward in the UI hierarchy, always within the app, that means, the app cannot be finished with button up
	- The back key and the left button in a floating touchpad is the real back button, it navigates back in the whole phone scale, which means you can kill the app with back button
	
- Navigation history can only be changed by activity ( Maybe the change of fragment can be rarely used in the navigation hierarchy )

- Navigation Hierarchy
	- Home screen is the entrance of the app, thus the parent of all other screen
	- Higher level in a navigation is called parent, while lower is called children, navigating from parent to children is called descending navigation and the other way around is called ascending navigation
	- Screens with the same priority or level are called siblings, such navigation is called lateral navigation
	- A bunch of siblings are called a collection
	- Links allow users to jump items that aren't navigationally adjcent
		- Crosslinks can jump anywhere within the app
		- External links can jump from outside the app to somewhere deep in the navigation ( Consider push for example )
	
- Patterns
	- Embeded Navigation ( static navigation bar at the bottom like a virtual touch pad )
		- Provide more convenient navigation but reduces available displaying space
		- Recommended for :
			- Apps with a strong primary view, and few alternate views
			- Apps that perform common tasks in the main view
			- Infrequently used apps
			
	- Tabs
	Tabs allow users to quickly move between a small number of equally important views. Suitable for hierarchy such as **Parents with embedded child views** or **A group of sibling views**
		- Recommended for:
			- Frequent switching between views
			- Apps with few top-level views
			- Promoting awareness of alternate views ( Don't really follow, maybe in a news app, notify the user to try sports news when financial news are unavailable? )
			
	- Bottom Navigation Bar
	A bottom navigation bar allows users to quickly move between a small number of top-level views. Suitable for hierarchy such as **Parents with embedded child views** or **A group of parent views**
	> Biggest difference between Bottom navigation bar and tabs from my point of view is that the bottom navigation bar is usually based on the root level of the whole app, navigating from a bunch of top-level pages ( Consider wechat or weibo ), while tabs usually navigates among a bunch of sub-leveled views ( Consider the exploring page in weibo )
	
		- Recommended for:
			- Frequent switching between views
			- Apps with few top-level views
			- Promoting awareness of alternate views
			- Mobile devices, as bottom navigation is located in a more ergonomic location
			
	- Navigation Drawer
	Side navigation can display many navigation targets at once. A drawer remains hidden until invoked by the user. Usually helpful when there's not enough space to support tabs. Suitable for hierarchy such as **Lateral navigation** or **Parents with siblings or peers**, check out the specs [here](https://material.io/guidelines/patterns/navigation-drawer.html#)
		- Recommended for:
			- Apps with many top-level views
			- Enabling quick navigation between unrelated views
			- Deep navigation structures
			- Reducing visibility of infrequent destinations
			
	- Nested Navigation
	Appropriate for hierarchies such as **lateral navigation** or **parents with siblings or peers**
		- Recommended for:
			- Deep navigation structures with many views
			- Enabling quick navigation between unrelated views
			
	- Expand or Cascading Navigation
	Not suitable for mobile
	
	- Gestural
	Gestural navigation allows users to use swipe gestures to navigate between sibling or peer views. Supported gestures include: touching and dragging the screen horizontally (left/right), vertically (up/down), or while zooming in or out
	> Like in wechat, swiping horizontally changes page can be seen as an alternative gestural navigation for bottom navigation bar
	
		- Recommended for:
			- Naturally ordered relationships, such as pages representing consecutive calendar days
			- Views with few siblings
			- Views with similar content types

- Combined Patterns
Combine multiple patterns together. 
	- In-context Navigation ( Consider the taobao app, always maintain a link to the shopping cart )
	Less linear, suitable for **Parents with siblings**
		- Recommended for:
			- Showing large sets of child scenes
			- Focusing attention on a specific set of tasks
			- Apps with a strong primary view, and few alternates
		- Examples:
			- Link a song to an artist
			- Move between recent items and a complete history
			- Connect a user’s post to their profile page
	
	- Side nav and Tab Combinations

#### Navigation Transition

Normally, screens with the same level share the same elevation, i.e. navigating from parent to child usually increase the elevation, and decrease elevation the other way around. Changing among peer-level items will not change elevation

#### Notification

- Anatomy
	- Header Area
		- The app icon
		- The app name
		- Header text (optional : only needed if an app send notification from multiple sources)
		- Timestamp (optional : only needed if time sent is important like a missing call)
		- Expand Indicator (optional : if the notification can be expanded)
	
	- Content Area
		- A content title
		- A content text
		- Large icon (optional : say if a message includes a large avatar of the sender)
		
	- Action Area (Usually only visible after expanded)
		- Action text
		- Action icon (optional : not support after Android N, but best to provide, for devices before Android N and Android Wear and Android Auto devices)
		
- Usage
	- Don't Use Scenario
		- Cross-promotion : Don't advertise another app using notification, **strictly prohibited!**
		- For users who never opend the app
		- Meaningless text like "Haven't seen you for a while (But the opertional management colleague uses all the time)"
		- Request for a rate
		- Info not involve user interaction like syncing
		- Error states that can be recovered without user action

	- Required Scenario
		- Foreground Services, which could still use batteray and data, so it's best to give user awareness and provide with an explicit "Stop" action
		
- Multiple Notification
When multiple notification arrives, there are two android-supported way of organizing them

	- Summarizing ( Collapse them together and replace with "X new messages" )
	- Grouping ( Collapse them together and replace with an ellipsis at the end )

- Type of Notification
	- Transactional
	
	|Transactional notifications can help users...|Examples|
	|---|---|
	|Enable human-to-human interaction|Incoming phone calls or text messages<br>Notification of a user's turn in a two-player game|
	|Function better in daily life|Calendar event about to take place<br>A reminder or alarm set up by the user<br>Delayed flight<br>Delivered order|
	|Monitor, control, or resolve temporary device states|Music playing<br>Turn-by-turn navigation<br>Stopwatch running<br>Screenshot taken<br>App running in the background|
	
	- Non-Transactional
		- Opt-out : Display at default, user has to manually disable
		- Opt-in : Not display at default, user has to manually enable

- Notification Channel
Since Android O, app have to define the notifcations with different channel, and user can choose to accept some type of the notifications

	- Define each channel with a topic and a desired importance level
	
	|Importance|Behavior|Usage|Examples|
	|---|---|---|---|
	|HIGH|Makes a sound and appears on screen|Time-critical information that the user must know, or act on, immediately|Text messages, alarms, phone calls|
	|DEFAULT|Makes a sound|Information that should be seen at the user’s earliest convenience, but not interrupt what they're doing|Traffic alerts, task reminders|
	|LOW|No sound|Notification channels that don't meet the requirements of other importance levels|New content the user has subscribed to, social network invitations|
	|MIN|No sound or visual interruption|Non-essential information that can wait or isn’t specifically relevant to the user|Nearby places of interest, weather, promotional content|
	
	- For devices prior than Android O, define a priority level by notification

	- Try to set each notification to a Android pre-defined category, which will help the system to rank priority your notifcation
	
	|Category|Description|
	|---|---|
	|CATEGORY_CALL|Incoming call (voice or video) or similar synchronous communication request|
	|CATEGORY_MESSAGE|Incoming direct message (SMS, instant message, etc.)|
	|CATEGORY_EMAIL|Asynchronous bulk message (email)|
	|CATEGORY_EVENT|Calendar event|
	|CATEGORY_PROMO|Promotion or advertisement|
	|CATEGORY_ALARM|Alarm or timer|
	|CATEGORY_PROGRESS|Progress of a long-running background operation|
	|CATEGORY_SOCIAL|Social network or sharing update|
	|CATEGORY_ERROR|Error in background operation or authentication status|
	|CATEGORY_TRANSPORT|Media transport control for playback|
	|CATEGORY_SYSTEM|System or device status update. Reserved for system use.|
	|CATEGORY_SERVICE|Indication of running background service|
	|CATEGORY_RECOMMENDATION|A specific, timely recommendation for a single thing. For example, a news app might recommend a news story the user might want to read next.|
	|CATEGORY_STATUS|Ongoing information about device or contextual status|
	
- Lock Screen
Because lock screen is visible to anyone touching the phone, notification should be marked as public and private, only show public notifications on the lock screen

- Style
Try the google recommended template [here](https://material.io/guidelines/patterns/notifications.html#notifications-templates)

#### Offline States

- Principles
	- Adapt to the connection : Consider how your feature or app behaves when the user has a slow, intermittent, or lack of internet connection
	- Illustrate functionality : Use an element’s design to illustrate how an offline feature works
	- Display available content : It’s better to load something than nothing, while explaining that the internet connection is limited

- Interaction
	- If app can provide some functions while offline, do it with an icon indicating it's offline
	- If app cannot provide offline functions, use a no-connection icon with text to indicate that
	- It's best to provide downloading some material to support offline mode
	- All the downloaded content should have a clear track and offer explicit delete action
	
#### Permissions

- Usage
	Permission Groups : There are nine groups of permissions for user to request in one shot for specific tasks
	
	|Permission|Description|
	|---|---|
	|Calendar|Managing calendars|
	|Camera|Taking photos and recording videos|
	|Contacts|Managing contacts|
	|Location|Current device location|
	|Microphone|Audio recording|
	|Phone|Dialing and managing phone calls|
	|Body Sensors|Heart rate and similar data|
	|SMS|Sending and viewing messages|
	|Storage|Accessing photos, media, and files|
	
- How To Request
	- Try to educate users before requesting, say in the first-open tutorial
	- Only request the most important and necessary permissions up-front, and try to educate the users to link your app to the permissions needed in a natural way
	> Say it would feel natrual to ask for SMS permissions for a message app, try to convince users with such manner
	
	- Ask the non-critical permissions only when needed, and try to do it with education
	
- Deal with user denial
	- For critical permissions, set an alternative page for splash page, indicating clearly the permissions needed, offer a direct link to the setting page
	- For non-critical permissions, Disable the function relying on it and offer a hint with snackbar ( Don't use toast which dismiss iteself quickly and cannot offer further actioins within )
	
#### Scrolling Techniques
Deals with the status bar, the tool bar, tab bar and some optional flexible space when content is scrollable, check out examples [here](https://material.io/guidelines/patterns/scrolling-techniques.html#)

	- Tool bar can stay fixed while scrolling or can be invisible when scrolling down and visible when scrolling up
	- Tab bar can replace where tool bar was when scrolling down and reset when scrolling up, they can also all be fixed when scrolling
	- Some flexible space can also be transformed into tool bar while scrolling and reset when scrolling up

#### Search

- Search Type
	- Persistent Search : The search box is fixed on the sceen waiting for focus, use only when the search action is the primary task in the screen
	- Expandable Search : The search box is collapsed into an search icon on the tool bar, only when clicking will it expand into the search box
	
- Search Interaction
	Check [here](https://material.io/guidelines/patterns/search.html#) for the detailed interaction with image
	
	- Icon left indicating the search action
	- Clickable icon right triggering the voice search
	- Text watcher displaying the search history and / or auto-completion
	
#### Selection

- Item Selection
	- Long press to chose one item, quit selecting mode by deselect all
	- Long press and drag to conveniently select multiple items
	- Use a check mark to indicate the selected state
	
- Text Selection
	- Long press the text to select, and back button or tapping another position to quit select
	- Toggle the left and right handle to change select section
	- The granularity of selection can be a word or a letter
	- A toobar can display above the selected text right after selected or after a tap on the selected text
	
#### Setting

- Select Setting Item Wisely
	- Shoud Do
		- Save user preferences
		- Get accessed infrequently
		- Be used by most users
		- Be used by a minority of users, but are essential to supporting their needs
	
	- Should NOT Do
		- Be frequently accessed (Move these to a toolbar)
		- Contain information about the app, such as a version or licensing information (Move these to a Help screen)
		- Manage user accounts (Present these in the main flow of your app, such as a side nav)
		
	- Choose Polite Defaults
		- Represent the selection most users would choose
		- Be neutral and pose little risk
		- Use less battery or mobile data
		- Only interrupt when important

- Organize Setting Item
	- Primary Text : Name the setting precisely and briefly
	- Secondary Text : Explain current setting state or explain what will happen when the select state changes, **Don't REPEAT the words in the section title or primary text**
	- If it's really necessary to offer a long explanation to the setting item, use a seperate page to explain the item and change its state

#### Swipe to Refresh

- When To Use
For dynamic content with a lot of updates frequently, do not use for :
	- Navigation drawers
	- Home screen widgets
	- Pannable content

- Threshold
	- Only when the refreshing icon is fully visible and an ACTION_UP is performed will the refresh be executed
	- Dragging the refresh icon out and in will not trigger the refresh action

### Growth & Communications
How to help users quickly and intuitively understand what they can do with your app, including onboarding, feature discovery, and gesture education.

- First 7 days : 
	- Onboarding: Self-Select model / QuickStart / Top User Benefit
	- User education: Basic guidance on how to use the app

- Within 30 days :
	- Feature discovery: Tips for features and functionality the user hasn’t tried

#### Onboarding (Detailed examples are [here](https://material.io/guidelines/growth-communications/onboarding.html#onboarding-onboarding-models))

|&nbsp;|Self-Select|Quickstart|Top User Benefits|
|---|---|---|---|
|When to use|1. The UI can be customized<br><br>2. Your app has setup and consent requirements|You’ve already identified the behaviors that correspond to increased engagement (in the first session) or increased retention (in the first seven days)|1. Your app is tackling a new challenge or providing a new kind of benefit<br><br>2. To announce new uses or major UI changes|
|When not to use|1. Your app is tackling a new challenge or providing a new kind of benefit<br><br>2. To announce new uses or major UI changes|Your app is tackling a new challenge or providing a new kind of benefit|1. Your app’s UI and benefits use patterns familiar to most users<br><br>2. Your app has no major changes|
|Combinations|Don’t combine Self Select with Top User Benefits|Ok to include setup before first-run experience|1. Don’t combine Top User Benefits with Self Select<br><br>2. It’s okay for your app to show setup after or as part of onboarding|

#### Feature Discovery
Introduce new feature to the users coming back

- Aim for the right user, don't introduce advanced feature to the casual user ( How to categorize the user is the real trick here, but it's a topic of the operational managment actually )

- The right moment to prompt is vital, because triggering at the wrong moment will be intruding and annoying, no user will buy that

|Don’t present upon opening an app|Contextually relevant moments|Natural pauses|
|---|---|---|
|Users may be less likely to find a feature discovery prompt helpful upon opening an app if they’re opening it to take a specific action.<br><br>Avoid displaying feature discovery prompts at interruptive moments.|Present feature discovery prompts at moments when they will help the user better complete the action they’re taking.<br><br>For example, let a user know they can crop an image only after they’ve added an image.|If you can’t set feature discovery prompts to display when triggered by specific actions, display them during natural pauses in the user experience.<br><br>For example, in a mail app, wait until the user has read or sent a message to display a feature discovery prompt.|

#### Gesture Education

- Target
	- Show gesture education only to users who have not performed the gesture
	
- Trigger
	- During the first-run experience (FRE)
	- In later sessions, if a user has not performed the gesture
	- After a major change to the UI
	
- Frequency
	- Most of the gesture education should be displayed **ONCE**, or **TWO** if it's really **critical**
	
### Usability

#### Accessibility
Accessible design allows users of all abilities to navigate, understand, and use your UI successfully.

- Principles
	- Clear
		- Clearly visible elements
		- Sufficient contrast and size
		- A clear hierarchy of importance
		- Key information discernable at a glance

	- Robost
	The app should meet the need of all kinds of users, all kinds of devices to : 
		- **Navigate**: Give users confidence in knowing where they are in your app and what is important
		- **Understand important tasks**: Reinforce important information through multiple visual and textual cues. Use color, shape, text, and motion to communicate what is happening
		- **Access your app**: Include appropriate content labelling to accommodate users who experience a text-only version of your app
		
	- Specific
	The app should work well the assistive technology
	
- Detailed specs are [here](https://material.io/guidelines/usability/accessibility.html#accessibility-color-contrast)

#### Bidirectionality
Used to support secarios like Arabic, dig when needed
