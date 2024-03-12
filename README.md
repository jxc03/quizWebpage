# quizWebpage
Free Code Camp - Learn accessibility by building a quiz.

## **Step 1** 
Welcome to the first part of the Accessibility Quiz. As you are becoming a seasoned HTML and CSS developer, we have started you off with the basic boilerplate.<br>
Start this accessibility journey by providing a `lang` attribute to your `html` element. This will assist screen readers in identifying the language of the page.

```html
<html lang="en">
```

## **Step 2** 
You may be familiar with the `meta` element already; it is used to specify information about the page, such as the title, description, keywords, and author.<br>
Give your page a `meta` element with an appropriate `charset` value.<br>
The `charset` attribute specifies the character encoding of the page, and, nowadays, `UTF-8` is the only encoding supported by most browsers.

```html
<meta charset="UTF-8">
```

## **Step 3** 
Continuing with the `meta` elements, a `viewport` definition tells the browser how to render the page. Including one betters visual accessibility on mobile, and improves SEO (search engine optimization).<br>
Add a `viewport` definition with a `content` attribute detailing the `width` and `initial-scale` of the page.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

## **Step 4** 
Another important `meta` element for accessibility and SEO is the `description` definition. The value of the `content` attribute is used by search engines to provide a description of your page.<br>
Add a `meta` element with the `name` attribute set to `description`, and give it a useful `content` attribute.

```html
<meta name="description" content="quiz" />
```

## **Step 5** 
Lastly in the `head`, the `title` element is useful for screen readers to understand the content of a page. Furthermore, it is an important part of SEO.<br>
Give your page a `title` that is descriptive and concise.

```html
<title>A Accessibility Quiz Webpage - freeCodeCamp</title>
```

## **Step 6** 
Navigation is a core part of accessibility, and screen readers rely on you to provide the structure of your page. This is accomplished with semantic HTML elements.<br>
Add a `header` and a `main` element to your page.<br>
The `header` element will be used to introduce the page, as well as provide a navigation menu.<br>
The `main` element will contain the core content of your page.

```html
<header></header>
<main></main>
```

## **Step 7** 
Within the `header`, provide context about the page by nesting one `img`, `h1`, and `nav` element.<br>
The `img` should point to `https://cdn.freecodecamp.org/platform/universal/fcc_primary.svg`, and have an `id` of `logo`.<br>
The `h1` should contain the text `HTML/CSS Quiz`.

```html
<img id="logo" src="https://cdn.freecodecamp.org/platform/universal/fcc_primary.svg">
<h1>HTML/CSS Quiz</h1>
<nav></nav>
```

## **Step 8** 
A useful property of an SVG (scalable vector graphics) is that it contains a `path` attribute which allows the image to be scaled without affecting the resolution of the resultant image.<br>
Currently, the `img` is assuming its default size, which is too large. CSS has a `max` function which returns the largest of a set of comma-separated values. For example:<br>
`img {` <br>
  `width: max(250px, 25vw);` <br>
`}`<br>
In this example, `img` elements will have a minimum width of `250px`. And as the viewport grows, the image will grow accordingly to be 25 percent of the viewport width.<br>
Scale the image using its `id` as a selector, and setting the `width` to be the maximum of `100px` or `18vw`.

```css
#logo {
  width: max(100px, 18vw);
}
```

## **Step 9** 
As described in the freeCodeCamp Style Guide, the logo should retain an aspect ratio of `35 / 4`, and have padding around the text.<br>
First, change the `background-color` to `#0a0a23` so you can see the logo. Then, use the `aspect-ratio` property to set the desired aspect ratio to `35 / 4`. Finally, add a `padding` of `0.4rem` all around.

```css
background-color: #0a0a23;
aspect-ratio: 35 / 4;
padding: 0.4rem;
```

## **Step 10** 
Make the `header` take up the full width of its parent container, set its `height` to `50px`, and set the `background-color` to `#1b1b32`. Then, set the `display` to use Flexbox.

```css
<h1>Nutrition Facts</h1>
```

## **Step 11** 
We've provided a basic HTML boilerplate for you.<br>
Create an `h1` element within your `body` element and give it the text `Nutrition Facts`.

