# Gsoc-2022-Final-submission Anuja Raj Verma | Wagtail | High Contrast Themes

# Introduction
The Google Summer of Code program has been a great and fun learning experience for me over the past months. The project aimed at improving the accessibility of wagtail in the lens of high contrast themes in windows. The project had two major parts<br></br>
Resolving existing high contrast issues mainly in the Wagtail admin:<br></br>
Most of the contrast and accessibility issues were present in Wagtail’s styleguide. The issues had to be dealt in all themes of the windows contrast themes to improve accessibility of the Admin for all its users<br></br>
 
Accessibility tests and reporting new issues :<br></br>
We can divide the tests into two categories- Automated and manual. The manual accessibility tests were mostly performed using Chrome tools and Windows 11 contrast themes.<br></br>
The Automated testing was performed using pa11y. 

# What is Wagtail
Wagtail is a free and open source content management system (CMS) written in Python. It is popular amongst websites using the Django framework.<br></br>
What is Windows High Contrast and why is it needed<br></br>
Windows High Contrast mode ensures a customized user interface that renders data according to the requirement of the user. Though to some users working without WHCM is a better option, many face visual disabilities and as a result, find the UI difficult to navigate. Therefore to allow all users a satisfactory admin interface we must ensure WHCM is implemented throughout the admin.

# Work Summary
 
## Fixed prior issues mentioned in the  Audits in the UI components, Admin interface, and Wagtail Style Guide which are described below:
##### Issue #1: 
High-contrast mode: buttons with .disabled class look active in high-contrast mode - To resolve this issue I added a PR that added a @media query in forced-colors for the disabled buttons with certain CSS styles to enable better disabled look<br></br>
##### Issue #2: 
Progress Bar not visible in Windows High Contrast Mode - To resolve this issue system colors were added to the components <br></br>
 
## Fixing issues discovered during the GSOC coding period are mentioned below:
##### Issue #3: 
Check Mark is not visible inside the checkbox in the users section of the Admin in Windows High Contrast Mode - To resolve the issue I used media query and forced color : active along with system colors<br></br>
##### Issue #4: 
The icons in the Styleguide, in contrast themes were overridden by forced colors which removed the icon’s original meaning - To achieve the desired result I commented the media query for forced-colors over the icons. The query was added when chrome was having a bug due to which an override on icons using fill (a css property) was required. Since the bug is removed we would want to remove the override too<br></br>
##### Issue #5: 
The boxes(help,critical message and warning boxes) inside the Styleguide were styled oddly giving visual traffic to eyes in Windows High Contrast Mode  - To resolve this issue I added three types of borders to the three kinds of boxes and removed any color from texts or borders. This provides a distinct look as well as more visual clarity to the viewer in Windows High Contrast Mode.Along with border styling the issue pertaining to text inside the first box (help box) in lighter modes of high contrast earlier was not visible<br></br>
##### Issue #6: 
In Windows High Contrast Mode / forced-colors mode, Styleguide’s  dialog component lacks a backdrop, thus making it hard to understand where the component is - To resolve this borders were added to the modal box using forced colors and system colors<br></br>
##### Issue #7: 
In Windows High Contrast Mode/ forced colors mode,tooltip-style "More" dropdowns are missing a border or outline, so it’s hard to tell where the dropdown is - To resolve this I added a transparent border to the component making it visible only in the contrast themes<br></br>
## Fixed Linting issues - Linting the changes while making changes on the frontend is important to reflect changes on the browser. 
Issue #8: While running npm run lint:format in windows, a certain error popped up due to some incorrect format of how it was written as a script inside the packages. This was corrected by changing the format of how it was written particularly for Windows users.<br></br>
## Accessibility Testing 
The accessibility testing was done in two parts, one being manual and the other being automated using pa11y. For most parts of the project we conducted manual testing using Windows Contrast themes and Chrome tools<br></br>
Working with Pa11y - For trying automated testing we preferred pa11y. Since most automated tests were already performed by my mentor Thibaud in his github repository, (https://github.com/thibaudcolas/wagtail-tooling/blob/main/accessibility/pa11y-test.js)I mostly worked with wagtail’s Bakery Demo website for testing pa11y. I conducted automated testing on its few pages and found bugs as shown in the below screenshots:<br></br>


The above issues were reported in the issues of wagtail’s bakery demo repository under the following link : <br></br>
https://github.com/wagtail/bakerydemo/issues/356<br></br>

## Pull Requests
 
### Merged pull requests before GSoC period
https://github.com/wagtail/wagtail/pull/8238
### Merged Pull requests during GSoc period
https://github.com/wagtail/wagtail/pull/8909 </br>
https://github.com/wagtail/wagtail/pull/8719 </br>
https://github.com/wagtail/wagtail/pull/8718 </br>
https://github.com/wagtail/wagtail/pull/8852 </br>
https://github.com/wagtail/wagtail/pull/8853 </br>
https://github.com/wagtail/wagtail/pull/8874 </br>
https://github.com/wagtail/wagtail/pull/8897 </br>
https://github.com/wagtail/wagtail/pull/8729 </br>

## Important Links
Documentation <br></br>
Blog Post About GSoC journey <br></br>
Project Repository: <br></br>
Contrast Themes and Testing
      

 
## Future Aspects
 
I intend to improve this project and also it can act as the starting point for anyone who would be interested in contributing to the project further. A few of the improvements and new features could be the following:</br>
Performing Automated pa11y testing over the Wagtail’s Bakery Demo Admin interface</br>
Extending the contrast improvements to Wagtail’s Bakery Demo site</br>

## Remarks
 
I had a fun and learning experience while working under Wagtail. I was afraid of asking questions initially which I overcame to some extent in the whole journey. I loved the Wagtail community and I got guidance and help whenever I got stuck. I would like to thank especially my mentors Jane, Thibaud and Scott for helping and guiding me throughout the process. I also would like to thank Lb for helping me get comfortable with the open source community during the application period.
