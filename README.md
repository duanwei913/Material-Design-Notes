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













































