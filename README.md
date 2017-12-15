# Material Design
### Material Property
1. material is sheet of 1 dp depth

2. Material can spilt, merge, heal (cutting part from a material, the rest is still a material, 好像壁虎), resize,  translate along x, y and z axis, rotate along x-y plane

3. Material cannot bend, pass through one another

4. User interaction has to be assign to one material, basic, you cannot click two buttons at one time

5. Materials have priority presented by elevation, different elements in different states should show with different elevation as follows ![](https://storage.googleapis.com/material-design/publish/material_v_12/assets/0Bzhp5Z4wHba3VG9SaVpNbkpHb2s/whatismaterial-3d-elevation2.png)

6. detailed elevation data can be represented as follows:


| Elevation (dp) | Component |
| ----- | ----- |
| 24 |	Dialog <br> Picker |
|16 |	Nav drawer <br> Right drawer <br>Modal bottom Sheet|
|12 |	Floating action button (FAB - pressed) |
|9 |	Sub menu (+1dp for each sub menu) |
|8 |	Bottom navigation bar <br> Menu <br> Card (when picked up) <br> Raised button (pressed state) |
|6 |	Floating action button (FAB - resting elevation) <br> Snackbar |
|4 |	App Bar |
| 3 |	Refresh indicator <br> Quick entry / Search bar (scrolled state) |
|2 |	Card (resting elevation) * <br> Raised button (resting elevation)* <br> Quick entry / Search bar (resting elevation) |
| 1 |	Switch |

### Material Motion

1. Material motion should be responsive, meaning the user can be guided quickly and precisely by motion after input( tap, drag, etc.)

2. Motion should be as natural as possible, meaning try to imitate the physical world, where natural motion happens every day under the physical law

3. Motion should be “clever”, that’s another way of being responsive, not only to user input, but also to each other

4. Motion should always have meaning, don’t add motion just for fancy animation, it should guide the user focus to follow your flow

5. Motion should be quick and clear, and most importantly, cohesive. Again, try to imitate the natural world, don’t make sudden changes

6. Use some motion as a bridge when loading is almost always better than just a loading icon

7. The duration of the motion should first be adaptive, there are basically long and complex motion, elements entering and leaving the screen
    - Elements entering the screen occur over 225ms
    - Elements leaving the screen occur over 195ms
    - Large, complex, full-screen transitions may have longer durations, occurring over 375ms
    
8. There is an easing curve for all the motions, the most common ones are standard curve, acceleration curve, deceleration curve and sharp curve

|Android Interpolator|After Effect Description|
|---|---|
| FastOutSlowInInterpolator | After Effect (outgoing velocity: 40%, incoming velocity: 80%) |
|FastOutLinearInInterpolator|After Effect (outgoing velocity: 0%, incoming velocity: 80%)|
|LinearOutSlowInInterpolator|After Effect (outgoing velocity: 40%, incoming velocity: 0%)|
|-|After Effect (outgoing velocity: 40%, incoming velocity: 40%)|

9. All on-screen movements should take the Standard Curve

10. The movement within screen bound should under the impact of gravity, thus should move in an arc way, but only when both x-axis and y-axis has movements

11. Elements entering and exiting the screen should move along one axis ( horizontally or vertically enter and exit the screen, don’t fly in and out from any direction)

12. Elements leaving and entering the screen should be independent from those on-screen movements

13. When entering the screen, Deceleration Curve should used, when permanently leaving the screen, Acceleration Curve should used, and when temporarily leaving the screen, Sharp Curve should be used

14. Elements in and out of the screen can also work with on-screen movements in a relative way, in which case Standard Curve should be used

15. Transformation can have both asymmetric and symmetric way, asymmetric works best when multiple elements change size simultaneously, and symmetric way is best when single element is changed

16. During a transformation, it’s content should expand or shrink along its parent’s pace (Caution for unwanted stretches of images)
17. Radial transformation often happens when an circle ( That is to say, don’t apply this on other source like oval or star) morphs into say a rectangle

18. The center of the radial transformation can be inside the circle or any other place, a translation or cornered expansion could be applied to the transformation ( See [here](https://material.io/guidelines/motion/transforming-material.html#transforming-material-radial-transformation) for more detail)

19. Joining and dividing should involve a little bit of overlapping

20. Always try to maintain a focal point during the motion, some constant visible points are recommended, but there should be too many visible points

21. If the content needs some loading time, leave enough space for it before head, so there won’t be further meaningless movements, take reference from 简书, whose UX can be inspiring if shutting down internet

22. Creating new serface should be connected to user input by rectangle or radial expansion (feels like the user input releashed the new surface)

23. A clear and compact focal path is necessary when multiple surfaces are created 

24. Surface creation without user input should be guided by a combination of scaling, positioning and fading transformation, but use them in a compat way ( One plain example is don't do rebound animation under such circulmstance )

25. Using a radial motion to mark the point of user input and notify that the user input has been received by the app

26. Surface creation without user input should be guided by a combination of scaling, positioning and fading transformation, but use them in a compat way ( One plain example is don't do rebound animation under such circulmstance )

27. Using a radial motion to mark the point of user input and notify that the user input has been received by the app

28. Transformation between two icons can show a explict link between the two icons or the two actions behind the icons ( e.g. The back button and menu button can only be show by clicking the counterpart )

29. Adding an animation that starts with the product icon when user first opens the app can offer a warm welcome to the new users

30. Creating some subtle animation can connect your users with the app in a deeper way ( Use gif to implement it? )

### Material Style

1. In Material Design, a primary color refers to a color that appears most frequently in your app. A secondary color refers to a color used to accent key parts of your UI, **secondary color should be used sparingly**

2. Secondary colors are best used forButtons, floating action buttons, and button textText fields, cursors, and text selectionProgress barsSelection controls, buttons, and slidersLinksHeadlines

3. Use color contrast to show prominence of UI component, thus to organize the components better by importance and increase usability

4. Color can have meanings ( Green is often comfort and red can often be alarming )

5. Color can show the change of state for an UI component ( Such as the pressed and normal state of a button ) Check for an awesome use of EditText state change example in [here](https://material.io/guidelines/style/color.html#color-usability)

6. When displaying text, try to use opacity instead of shifting to gray, common opacity for dark text on light background and light text on dark background are as follows

|Dark text (#000000)|Opacity|
|---|---|
|Primary text|87%|
|Secondary text|54%|
|Disabled text, hint text|38%|
|Dividers|12%|

<br>

|Light text (#FFFFFF)|Opacity|
|---|---|
|Primary text|100%|
|Secondary text|70%|
|Disabled text, hint text|50%|
|Dividers|12%|

7. When displaying icons, such strategy can also be applied to them, the common pattern is as follows

|Dark icons (#000000)|Opacity|
|---|---|
|Active Icon|54%|
|Inactive Icon|38%|

<br>

|Light icons (#000000)|Opacity|
|---|---|
|Active Icon|100%|
|Inactive Icon|50%|

8. Colored text on colored background should be used sparingly, most of the text should use light or dark, only the most important info should be conveyed using colored text

9. Theme is a good thing to offer consistancy, the four elements are covered here
	- Status bar
	- App bar
	- Background
	- Card / Dialogs

> The light and dark theme palette along with their UI application can be checked out [here](https://material.io/guidelines/style/color.html#color-themes)

10. Icon consists of **Product Icon** and **System Icon**, product icons are the expression of your products, services or tools you can provide, system icons express a command, file, device, directory or other common actions, **icons product are 48dp and system icons are 24dp**

11. Icons have two kind of states, active or not and focus or not (in Android, enabled, focused), use opacity to disguish from these states

**Icons on light backgrounds**

|Icon state|Opacity|
|---|---|
|Active + focused|87%|
|Active + unfocused|54%|
|Inactive|38%|

<br>

**Icons on dark backgrounds**

|Icon state|Opacity|
|---|---|
|Active + focused|100%|
|Active + unfocused|70%|
|Inactive|50%|

12. Product icons with 48dp size should have 1dp margin, when scalling, scale the margin with the rest of the icon (e.g. if the icon is 192dp, the margin should  be 4dp)

13. The rest of the icon and imagery part are too design related, it's best to review directly from [here](https://material.io/guidelines/style/imagery.html)

14. **Roboto** and **Noto** are standard typeface on Android (Noto covering those not covered by Roboto)

15. There are 3 categories of languages:
	- English and English like (Latin, Greek, Cyrillic)
	- Dense (Chinese, Japanese, and Korean)
	- Tall (South and Southeast Asian and Middle Eastern language)

The conventions for text size among all the components are as follows:

|-|App bar|Buttons|Subheading|Body 1|
|---|---|---|---|---|
|English|Medium 20sp|Medium 14sp, all caps|Regular 16sp (device), 15sp (desktop)|Regular 14sp (device), 13sp (desktop)|
|Dense|Medium 20sp|Medium 15sp, all caps|Regular 17sp (device), 16sp (desktop)|Regular 15sp (dense), 14sp (desktop)|
|Tall|Medium 20sp|Bold 15sp|Regular 17sp (device), 16sp (desktop)|Regular 15sp (device), 14sp (desktop)|

16. For android, the font stack should specify Roboto, Noto and then sans-serif

17. Line wrapping only applies to body, subheading, headlines and the smaller display style. All the other styles should display in one line

18. Text color should maintian a contrast ratio for better readability (using opacity to control contrastion), the minimum is 4.5:1, the preferred is 7:1, recommended opacity are listed as follows:

|Style|Opacity|
|---|---|
|Display 4|54%|
|Display 3|54%|
|Display 2|54%|
|Display 1|54%|
|Headline|87%|
|Title|87%|
|Subheading|87%|
|Body 2|87%|
|Body 1|87%|
|Cpation|54%|
|Menu|87%|
|Button|87%|

19. Ideal line length for English body text is 40-60 characters per line, for short lines, 15-40 characters per line is preferred

20. Try to use "you", "your", "my", "I" when addressing users, but don't mix them, like

> Quickly open the camera without unlocking your screen

> I agree to follow the Google Terms of Service

21. Avoid using "we" except for situations like "We’ll review your appeal and respond within a few days"

22. Try to be concise, simple and direct

23. Use common words

24. Define glossary, i.e. It's really important using the **same word for same action throughout the app**

25. Use 1,2,3 to say numbers, don't use one, two, three

26. **Never say "never"**

> For more examples and the text for specific UI component, see [here](https://material.io/guidelines/style/writing.html#writing-language)

28. Be friendly, respectful, focus, humble, inviting, positive and essential (examples see the link above)

29. Use sentence style caps (Don't do something like **Search Setting**)

30. Don't specify gender if not necessary

### Material Layout

1. Glossary: A seam is two materials sharing an entire edge, a step is two materials with different z-axis

2. Floating action button can straddle a step if it's related to the content creating that step (Maybe the frontground part? ), and ite can straddle a seam if it's related to both materials, **Don't add decorative seam just to provide anchor point for the button**

3. screen density = screen width (or height) in pixels / screen width (or height) in inches

4. dp = (width in pixels * 160) / screen density (Dp is for Android only)

5. The primary difference between an sp and a dp is that sp preserves a user's font settings. Users who have larger text settings for accessibility will see the font size matched to their text size preferences.

6. Resource scalling in Android, **Really Important!!**

|Screen Resolution|dip|Pixel Ratio|Image Size(pixels)|
|---|---|---|---|
|xxxhdpi|640|4.0|400 x 400|
|xxhdpi|480|3.0|300 x 300|
|xhdpi|320|2.0|200 x 200|
|hdpi|240|1.5|150 x 150|
|mdpi|160|1.0|100 x 100|

7. For some recommended metrics and keyline pattern, check out [here](https://material.io/guidelines/layout/metrics-keylines.html#metrics-keylines-keylines-spacing)

8. Touch targets should be at least 48*48dp. In most cases, there should be 8dp or more space between them.

9. Mobile UI structure usually contains such elements:
	- App bar / primary toolbar
	- Content Area
	- Optional Bottom bar
	- Optional Side Nav
	- Optional Right nav
The construction looks like ![this](https://storage.googleapis.com/material-design/publish/material_v_12/assets/0Bx4BSt6jniD7T0hfM01sSmRyTG8/layout-structure-regions-mobile.png)

10. There are some principles like **Using the whitespace wisely instead of too many regions** and **Breaking edges with cards or floating action buttons (Let them straddle)** or **Use card to organize infomation that need group or seperation**, check them [here](https://material.io/guidelines/layout/structure.html#structure-ui-regions) with multiple image examples

11. App bar / Action bar is a special tool bar for android that serves for navigation, title, app-related icons

12. Default height for app bar is 56dp portrait and 48dp landscape

13. **16dp is the most commonly used margin in Material Design Documentation** (Almost all the elements in the UI structure that has a margin define it to be 16dp)

14. Responsive UI seems to me to be developing different UI for differen display size, anyhow, check [here](https://material.io/guidelines/layout/responsive-ui.html#responsive-ui-patterns) for a richful amount of amazing apply strategy for different displays

15. Split screen looks like some fancy moves to me, but I haven't figured it out what it can do actually, looks like another way of saying responsive UI within one device now.

16. Android status bar height: 24dp

### Material Components

#### Bottom Navigation
	- Usage
		- Three to five top-level destination of similar importace (Use TAB instead when there are two and use navigate drawer when there are six or more)
		- Destinations requiring direct access from anywhere in the app
	
	-Style
		Becuase bottom navigation are presented as icons and text, they should be used for content that can be suitably 
		- When the view is in focus, display that view‘s icon and text
		- When there are only 3 actions, display both icon and text all the time ( But disguish with color )
		- When there are four or five actions, display inactive views as icons only
		- Don’t make text too long (Try to use one  single word)
		- Tapping the active action will navigate the user to the top of the view (iOS taps the actionbar)
		- Navigate through the bottom navigation should reset the view when change ( Doesn't apply for tabs, check out weibo, and the bottom bar itself, shouldn't there exist a situation where user want the exact circumstance be restored, like wechat ios doesn't reset contact when change )
		- Hide the bar when scrolling down, reveal when scrolling up
		- Don't use lateral motion ( ? Why not, wechat is against it)
		
	-Spec
		- Action width should divider screen width by number of actions
		- Minimum : 80dp;  Maximum : 168dp
		- Height : 56dp
		- Icon : 24 * 24dp
		- Alignment : Center Horizontal
		- Padding above icon : 6dp (active) ; 8dp (inactive)
		- Other Padding : 10dp under text, 12dp left and right of text
		- Text : Roboto Regular 14sp (active) ; Roboto Regular 12sp (inactive)
		
	-Spec(Shifting bottom navigation bar)
		- Only active view has visible text label
		- Minimum : 56dp (inactive) ; 96dp (active)
		- Maximum : 96 (inactive) ; 168dp (active)
		- Height : 56dp
		- Icon : 24 * 24dp
		- Alignment : Center Horizontal
		- Padding above icon : 6dp (active) ; 16dp above and below icon (inactive)
		- Other Padding : 10dp under text
		- Text : Roboto Regular 14sp (active)
		
	-Elevation
		Elevation of different UI component can be checked out as follows
		
![here](https://storage.googleapis.com/material-design/publish/material_v_12/assets/0B3321sZLoP_HUW9qLXpZTDhhS1U/components-bottomnavigation-spec-elevation3-.png)
		
#### Bottom Sheets

There are two major bottom sheets, the Modal bottom sheets and persistent bottom sheets

**Modal bottom sheets** are alternative to menus or simple dialogs, can also present [Deep-Linked](https://en.wikipedia.org/wiki/Mobile_deep_linking) contents from other apps, they take foucs of the screen, must be dismissed before interacting with content underlying (like dialog in Android)

	- Usage
		- Present actions in a list or grid as an alternative to menus or simple dialogs
		- Display a context menu, when there is no obvious entry for a menu
		- Prioritize the visibility of the elements they contain
		
	- Style
		- Should maintain a minimum of 8dp distance from the bottom of the app bar
		- The sheet should be compact, the height should be decided by its content
		- Initial height should not pass 16 : 9 ratio
		
	- Behaviour
		- Dismiss by swiping down, touching outside the sheet or touching back button
	

**Persistent bottom sheets** present in-app content (Like map layer in baidu map)

	- Usage
		- To introduce new content on a unique surface
		- To display ocntent equal in value to the primary content
		
	- Style
		- In mobile apps, the persistent bottom sheets are often in full width both portrait and landscape
		- Initial height should not pass 16 : 9 ratio
		
	- Behaviour
		- Dismiss by touching back button or swiping down
	
**Specs for bottom sheets**

	- Font and color
		- Text : Roboto Regular 16sp, #000, 87%
		- Title (Optional) : Roboto Regular 16sp, #000, 54%
		- Default background color : #FFF
		- Transparent overlay : #000 20%
		
	- List Style Bottom Sheet
		- Screen edge left & right margins : 16dp
		- Top and bottom margins : 8dp
		- List-item height : 48dp
		- List icons : 24 * 24dp, center vertical alignment
		- Text associated with icons padding : 32dp horizontal
		
	- List Style Sheet with Header
		- Screen edge left & right margins : 16dp
		- Space below the top list item : 7dp
		- Divider line : 1dp
		- Space above second bottom sheet : 8dp
		- List-item height : 48dp
		- List icons : 24 * 24dp, center vertical alignment
		- Text associated with icon spacing : 32 horizontal
		- List title height : 56dp
		
	- Grid Style Bottom Sheet with Icons
		- Margin on all sides of grid : 24dp
		- Space between grid list rows : 24dp
		- Grid list icons : 48 * 48dp, equally spaced by line
		- Grid list text label : 16sp, center horizontal, below icon
		- Margin between icon and text : 8dp
		
	- Grid Style Bottom Sheet with Header
		- Screen edge left & right margins : 24dp
		- Space below list row : 8dp
		- Divider line : 1dp
		- Space above and below divider line : 8dp
		- List icons : 48 * 48dp, center vertical alignment
		- Grid list text label : 16sp, center horizontal, below icon
		- List title height : 56dp
		
#### Buttons

**Button Types**
	**Floating action button** : A cicular material button that lifts and displays an ink reaction on press <br>![here](https://storage.googleapis.com/material-design/publish/material_v_12/assets/0B7WCemMG6e0VUl95QlVMNXJLU3c/components-buttons-usage1.png)
	**Raised button** : A typically rectangular material button that lifts and isplays ink reactions on press <br>![here](https://storage.googleapis.com/material-design/publish/material_v_12/assets/0B7WCemMG6e0VbDh6YmNiYVc3SHM/components-buttons-usage2.png)	
	**Flat button** : A button made of ink that displays ink reactions on press but does not lift (Like yes and no button in a dialog)<br> ![here](https://storage.googleapis.com/material-design/publish/material_v_12/assets/0B7WCemMG6e0VNDg3V3ZjU2hsNGc/components-buttons-usage3.png)
	
|Context|Button type|
|---|---|
|Dialog|Use flat buttons in dialogs.|
|Inline|Raised buttons or flat buttons can be used for inline buttons.|
|Always available|If your app requires actions to be persistent and readily available, you can use the floating action button or persistent footer buttons.|

**Button Placement**

	- For standard dialog and alike, put buttons along with right with affirmative button on the right
	- For forms and alike, put buttons along with left with affirmative button on the left

**Flat Buttons**

	- Usage
		- On toolbars
		- In dialogs, to unify the button action with the dialog content
		- Inline, with padding, so the user can easily find them but not cause too much distraction at the same time (Consider examples like agreement doc, share buttons, etc)
		
	- Specs
		- Minimum width : 88dp
		- Height : 36dp
		- Corner radius : 2dp
		- Pressed : 40%, #999 (Light Theme) ; 25%, #CCC (Dark Theme)
		- Disabled text : 26%, #000 (Light Theme) ; 30%, #FFF (Dark Theme)
		- Dialog button height : 36dp
		- Dialog button top margin : 24dp
		- Dialog button padding : 8dp
		- Dialog buggon alignment : right 
		- Consider 12% opacity with text color to background color to disguish focused state

**Raised Buttons**

	- Usage
		- Give more prominence to actions in layouts with a lot of varying contnet
		- Help delineate sections of content on a page
		
	- Spec
		- Minimum width : 88dp
		- Height : 36dp
		- Corner radius : 2dp
		- Disabled text : 26%, #000 (Light Theme) ; 30%, #FFF (Dark Theme)
		- Disabled button : 12%, #000 (Light Theme); 12%, #FFF (Dark Theme)
		- Focused : 12%, #000 shade over the color
		- Elevation : default 2dp
	
Persistent footer buttons should define spec the same as flat buttons, only fixed to one window foot

**Dropdown Buttons**

> Dropdown buttons contains three categories, the **Generic overflow dropdown button**, the **Segmented dropdown button** and the **Editable segmented dropdown button**

> The biggest difference between generic overflow to segmented dropdown button is that generic buttons has only one selection, and segmented dropdown buttons have two selections, you have to click the current selected state to fire its action

#### Floating Action Button

	- Usage 
		- To represent the "Most Common Actions"
		- Try to use FAB to represent positive actions
		
|Do|Don't|
|---|---|
|Create<br>Favorite<br>Share<br>Navigate<br>Explore|Archive or Trash<br>Nonspecific actions<br>Alerts or errors<br>Limited tasks like cutting text<br>Controls that should be in a toolbar, like volumn control or changing a font color|
		
	- Spec
		- Default size : 56 * 56dp
		- Mini size : 40 * 40dp
		- Minimal margin : 16dp
		- Interior icon : 24 * 24dp


For more detailed behaviour and interactions of FAB, check out [here](https://material.io/guidelines/components/buttons-floating-action-button.html#buttons-floating-action-button-transitions)

	Basic principles are:
		- FAB are access to primary actions, not flowing menu
		- FAB can transit to full screen, a part of UI layout and a short sheet of material
		- Do not put menu inside the poping up sheet of material


#### Cards

- Usage : Display content that : 
	- As a collection, comprises multiple data types, such as images, movies and text
	- Does not require direct comparison ( a user is not directly comparing images or text )
	- Supports content of highly variable length, such as comments
	- Contains interactive content, such as +1 buttons or comments
	- Would otherwise be in a grid list but needs to display more contnet to supplement the image
	- Use list or tile for homogeneous content
		
- Content
	- Content should be hetergeneous, containing image and text
	- Use hierarchy to direct user's attention, e.g. the primary content should be placed on top of the card
		
- Behaviour ([here](https://material.io/guidelines/components/cards.html#cards-behavior) for detailed examples)
	- Try to use swip and pick-up-and-move gesture
	- Avoid nest scrolling action in the card, especially when there's a scroll bar outside the card

- Actions ( [here](https://material.io/guidelines/components/cards.html#cards-actions) for detailed examples )
	- Actions consists of primary action and supplemental action
	- Primary action is typically the card itself
	- Supplemental Actions are explicitly called out using icons, text, and UI controls, typically put at the bottom of the card
	- Limit supplemental actions to 2, in addition to an overflow menu
	- **Do not** put inlined links inside card text
	
- Content Blocks
Cards may contain the following content blocks:
	- An optional header
	- A primary title (24sp / 14sp ; subtitle : 14sp ; left & right margin : 16dp ; top & bottom margin : 16dp or 24dp, depending on whether a large title or a supporting action is offered)
	- Rich media (16 : 9 or 1 : 1)
	- Supporting text (14sp ; left & right padding : 16dp ; bottom padding : 16dp or 24dp, depending on whether a supporting action is offered)
	- Actions (Padding : 8dp)

- Card Collections
	- Card margins : 8dp (Try responsive by setting margins to 8dp, 16dp, 24dp, 40dp, etc)
	- Card elevation : 2dp (resting, default) ; 8dp (raised)
	
Check out some common combintion of contnet blocks [here](https://material.io/guidelines/components/cards.html#cards-content-blocks)

#### Chips

Chips represent complex entities in small blocks, such as a **contact**(Like when you send emails, to "To:" part)

- Usage
	- A chip may contain a photo, short title and brief information
	- Chips can be expressed in multiple ways, like free form text, predefined text, rules or contacts
	
- Behaviour
	- Click the chip opens the view containing the full detailed info
	- A chip can has a delete or close button inside, click it can dismiss the chip
	
- Specs
	- Height : 32dp
	- Label left padding : 12dp
	- Label right padding : 0dp (Deletable) ; 12dp (Non-Deletable)
	- Remove icon (if needed) : 24 * 24dp ; 54%, black ; margins : 4dp
	
Check out [here](https://material.io/guidelines/components/chips.html#chips-specs) for a detailed version of Contact Chip specs

#### Data Tables

Data tables are mostly for desktops, check [here](https://material.io/guidelines/components/data-tables.html#) for full guide in case of future need

#### Dialogs

- Behaviour
	- Use dialog sparingly to reduce interruption
	- Dialog should always retain focus until dismiss or futher action, try to avoid : 
		- Opening dialog within dialogs
		- Containing scrolling content
	- Full Screen dialogs can open dialogs within it
	- Dialogs with selections can support scrolling (e.g. selecting ringtone)
	- Usually, dismissing can be done by tapping outside the dialog, tapping button back, or trigger some action within the dialog
	
- Alert
	- The affirmative action text should be clear, don't use words like "yes" or "no", use something like "Discard", "cancel" to indicate the action
	- If a title is required:
		- Use a clear question or statement with explanation in the content area, such as "Erase USB storage?"
		- Avoid apologies, ambiguity or questions, such as "Warning!" or "Are you sure?"	

- Simple Dialog
	- Don't add explicit cancel button
	- Touch ouside the dialog or press button back dismiss the dialog
	- Touch any selection on the dialog immediately take effect and dismiss the dialog
	- Dialog should be displayed centered in scren
	- The horizontal margin of the dialog should be at least 40dp, the vertical margins 24dp
	- Content of the dialog should have a margin of at least 24dp
	- Specs
		- Title top padding : 24dp
		- Title bottom padding : 20dp
		- Title text size : Roboto Medium 20sp
		- Title text line height : 28dp
		- Content row height with avatar : 56dp
		- Bottom edge padding : 8dp

- Confirmation Dialog
	- There are explicit confirm buttons and cancel buttons
	- Don't launch dialog within dialog
	- Confirm one single value in one dialog (For multiple values, or launching dialog within dialog, try full-screen dialog)

- Full Screen Dialog
	- Contains multiple actions and tasks
	- Serves as a draft, only take effect the confirm button is clicked (Has to have explicit confirm button and cancel button)
	- Confirm changes and discard changes should have alert dialog within the full-screen dialog
	- Use "X" instead of arrow back on top left to indicate this is a dialog, not a seperate page for better navigation
	- Specs
		- App bar height with a single line of text : 56dp
		- App bar height with two lines of text : 80dp
		- Title text margin left : 72dp
		- Title text : 20sp
		- Title text vertical padding : 20dp
		- Dismissive action padding from left edge : 16dp
		- Affirmative action text : 14sp
		- Affirmative action horizontal padding : 16dp 


- Specs
Most of the specs are covered in the above categorized dialog specs, check out [here](https://material.io/guidelines/components/dialogs.html#dialogs-specs) for a complete spec definition

	- Padding around content area : 24dp
	- Padding between title and body text : 20dp
	- Padding around buttons : 8dp
	- Button height : 36dp
	- Minimum button width : 64dp
	- Action area height : 52dp
	- Dialog elevation : 24dp

#### Dividers

- Usage
	- For lists without anchoring element such as avatar or icon, try to use full-bleed divider to seperate tiles
	- For grid list, use white space and subheaders to seperate content
		
- Types
	- Full-bleed divider go through the whole window to seperate distinct cnotent or create seam between material (could indicate the material to expand when content is expanded)
	- Inset dividers create sections, should be used with anchoring elements
	- Subheaders and dividers used together to reinforce the relationship between the subheaders and its content	
	
- Specs
	- 1dp thick, opacity 12% black in white theme and 12% white in black theme
		
#### Expansion Panel

- Usage
	- A lightweight container that may either stand alone or be connected to a larger surface
	- Can be used to lightweight edit an element value, or to display in a sequence to make a creation flow

- Behaviour
	- Expanded state, collapsed state as its literal meaning, focused state for users with keyboard to navigate
	
- Specs
	- Label : Roboto Regular 15sp
	- Horizontal Padding : 24dp
	- Vertical Padding : 16dp
	
#### Grid Lists

-Usage
	- For homogeneous data, create better visual comprehension and differentiating between similar data type
	- Cell is the basic item in a grid list, tiles hold content and can span one or more cells horizontally or vertically

- Content
	- Should have primary and secondary content, primary should fill the whole grid

- Behaviour
	- Usually grid list only scroll vertically
	- Cut off grid tiles in the view's inital scroll position to indicate there are more content

- Specs
	- Single-line header/footer
		- Height : 48dp
		- Text padding : 16dp
		- Default font size : 16sp
	
	- Two-line header/footer
		- Height : 68dp
		- Text padding : 16dp
		- Defaunt font size for each line : 16sp/12sp or 14sp/12sp
		
	- Image-only grid list
		- Grid list padding : 4dp or 1dp
		
	- Single-line grid list (Text only or text with icon)
		- Height : 48dp
		- Text padding : 16dp
		- Default font size : 16sp
		- Grid list padding : 4dp or 1dp

	- Two-line grid list (Text only or text with icon)
		- Height : 68dp
		- Text padding : 16dp
		- Default font size for each line : 16sp/12sp or 14sp/14sp
		- Grid list padding : 4dp or 1dp

#### List

- Usage
Display homogenous data type of sets of data types

	- Data should be presented in less than 3 lines of text or Card should be used
	- Data shouldn't take image as the primary distinguishing content or grid list should be used

- Content
	- The majority of space on a list tile should be dedicated to the primary action
	- Place the most distinguishing content towards the left of the tile
	- In tiles with multi-line content, place the most distinguishing content in the first line
	- Place supplemental actions on the right side
	
- Specs
The specs contains two many sub-categories, it's best to check out the specific specs according to the layout of your list item [here](https://material.io/guidelines/components/lists.html#lists-specs)

|Layout|Specification|
|---|---|
|Single-line text-only|Font: Roboto Regular 16sp/13sp(densed)<br>Height: 48dp/40dp(densed)<br>Horizontal padding: 16dp<br>Top padding: 8dp/4dp(densed)|
|Single-line text-with-icon|Font: Roboto Regular 16sp/13sp(densed)<br>Height: 48dp/40dp(densed)<br>Icon padding, left: 16dp<br>Text padding, left: 72dp<br>Top padding: 8dp/4dp(densed)|
|Single-line text-with-avatar|Font: Roboto Regular 16sp/13sp(densed)<br>Height: 56dp/48dp(densed)<br>Left avatar padding: 16dp<br>Text padding, left: 72dp<br>Top padding: 8dp/4dp(densed)|
|Single-line text-with-avater-with-icon|Font: Roboto Regular 16sp/13sp(densed)<br>Height: 56dp/48dp(densed)<br>Left avatar padding: 16dp<br>Right icon padding: 16dp<br>Text padding, left: 72dp<br>Top padding: 8dp/4dp(densed)|
|Two-line text-only|Font: Roboto Regular 16sp/13sp(densed)<br>Height: 72dp/60dp(densed)<br>Left and right padding from screen edge: 16dp<br>Top padding: 8dp/4dp(densed)|
|Two-line text-with-icon|Font: Roboto Regular 16sp/13sp(densed)<br>Height: 72dp/60dp(densed)<br>Icon left padding: 16dp<br>Text left padding: 72dp<br>Padding above list: 8dp/4dp(densed)<br>Text right padding: 16dp|
|Two-line text-with-avatar|Font: Roboto Regular 16sp/13sp(densed)<br>Tile height: 72dp/60dp(densed)<br>Icon left padding: 16dp<br>Text left padding: 72dp<br>Padding above list: 8dp/4dp(densed)<br>Text right padding: 16dp|
|Two-line text-with-avatar-with-icon|Font: Roboto Regular 16sp/13sp(densed)<br>Tile height: 72dp/60dp(densed)<br>Icon left padding: 16dp<br>Text left padding: 72dp<br>Padding above list: 8dp/4dp(densed)<br>Text right padding: 16dp|
|Three-line text-only|Font: Roboto Regular 16sp/13sp(densed)<br>Tile height: 88dp/76dp(densed)<br>Text left padding: 16dp<br>Text right padding: 16dp<br>Padding above list: 8dp/4dp(densed)|
|Three-line text-with-icon|Font: Roboto Regular 16sp/13sp(densed)<br>Tile height: 88dp/76dp(densed)<br>Icon left padding: 16dp<br>Text left padding: 72dp<br>Text padding right: 16dp<br>Padding above list: 8dp/4dp(densed)|
|Three-line text-with-avatar|Font: Roboto Regular 16sp/13sp(densed)<br>Tile height: 88dp/76dp(densed)<br>Padding above list: 8dp/4dp(densed)<br>Padding left of avatar: 16dp<br>Text left padding: 72dp<br>Text right padding: 16dp|
|Three-line text-with-avatar-with-icon|Font: Roboto Regular 16sp/13sp(densed)<br>Tile height: 88dp/76dp(densed)<br>Left avatar padding: 16dp<br>Text left padding: 72dp<br>Padding above list: 8dp/4dp(densed)<br>Right and left padding by the icon: 16dp|

- Controls
	- Usage
		- State
		- Primary action (including text strings)
		- Secondary action
		- Secondary info
	
	- Types of Controls, check [here](https://material.io/guidelines/components/lists-controls.html#lists-controls-types-of-list-controls) for detailed examples
		- Checkbox
		- Switch
		- Reorder (Used to drag the list item somewhere else)
		- Expand / Collapse
		- Leave behind

#### Menus

- Usage
	- Context menu : the content changes with the change of app context
	- Action overflow menu : global actions in the whole app with access normally in app bar

- Behaviour
	- Menu has the highest elevation, even higher than dialogs, try not to have a dialog and a menu showing at the same time though
	- For context menu, place current selected item over emmitting item
	- Don't show duplicate item of the selected one
	- Dismissing menu is like dismissing a simple dialog, ouside touch, item touch or back button will do
	- Scrollable menus should always show a scrollbar
	- Text in menu item are always left-aligned
	
- Specs
	- Menu item height: 48dp
	- Menu item text left padding: 16dp
	- Menu item text bottom padding: 20dp
	- Vertical padding : 8dp
	- Typography: 16sp

#### Pickers

- Usage
	- Best used for a confirmation dialog, for date pick or time pick
	- Date picker and time picker should adapt to device orientation

#### Progress & Activity

- Types of Indicators(Check out linear and circular examples [here](https://material.io/guidelines/components/progress-activity.html#progress-activity-types-of-indicators))
	- Determinate : indicate how long an operation will take ( Like buffer progress in an online video player )
	- Indeterminate : visualize an unspecified waiting time (Normal loading progress widget )
	
- Behaviour (Check out video examples [here](https://material.io/guidelines/components/progress-activity.html#progress-activity-behavior))
	- One phase loading : finish all the work in loading and display
	- Two phase loading : finish some work and start displaying, load the rest and display at the same time

#### Selection Controls

- Style 

|Component|Light Theme|Dark Theme|
|---|---|---|
|Checkbox|On: Swatch 500, Opacity 100%<br>Off: #000000, Opacity 54%<br>Disabled: #000000, Opacity 26%|On: Swatch 500, Opacity 100%<br>Off: #FFFFFF, Opacity 70%<br>Disabled: #FFFFFF, Opacity 30%|
|Radio Button|On: Swatch 500, Opacity 100%<br>Off: #000000, Opacity 54%<br>Disabled: #000000, Opacity 26%|On: Swatch 500, Opacity 100%<br>Off: #FFFFFF, Opacity 70%<br>Disabled: #FFFFFF, Opacity 30%|
|Switch|Thumb On: Swatch 500, Opacity 100%<br>Track On: Swatch 500, Opacity 50%<br><br>Thumb Off: Grey 50, #FAFAFA, Opacity 100%<br>Track Off: #000000, Opacity 38%<br><br>Thumb Disabled: Grey 400, #BDBDBD, Opacity 100%<br>Track Disabled: #000000, Opacity 12%|Thumb On: Swatch 200, Opacity 100%<br>Track On: Swatch 200, Opacity 50%<br><br>Thumb Off: Grey 400, #BDBDBD, Opacity 100%<br>Track Off: #FFFFFF, Opacity 30%<br><br>Thumb Disabled: Grey 800, #424242, Opacity 100%<br><br>Track Disabled: #FFFFFF, Opacity 10%|

#### Sliders

- Style for Continuous slider and discrete slider
Check out [here](https://material.io/guidelines/components/sliders.html#sliders-continuous-slider) for detailed examples
	- Light Theme
		- Thumb on: Swatch 500, Opacity 100%
		- Track on: Swatch 500, Opacity 100%

		- Thumb off: #000000, Opacity 26%
		- Track off: #000000, Opacity 26%

		- Focused and Click Thumb off: #000000, Opacity 38% 
		- Focused and Click Track off: #000000, Opacity 38%

		- Disabled (disconnected): #000000, Opacity 26%
		
	- Dark Theme
		- Thumb on: Swatch 200, Opacity 100%
		- Track on: Swatch 200, Opacity 100%

		- Thumb off: #FFFFFF, Opacity 30%
		- Track off: #FFFFFF, Opacity 30%

		- Disabled (disconnected): #FFFFFF, Opacity 30%


#### Snackbars & Toasts

- Usage
	- Show only ONE snack bar at a time
	- Snack bar are lower in elevation than **Dialogs**, **Bottom Sheets** and **Navigation drawers**
	- Toast appear and disappear automatically, user cannot intercept it, snackbar appear automatically, but user can dismiss it by swipe it out of the screen, trigger the action inside it (Toast cannot have actions), or wait for it to dismiss after a timeout
	- Don't use anything other than text in snackbar
	- Add only ONE action at the snackbar, don't add something like dissmiss
	- Don't block FAB (Check out [here](https://material.io/guidelines/components/snackbars-toasts.html#snackbars-toasts-usage) for example)
	
- Specs
	- Single-line snackbar height: 48dp
	- Multi-line snackbar height: 80dp
	- Text: Roboto Regular 14sp
	- Action button: Roboto Medium 14sp, all-caps text
	- Default background fill: #323232 100%
	
#### Steppers

- Usage
	- Steppers break a progress into multiple seperate logical and numbered steps like ![this one](https://storage.googleapis.com/material-design/publish/material_v_12/assets/0B7WCemMG6e0Vb2hCdkt3d05DVUE/components-acux-stepper-vertstep.png)
	- Don't use steppers inside stepper

- Types of **steps**
	- Editable steps : Which user can return later to edit again (Like an online exam, you can always come back and edit your answer before you hand in)
	- Non-editable steps : User cannot edit one the step is completed (Like reading and writing test in ITELTS, they take your paper away once completed)
	- Mobile steps : Like a user guide when fist open an app, marked by dots at the bottom
	- Optional steps

- Types of **steppers**
	- Horizontal steppers
	- Vertical steppers
	- Linear Steppers : User has to finish current step to move to next
	- Non-linear Steppers : User can choose the steps to finish

- Specs
	- Standard stepper 
		- Step height: 72dp
		- Icon top, bottom, and left padding: 24dp
		- Icon right padding: 8dp
		
	- Optional step
		- Step height: 72dp
		- Icon left and right padding: 8dp
		- Label right padding: 8dp
		
	- Alternative Label
		- Step height: 104dp
		- Icon left and right padding: 8dp
		- Label top padding: 16dp
		- Icon and label padding from edge: 24dp
		
	- Non-Linear steppers
		- Backgorund : 6% black
		- Step circle : 24 * 24dp, 12sp Roboto Regular, Text 100% white, 38% black
		
	- Vertical steppers
		- Icon left padding: 24dp
		- Icon alignment with label: Center vertical
		- Icon top and bottom padding: 8dp
		- Label top padding: 24dp
		- Label bottom padding: 16dp
		- Vertical space between steps: 48dp
		- Button height: 48dp
		- Button top padding: 16dp
		
	- Mobile steppers
		- Icon top and bottom padding: 8dp
		- Label top padding: 24dp
		- Label button padding (no sublabel): 16dp
		- Vertical space below inactive step: 40dp
		- Vertical space below active step: 48dp
		- Button height: 48dp

#### Subheaders

- Usage 
	- Subheaders are listed tiles that delineate sections of a list or grid list
	- May be displayed inline with tiles or associated with content
	
- Types
	- List Subheaders
		- Tile height : 48dp
		- Font : Roboto Medium 14sp
		- Color : could either be secondary gray text (54% black) or the primary color of the app
		- Alignment : left align with avatar / icon or text if there's a floating button
		
	- Grid Subheaders
		- Tile height : 48dp
		- Font : Roboto Medium 14sp
		- Alignment : left align with 16dp padding
		
	- Menu Subheaders
		- Tile height : 48dp
		- Font : Roboto Medium 14sp
		- Alignment : left align with 16dp padding
		
#### Tabs

- Usage
	- Use tabs to organize content at a hight level, like to present different sections of a newspaper
	- Don't use tabs to carousal or pagination of content
	- Don't use tabs with content taht support swipe
	- Fixed tabs should be used with a limited number of tabs to aid muscle memory
	- Scrollable tabs should be used when there are viariable number of tabs (check out examples [here](https://material.io/guidelines/components/tabs.html#tabs-types-of-tabs))
		
- Characteristics
	- Present tabs as a single row. Wrap tab labels to a second line if needed, and then truncate
	- Do not include a set of tabbed content within a tab
	- Highlight the tab corresponding to the visible content
	- Group tabs together hierarchically. Connect a group of tabs with its content (check out examples [here](https://material.io/guidelines/components/tabs.html#tabs-content) )
	- Keep tabs adjacent to their content to maintain the relationship between the two
	
- Specs for fixed tabs
	- Min width : 160dp for large view and 72dp for small view
	- Max width : 264dp
	- Consider divider the full window by the number of tabs if it's narrow, and center or align all the tabs left if it's too wide
	- Height : 48dp
	- Horizontal padding : 12dp
	- Padding bottom : 20dp for single line, 12dp for two lines of text
	- Indicator : 2dp, #fff or accent color
	
|Tab Type|Specs|
|---|---|
|Tab with text only|14sp Roboto Medium<br>12sp when wrapped across a maximum of two lines<br>All caps<br>Horizontally and vertically centered<br>Active color: #fff or accent color<br>Unfocused tab color: #fff 70%|
|Tab with icons and text|72dp in height<br>24 * 24dp icons<br>Text and icons are centered horizontally<br>10dp between icon and text<br>16dp under text|
|Tab with icons only|48dp in height<br>24 * 24dp icons<br>Icon is centered in the tab<br>12dp under icon|

- Specs for scrollable tabs
	- Min width : 160dp for large view and 72dp for small view
	- Max width : 264dp or view width minus 56dp
	- Height : 48dp
	- Horizontal padding : 12dp
	- Padding bottom : 20dp for single line, 12dp for two lines of text
	- Indicator : 2dp, #fff or accent color
	- Text
	
		- 14sp Roboto Medium
		- 12sp when wrapped across a maximum of two lines
		- All caps
		- Vertically and horizontally centered
		- Active color: #fff or accent color
		- Unfocused tab color: #fff 70%
		
#### Text Fields

- Principles
	- **Identifiable** : Using a tappable touch target, text fields should indicate that users can enter information
	- **Findable** : It should be easy to find a text field among other elements
	- **Legible** : Text fields should indicate their state – whether enabled or disabled, empty or filled, valid or invalid – with clear label, input, and assistive text

- Layout of elements (It's best to see the image examples [here](https://material.io/guidelines/components/text-fields.html#text-fields-layout))
	- **Label**
	Displaying the required input of the field, could be resting or floating
	
		- Padding top : 16dp
		- Padding bottom : 8dp
		- Padding bottom below input : 8dp (floating mode, check out the image examples)
	
	- **Input Line**
	Indicate where to input, change color to swich from resting to focused state
	
	- **Cursor**
	Indicate the current input position, should only appear upon focused
	
	- **Input Text**
	Could apply auto-complete or suggestions to it
	
		- Vertical Padding : 8dp
		
	- **Placeholder / Hint Text**
	Text displaying when input text is empty
	
		- Vertical Padding : 8dp

	- **Helper Text**
	Helper text gives context about a field's input, such as how the input will be used
	
		- Left aligned
		- It's best to keep it in one line

	- **Error Message**
	Should take the place of helper text if the input is not accepted
	
	- **Required Field**
	Use * to mark a filed as required, or use the (required) / (optional) text to categorize fields
	
	- **Charater or word counter**
	Align right, should be helpful if the input has a word limit, like weibo with limit of 140 characters
	
	- **Icon Signifier**
	Helps to describe the type of input the field requires
	
		- Width : 24dp
		- Padding between icon and text : 16dp
		
	- **Voice input** icon if supported
	
		- Size : 24 * 24dp
		- Align bottom with text, right align
		
	- **Dropdown icon** if supported
	
		- Size : 24 * 24dp
		- Align bottom with text, right align
		
	- **Clear button**
	Try always offer a clear botton if possible
	
		- Size : 24 * 24dp
		- Align bottom with text ,right align

- State
	- Enabled / Disables
	- Idle / Hover / Pressed / Focused
	- Empty / Filled
	- Valid / Invalid

Detailed style is as follows ![](https://storage.googleapis.com/material-design/publish/material_v_12/assets/0B5ZSepuCX1xOb195LU9KWEdIeEk/states.png)

Specs alongside with all those different states are too many to recite, cross reference with the images above and check out specs [here](https://material.io/guidelines/components/text-fields.html#text-fields-states)

- Filled Types
	- Single-line Fields
	- Multi-line Fields
	- Text Area
	
> Personal Opinion : Single-line Fields and Multi-line Fields expected the input to be short, only Multi-line Fields would assume the content typed is important for further input, at least important enough to change the original layout to fit the new content length. Text area on the other hand, expects a long input in the first place

- Input Types
	- Formatted Inputs
		- Grouped Characters ( Like (+86)131 1234 4321 )
		- Prefixes and suffixes ( Like $10 )
		- Password redaction
		
	- Other Inputs
		- Menus and pickers

- Field Variations
	- Labels as headings (Like a dialog with only an input and buttons)
	- Solo fields ( Like a search input )
	- Full-width field ( Like when writing an email )

- Text Boxes
It's ok to add a semi-transparent rectangle background to the input field to increase identification, check out [here](https://material.io/guidelines/components/text-fields.html#text-fields-text-field-boxes) for its specs

#### Toolbars

- Usage
	- Toolbars appear above app content
	- Toolbars shouldn't be split by another sheet of material unless it's something transient like a menu or dialog

#### Tooltips

- Usage
	- Use tooltips for interactive imagery
	- Tooltips should only contain simple text
	
- Interaction
	- A tooltip is triggered by tapping and holding an item. Keep the tooltip displayed as long as the user continues to hold the element
	- On lift, display the tooltip for 1.5 seconds
	- If the user takes another action before that time ends, the tooltip will disappear

- Specs
	- Text: Roboto Medium 14sp
	- Color: Grey 700
	- Opacity: 90%
	- Tile height: 32dp
	- Left and right text padding: 16dp
	- Top margin: 24dp

#### Widgets

- Usage
Home screen widgets display your app’s new and interesting content in a consolidated form. They link to richer detail within the app

- Types of Widgets
	- Information widgets ( Like a clock or weather widget )
	- Collection widgets ( Like a news widget )
		- They can browse a collection
		- They can open an element's detail view
		- They can scroll vertically
		
	- Control widgets ( Like a music player )
	- Hybrid widgets ( Combination of the above )


### Pattern

#### Confirm & Acknowledgement

- Usage
	- Confirming involves asking the user to verify that they want to proceed with an action
	- Acknowledging is displaying text to let the user know that the action they chose has been completed

- Confirmation
	- Use model dialog for confirmation
	- Use title to echo the request action
	- Use the content for detailed explanation
	- Don't confirm for reversable or negligible actions
	
- Acknowledgement
	- Reveals the implicitly done actions
	- Could paire with an undo action
	
#### Data Formats

Different types of numeric and linguistic data are represented using data formats

- Date & Time (Check out for some common practices [here](https://material.io/guidelines/patterns/data-formats.html#data-formats-date-time) if necessary)

	- Talk about date and time
		- Refer to yesterday or tomorrow in those terms
		- If the day is in the upcoming week, display the day of the week (such as Tuesday)
		- Describe a time of day in other ways that promote understanding, such as, “Store open 9:00 AM–Midnight” or “Reminder for tomorrow afternoon”

- Data redaction and Truncation
	- To redact most numbers, like Social Security numbers, use three midline ellipses [• • •]
	- Credit and debit card data must be redacted using four midline ellipses [• • • •]
	- Baseline ellipses [...] represent letters, words, or phrases that aren’t shown. They also represent when a name or email address is only partially visible
	
#### Empty States
	
A list that doesn’t contain any items, or a search that doesn’t display any results, are examples of empty states. Although these states aren’t typical, they should be designed to prevent user confusion

- Displaying Empty States
The most basic empty state displays a non-interactive image and a text tagline

	- Use an image that:
		- Is subtle and neutral with respect to the background
		- Conveys the purpose and potential of the app in a lively way, such as your app's icon
		
	- Include a tagline that:
		- Has a positive tone
		- Is consistent with your brand
		- Conveys the purpose of the app without appearing to be actionable
	
- Avoiding Completely Empty States
There are several situations in which you can provide users with alternatives to truly empty states

	- Starter Content
	The most compelling way for new users to learn and get excited about your app is by using it. Consider providing starter content that will allow users to explore your app right away
	
		- Use content that has broad appeal and demonstrates primary features
		- Give users the ability to delete and replace this content
		- If possible, provide content that's personalized
		
	- Educational Content
	If the purpose of the screen isn't easily conveyed through an image and a tagline, consider showing educational content instead
	
		- Help users understand what they'll be able to do on this screen once it has content
		- Make it possible to dismiss or skip this content
		- Keep it brief
		
	- Best Match
	If nothing exactly matches the user's query, are there any results for a query spelled slightly differently? If so, then show the results, as they may help a user find what they're after
	**Use a heading to prevent from mistaking it as a match**
	
#### Errors

- Usage
	- Common errors occur as 
		- The app does not understand user input
		- The system or app fails
		- A user intends to run incompatible operations concurrently
		
	- When addressing the errors
		- Clearly communicate what is happening
		- Describe how a user can resolve it
		- Preserve as much user-entered input as possible
		
- User Input Errors
Combing the Input in UI Component, try to use helper text, error text, word count text altogether to notify the user the  error in inputs (Check out for specs and image examples [here](https://material.io/guidelines/patterns/errors.html#errors-user-input-errors))

- App Errors
Use dialogs, snack bars or empty page to indicate the error, try to add solution actions if possible ( Like "Try Again" for broken connection )

- Incompatibility
Users try to trigger actions conflicting current phone state, like making phoen calll in airplane mode, or do without permission

If not asked ( Like dynamically request permissions ), try with model dialog described above. When user has manually turned off function, use snackbar with concise explanation and an solution action

#### Fingerprint

- Enrollment
	- Upon opening the app
	- During your app’s purchase flow
	- In your app settings
	- After enrollment

- Icon Spec
	- Background Circle : 40dp
	- Icon : 24dp system icon
	
- Behavioiur
	- Check out MiPay for interaction
	- **Always provide with another way of reauthentication** in case the fingerprint fails
	- Add a way of entering fingerprint authentication in other authentication ways
	
#### Gestures

|Action|Description|Touch mechanics|
|---|---|---|
|Activate|Activates a screen element, like a button|Touch|
|Cancel or Escape|Cancels or escapes out of the current task, as in dialogs or menus|Touch|
|Enable/Disable lights out|Hides or shows a view’s chrome|Touch|
|Data selection (when nothing is selected)|Selects a single element|Long press, two-finger touch|
|Data selection (when items are already selected)|Selects additional elements while in selection mode <br><br>Can use any combination of subsequent one- or two-finger gestures|Touch, two-finger touch|
|Data multi-selection drag|Reveals selection box that originates from point of gesture initiation <br>The height and width can be adjusted based on finger position. <br>The final selection is based on selection box dimensions upon finger(s) lifting.|Two-finger swipe or drag, long-press drag with no items selected|
|Pick up and move|Affects the selected item or items. It can be used to:<br>* Rearrange data within a view<br>* Move an item into a container or onto a target<br>* Reorder items in a list or a card collection|Two-finger long-press drag, long-press drag on selected item|
|Zoom in|Scales up content|Double-touch<br>brDouble-touch drag (down)<br>Pinch open|
|Zoom in to fit|For nested views, scales up the smallest targetable view|Double-touch|
|Zoom out|Scales down content|Double-touch at maximum zoom<br>Double-touch drag (up)<br>Pinch closed<br>Two-finger touch<br>Two-finger double touch|
|Expand|Expands collapsed content|Pinch open|
|Collapse|Collapses expanded content|Pinch closed|
|Rotate|Rotates the targeted content|Rotate|

Check out the drag, swipe and fling detail [here](https://material.io/guidelines/patterns/gestures.html#gestures-drag-swipe-or-fling-details)

#### Help & Feedback