```css
h1 {
  color: #f1be32;
  font-size: min(5vw, 1.2em);
}
```

## **Step 12** 
To enable navigation on the page, add an unordered list with the following three list items:<br>
- `INFO`
- `HTML`
- `CSS`<br>

The list items text should be wrapped in anchor tags.

```html
<ul>
    <li>
        <a>INFO</a>
    </li>
    <li>
        <a>HTML</a>
    </li>
    <li>
        <a>CSS</a>
    </li>
</ul>
```

## **Step 13** 
The child combinator selector `>` is used between selectors to target only elements that match the second selector and are a direct child of the first selector.<br>
This can be helpful when you have deeply nested elements and want to control the scope of your styling.<br>
Use the `>` selector to target the unordered list elements within the `nav` elements, and use <i>Flexbox</i> to evenly space the children.

```css
nav > ul {
  display: flex;
  justify-content: space-evenly;
}
```

## **Step 14** 
As this is a quiz, you will need a form for users to submit answers. You can semantically separate the content within the form using `section` elements.<br>
Within the `main` element, create a form with three nested `section` elements. Then, make the form submit to `https://freecodecamp.org/practice-project/accessibility-quiz`, using the correct method.

```html
<form method="post" action="https://freecodecamp.org/practice-project/accessibility-quiz">
  <section></section>
  <section></section>
  <section></section>
</form>
```

## **Step 15** 
To increase the page accessibility, the `role` attribute can be used to indicate the purpose behind an element on the page to assistive technologies. The `role` attribute is a part of the <i>Web Accessibility Initiative (WAI)</i>, and accepts preset values.<br>
Give each of the `section` elements the `region` role.

```html
<section role="region"></section>
<section role="region"></section>
<section role="region"></section>
```

## **Step 16** 
Every `region` role requires a label, which helps screen reader users understand the purpose of the region. One method for adding a label is to add a heading element inside the region and then reference it with the `aria-labelledby` attribute.<br>
Add the following `aria-labelledby` attributes to the `section` elements:<br>
- `student-info`
- `html-questions`
- `css-questions`<br>

Then, within each `section` element, nest one `h2` element with an `id` matching the corresponding `aria-labelledby` attribute. Give each `h2` suitable text content.

```html
<section role="region" aria-labelledby="student-info">
  <h2 id="student-info">Student Information</h2>
</section>
<section role="region" aria-labelledby="html-questions">
  <h2 id="html-questions">HTML Questions</h2>
</section>
<section role="region" aria-labelledby="css-questions">
  <h2 id="css-questions">CSS Questions</h2>
</section>
```

## **Step 17** 
Typeface plays an important role in the accessibility of a page. Some fonts are easier to read than others, and this is especially true on low-resolution screens.<br>
Change the font for both the `h1` and `h2 elements to `Verdana`, and use another web-safe font in the sans-serif family as a fallback.<br>
Also, add a `border-bottom` of `4px solid #dfdfe2` to `h2` elements to make the sections distinct.

```css
h1, h2 {
  font-family: Verdana, sans-serif;
}

h2 {
  border-bottom: 4px solid #dfdfe2;
}
```

## **Step 18** 
To be able to navigate within the page, give each anchor element an `href` corresponding to the `id` of the `h2` elements.

```html
<li><a href="#student-info">INFO</a></li>
<li><a href="#html-questions">HTML</a></li>
<li><a href="#css-questions">CSS</a></li>
```

## **Step 19** 
Filling out the content of the quiz, below `#student-info`, add three `div` elements with a `class` of `info`.<br>
Then, within each `div` nest one `label` element, and one `input` element.

```html
<div class="info"><label></label><input></input></div>
<div class="info"><label></label><input></input></div>
<div class="info"><label></label><input></input></div>
```

## **Step 20** 
It is important to link each `input` to the corresponding `label` element. This provides assistive technology users with a visual reference to the input.<br>
This is done by giving the `label` a `for` attribute, which contains the `id` of the `input`.<br>
This section will take a student's name, email address, and date of birth. Give the `label` elements appropriate `for` attributes, as well as text content. Then, link the `input` elements to the corresponding `label` elements.

