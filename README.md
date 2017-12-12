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





