```html
<div class="info">
  <label for="name">Name:</label>
  <input id="name">
</div>
<div class="info">
  <label for="email">Emai:</label>
  <input id="email"/>
</div>
<div class="info">
  <label for="age">D.O.B</label>
  <input id="age"/>
</div>
```

## **Step 21** 
Keeping in mind best-practices for form inputs, give each `input` an appropriate `type` and `name` attribute. Then, give the first `input` a `placeholder` attribute.

```html
<div class="info">
  <label for="student-name">Name:</label>
  <input id="student-name" name="student-name" type="text" placeholder="Enter your name..."/>
</div>
<div class="info">
  <label for="student-email">Email:</label>
  <input id="student-email" name="student-email" type="email"/>
</div>
<div class="info">
  <label for="birth-date">D.O.B.:</label>
  <input id="birth-date" name="birth-date" type="date"/>
</div>
```

## **Step 22** 
Even though you added a `placeholder` to the first input element in the previous lesson, this is actually not a best-practice for accessibility; too often, users confuse the placeholder text with an actual input value - they think there is already a value in the input.<br>
Remove the placeholder text from the first `input` element, relying on the `label` being the best-practice.

```html
```

## **Step 23** 
Arguably, `D.O.B.` is not descriptive enough. This is especially true for visually impaired users. One way to get around such an issue, without having to add visible text to the label, is to add text only a screen reader can read.<bbr>
Append a `span` element with a class of `sr-only` to the current text content of the third `label` element.

```html
<label for="birth-date">D.O.B.<span class="sr-only"</span></label>
```

## **Step 24** 
Within the `span` element, add the text `(Date of Birth)`.

```html
<label for="birth-date">D.O.B.<span class="sr-only">(Date of Birth)</span></label>
```

## **Step 25** 
The `.sr-only` text is still visible. There is a common pattern to visually hide text for only screen readers to read.<br>
This pattern is to set the following CSS properties:<br>
`position: absolute;`
`width: 1px;`
`height: 1px;`
`padding: 0;`
`margin: -1px;`
`overflow: hidden;`
`clip: rect(0, 0, 0, 0);`
`white-space: nowrap;`
`border: 0;`
Use the above to define the `sr-only` class.

```css
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}
```

## **Step 26** 
Within the second `section` element, add two `div` elements with a class of `question-block`.<br>
Then, within each `div.question-block` element, add one `p` element with text of incrementing numbers, starting at `1`, and one `fieldset` element with a class of `question`.

```html
<div class="question-block">
  <p>1</p>
  <fieldset class="question"></fieldset>
</div>
<div class="question-block">
  <p>2</p>
  <fieldset class="question"></fieldset>
</div>
```

## **Step 27** 
Each `fieldset` will contain a true/false question.<br>
Within each `fieldset`, nest one `legend` element, and one `ul` element with two options.

```html
<legend></legend>
<ul>
  <li></li>
  <li></li>
</ul>
```

## **Step 28** 
Give each `fieldset` an adequate `name` attribute. Then, give both unordered lists a `class` of `answers-list`.<br>
Finally, use the `legend` to caption the content of the `fieldset` by placing a true/false question as the text content.

```html
<fieldset class="question" name="html-question-1">
  <legend>Question 1</legend>
  <ul class="answers-list">

<fieldset class="question" name="html-question-1">
  <legend>Question 2</legend>
  <ul class="answers-list">
```

## **Step 29** 
To provide the functionality of the true/false questions, we need a set of inputs which do not allow both to be selected at the same time.<br>
Within each list element, nest one `label` element, and within each `label` element, nest one `input` element with the appropriate `type`.

```html
<label>
  <input type="radio"></input>
</label>
```

## **Step 30** 
Add an `id` to all of your radio `input`s so you can link your labels to them. Give the first one an `id` of `q1-a1`. Give the rest of them `id`s of `q1-a2`, `q2-a1`, and `q2-a2`, respectively.

```html
<input type="radio" id="q1-a1"/>
<input type="radio" id="q1-a2"/>
<input type="radio" id="q2-a1"/>
<input type="radio" id="q2-a2"/>

```

## **Step 31** 
Although not required for `label` elements with a nested `input`, it is still best-practice to explicitly link a `label` with its corresponding `input` element.<br>
Now, add a `for` attribute to each of your four `label`s that links the `label` to its corresponding radio `input`.

```html
<label for="q1-a1">
<label for="q1-a2">
<label for="q2-a1">
<label for="q2-a2">
```

## **Step 32** 
Give the `label` elements text such that the `input` comes before the text. Then, give the `input` elements a `value` matching the text.<br>
The text should either be `True` or `False`.

```html
<input type="radio" id="q1-a1" value="True"/> True
<input type="radio" id="q1-a2" value="False"/>False
<input type="radio" id="q2-a1" value="True"/>True
<input type="radio" id="q2-a2" value="False"/>False
```

## **Step 33** 
If you click on the radio inputs, you might notice both inputs within the same true/false fieldset can be selected at the same time.<br>
Group the relevant inputs together such that only one input from a pair can be selected at a time.

```html
<input type="radio" id="q1-a1" value="true" name="question"/>
<input type="radio" id="q2-a1" value="true" name="question2"/>
```

## **Step 34** 
To prevent unnecessary repetition, target the `before` pseudo-element of the `p` element, and give it a `content` property of `"Question #"`.

```css
p::before {
  content: "Question #";
}
```

## **Step 35** 
The final section of this quiz will contain a dropdown, and a text box.<br>
Begin by nesting a `div` with a `class` of `formrow`, and nest four `div` elements inside of it, alternating their `class` attributes with `question-block` and `answer`.

```html
<div class="formrow">
  <div class="question-block"></div>
  <div class="answer"></div>
  <div class="question-block"></div>
  <div class="answer"></div>
</div>
```

## **Step 36** 
Within the `div.question-block` elements, nest one `label` element, and add a `CSS` related question to the `label` text.

```html
<label>Can the CSS margin property accept negative values?</label>
<label>Do you have any questions:</label>
```

## **Step 37** 
Within the first `div.answer` element, nest one required `select` element with three `option` elements.<br>
Give the first `option` element a `value` of `""`, and the text `Select an option`. Give the second `option` element a `value` of `yes`, and the text `Yes`. Give the third `option` element a `value` of `no`, and the text `No`.

```html
<select required>
  <option value="">Select an option</option>
  <option value="yes">Yes</option>
  <option value="no">No</option>
</select>
```

## **Step 38** 
Link the first `label` element to the `select` element, and give the `select` element a `name` attribute.

```html
<label for="answer-options">Can the CSS margin property accept negative values?</label>
<select  id="answer-options" name="answer-options" required>
```

## **Step 39** 
Nest one `textarea` element within the second `div.answer` element, and set the number of rows and columns it has.<br>
Then, give the `textarea` placeholder text describing an example answer.

```html
<textarea rows="4" cols="40" placeholder="What is flexbox?.."></textarea>
```

## **Step 40** 
As with the other `input` and `label` elements, link the `textarea` to its corresponding `label` element, and give it a `name` attribute.

```html
<label for="css-textarea">Do you have any questions:</label>
<textarea id="css-textarea" name="css-questions" rows="5" cols="24" placeholder="Who is flexbox..."></textarea>
```

## **Step 41** 
Do not forget to give your `form` a submit button with the text `Send`.

```html
<input type="submit" value="Send" />
```

## **Step 42** 
Two final semantic HTML elements for this project are the `footer` and `address` elements. The `footer` element is a container for a collection of content that is related to the page, and the `address` element is a container for contact information for the author of the page.<br>
After the `main` element, add one `footer` element, and nest one `address` element within it.

```html
<footer>
  <address></address>
</footer>
```

## **Step 43** 
Within the `address` element, add the following:<br>
`freeCodeCamp<br />`<br>
`San Francisco<br />`<br>
`California<br />`<br>
`USA`<br>
The `br` tags will allow each part of the address to be on its own line and are useful for presenting `address` elements properly.

```html
<address>
  freeCodeCamp<br />
  San Francisco<br />
  California<br />
  USA
</address>
```

## **Step 44** 
The `address` element does not have to contain a physical geographical location. It can be used to provide a link to the subject.<br>
Wrap a link around the text `freeCodeCamp`, and set its location to `https://freecodecamp.org`.

```html
<a href="https://freecodecamp.org">freeCodeCamp</a><br />
```

## **Step 45** 
Back to styling the page. Select the list elements within the navigation bar, and give them the following styles:`<br>
`color: #dfdfe2;`<br>
`margin: 0 0.2rem;`<br>
`padding: 0.2rem;`<br>
`display: block;`<br>

```css
nav > ul > li {
  color: #dfdfe2;
  margin: 0 0.2rem;
  padding: 0.2rem;
  display: block;
}
```

## **Step 46** 
On the topic of visual accessibility, contrast between elements is a key factor. For example, the contrast between the text and the background of a heading should be at least 4.5:1.<br>
Change the font color of all the anchor elements within the list elements to something with a contrast ratio of at least 7:1.

```css
li > a {
  color: #dfdfe2;
}
```

## **Step 47** 
To make the navigation buttons look more like typical buttons, remove the underline from the anchor tags.<br>
Then, create a new selector targeting the navigation list elements so that when the cursor hovers over them, the background color and text color are switched, and the cursor becomes a pointer.

```css
li > a {
  text-decoration: none;
}

nav li:hover {
    background-color: #dfdfe2;
    color: #1b1b32;
    cursor: pointer; 
}
```

## **Step 48** 
Tidy up the `header`, by using Flexbox to put space between the children, and vertically center them.<br>
Then, fix the `header` to the top of the viewport.

```css
justify-content: space-between;
align-items: center;
position: fixed;
top: 0;
```

## **Step 49** 
When the screen width is small, the `h1` does not wrap its text content how it should. Align the text for the `h1` element in the center.<br>
Then, give the `main` padding such that the `Student Info` section header can be fully seen.

```css
h1 {
  color: #f1be32;
  font-size: min(5vw, 1.2em);
  text-align: center;
}

main {
  padding-top: 100;
}
```

## **Step 50** 
On small screens, the unordered list in the navigation bar overflows the right side of the screen.<br>
Fix this by using <i>Flexbox</i> to wrap the `ul` content. Then, set the following CSS properties to correctly align the text:<br>
`align-items: center;`
`padding-inline-start: 0;`
`margin-block: 0;`
`height: 100%;`

```css
nav > ul {
  display: flex;
  justify-content: space-evenly;
  flex-wrap: wrap;
  align-items: center;
  padding-inline-start: 0;
  margin-block: 0;
  height: 100%;
}
```

## **Step 51** 
Set the width of the `section` elements to `80%` of their parent container. Then, use margins to center the `section` elements, adding `10px` to the bottom margin.<br>
Also, ensure the `section` elements cannot be larger than `600px` in width.

```css
section {
  width: 80%;
  margin: 0 auto 10px auto;
  max-width: 600px;
}
```

## **Step 52** 
Replace the top margin of the `h2` elements with `60px` of top padding.

```css
margin-top: 0;
padding-top: 60px;
```

## **Step 53** 
Add padding to the top and left of the `.info` elements, and set the other values to `0`.

```css
.info {
  padding-top: 10px;
  padding-left: 10px;
  padding-right: 0;
  padding-bottom: 0;
}
```

## **Step 54** 
Give the `.formrow` elements top margin, and left and right padding. The other padding values should be `0`.<br>
Then, increase the font size for all `input` elements.

```css
.formrow {
  margin: 10 10 10 0;
  padding-left: 10px;
  padding-right: 10px;
  padding-top: 0;
  padding-bottom: 0;
}

input {
  font-size: 16px;
}
```

## **Step 55** 
To make the first section look more inline, target only the `input` elements within `.info` elements, and set their `width` to `50%`, and left-align their text.

```css
.info input {
  width: 50%;
  text-align: left;
}
```

## **Step 56** 
Target all `label` elements within `.info` elements, and set their `width` to `10%`, and make it so they do not take up less than `55px`.

```css
.info label {
  width: 10%;
  min-width: 55px;
}
```

## **Step 57** 
To align the input boxes with each other, create a new ruleset that targets all `input` and `label` elements within an `.info` element and set the `display` property to `inline-block`.<br>
Also, align the `label` element's text to the right.

```css
.info label, .info input {
  display: inline-block;
  text-align: right
}
```

## **Step 58** 
To neaten the `.question-block` elements, set the following CSS properties:<br>
`text-align: left;`<br>
`display: block;`<br>
`width: 100%;`<br>
`margin-top: 20px;`<br>
`padding-top: 5px;`<br>

```css
.question-block {
  text-align: left;
  display: block;
  width: 100%;
  margin-top: 20px;
  padding-top: 5px;
}
```

## **Step 59** 
Make the paragraph elements appear as a higher priority, with the following CSS properties:<br>
`margin-top: 5px;`<br
`padding-left: 15px;`<br
`font-size: 20px;`<br

```css
p {
  margin-top: 5px;
  padding-left: 15px;
  font-size: 20px; 
}
```

## **Step 60** 
It is useful to see the default border around the `fieldset` elements, during development. However, it might not be the style you want.<br>
Remove the border and bottom padding on the `.question` elements.

```css
.question {
  border: none;
  padding-bottom: 0;
}
```

## **Step 61** 
While `ul`/`li` elements are great at providing bullets for list items, your radio buttons don't need them. You can control what the bullets look with the `list-style` property. For example you can turn your bullets into circles with the following:<br>
`ul {`<br>
  `list-style: circle;`<br>
`}`<br>
Remove the default styling for the `.answers-list` items by setting its style to `none`, and remove the unordered list padding.

```css
.answers-list {
  list-style: none;
  padding: 0;
}
```

## **Step 62** 
Give the submit button a freeCodeCamp-style design, with the following CSS properties:<br>
`display: block;`<br>
`margin: 40px auto;`<br>
`width: 40%;`<br>
`padding: 15px;`<br>
`font-size: 23px;`<br>
`background: #d0d0d5;`<br>
`border: 3px solid #3b3b4f;`<br>

```css
button {
  display: block;
  margin: 40px auto;
  width: 40%;
  padding: 15px;
  font-size: 23px;
  background: #d0d0d5;
  border: 3px solid #3b3b4f;
}
```

## **Step 63** 
Set the `footer` background color to `#2a2a40`, and use Flexbox to horizontally center the text.

```css
footer {
  background-color: #2a2a40;
  display: flex;
  justify-content: center;
}
```

## **Step 64** 
Now, we cannot read the text. Target the `footer` and the anchor element within to set the font color to a color of adequate contrast ratio.

```css
footer, footer a {
  color: #d0d0d5;
}
```

## **Step 65** 
Horizontally center all the text within the `address` element, and add some padding.

```css
address {
  text-align: center;
  padding: 10px;
}
```

## **Step 66** 
Clicking on the navigation links should jump the viewport to the relevant section. However, this jumping can be disorienting for some users.<br>
Select all elements, and set the `scroll-behavior` to `smooth`.

```css
* {
  scroll-behavior: smooth;
}
```

## **Step 67** 
Certain types of motion-based animations can cause discomfort for some users. In particular, people with <i>vestibular</i> disorders have sensitivity to certain motion triggers.<br>
The `@media` at-rule has a media feature called `prefers-reduced-motion` to set CSS based on the user's preferences. It can take one of the following values:<br>
- `reduce`
- `no-preference`<br>

`@media (feature: value) {`<br>
  `selector {`<br>
    `styles`<br>
  `}`<br>
`}`<br> 

Wrap the style rule that sets `scroll-behavior: smooth` within an `@media` at-rule with the media feature `prefers-reduced-motion` having `no-preference` set as the value.

```css
@media (prefers-reduced-motion: no-preference) {
  * {
    scroll-behavior: smooth;
  }
}
```

## **Step 68** 
Finally, the navigation accessibility can be improved by providing keyboard shortcuts.<br>
The `accesskey` attribute accepts a space-separated list of access keys. For example:<br>
`<button type="submit" accesskey="s">Submit</button>`<br>
Give each of the navigation links a single-letter access key.<br>
<i>Note: It is not always advised to use access keys, but they can be useful</i><br>
Well done. You have completed the <i>Accessibility Quiz</i> practice project.

```html
<li><a href="#student-info" accesskey="i">INFO</a></li>
<li><a href="#html-questions" accesskey="h">HTML</a></li>
<li><a href="#css-questions" accesskey="c">CSS</a></li>
```