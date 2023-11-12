# Frontend Mentor - Newsletter sign-up form with success message solution

This is a solution to the [Newsletter sign-up form with success message challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/newsletter-signup-form-with-success-message-3FC1AZbNrv). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)


## Overview

### The challenge

Users should be able to:

- Add their email and submit the form
- See a success message with their email after successfully submitting the form
- See form validation messages if:
  - The field is left empty
  - The email address is not formatted correctly
- View the optimal layout for the interface depending on their device's screen size
- See hover and focus states for all interactive elements on the page

### Screenshot

![](./screenshot.jpg)

Add a screenshot of your solution. The easiest way to do this is to use Firefox to view your project, right-click the page and select "Take a Screenshot". You can choose either a full-height screenshot or a cropped one based on how long the page is. If it's very long, it might be best to crop it.

Alternatively, you can use a tool like [FireShot](https://getfireshot.com/) to take the screenshot. FireShot has a free option, so you don't need to purchase it. 

Then crop/optimize/edit your image however you like, add it to your project, and update the file path in the image above.


### Links

- Solution URL: [GitHub](https://github.com/hasanur82/sign-up)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow
- [React](https://reactjs.org/) - JS library
- [Next.js](https://nextjs.org/) - React framework
- [Styled Components](https://styled-components.com/) - For styles

### What I learned

Use this section to recap over some of your major learnings while working through this project. Writing these out and providing code samples of areas you want to highlight is a great way to reinforce your own knowledge.

To see how you can add code snippets, see below:

#### HTML
```html
<div class="suppot-photo mobile">
    <img src="./assets/images/illustration-sign-up-mobile.svg" alt="illustration sign up mobile svg">
  </div>
  <div class="sign-up-page">
    <!-- Sign-up form start -->
    <div class="suppot-photo desktop">
      <img src="./assets/images/illustration-sign-up-desktop.svg" alt="illustration sign up mobile svg">
    </div>
    <div class="content">
      <h1>Stay updated!</h1>

      <p>Join 60,000+ product managers receiving monthly updates on:</p>

      <ul class="list">
        <li>Product discovery and building what matters</li>
        <li>Measuring to ensure updates are a success</li>
        <li>And much more!</li>
      </ul>

      <form
        action="./sign-up-succesfull.html"
        class="sign-up-form">
        <span>Valid email required</span>
        <input type="email" name="email" id="email" placeholder="email@company.com" required
          oninvalid="
          this.setCustomValidity(' ');
          document.querySelector('.sign-up-form span').style.display='block'
          "
          oninput="
          this.setCustomValidity('');
          document.querySelector('.sign-up-form span').style.display='none'
          " />
        <input type="submit" value="Subscribe to monthly newsletter">
      </form>
    </div>

  </div>
  </div>
```
#### Style Sheet 
```css

body {
    font-family: Roboto-Regular;
    margin: 0;
    padding: 0;
    font-size: 13px;
    background-color: var(--white);
}

h1 {
    font-family: Roboto-Bold;
    font-size: 30px;
    margin-top: 1em;
    color: var(--dark-Slate-Grey);
}

p {
    color: var(--charcoal-Grey);
}

.suppot-photo.desktop img,
.suppot-photo.desktop {
    display: none;
}

.suppot-photo.mobile img,
.suppot-photo.mobile {
    display: block;
    padding: 0;
}


.content {
    margin-inline: 1.2em;
}

.sign-up-Success {
    padding-block: 40%;
}

.list {
    list-style: none;
    padding: 0;
}

.list li {
    display: flex;
    padding-block: .5em;
}

.list li::before {
    content: '';
    display: block;
    height: 2rem;
    width: 2rem;
    background-image: url(./assets/images/icon-list.svg);
    background-size: 1.1rem;
    background-repeat: no-repeat
}

.sign-up-form::before,
.sign-up-form span {
    content: 'Email address';
    font-size: .65em;
    font-weight: 600;
    display: flex;
}

.sign-up-form span {
    float: right;
    color: var(--tomato);
    display: none;
}

input:is([type="email"],
    [type="submit"]) {
    margin-block: .5em;
    padding: 1em;
    border-radius: .4em;
    width: calc(100% - 2em);
    transition: border .15s;
    outline: none;
}

input:user-invalid {
    border: 1px solid var(--tomato);
    background-color: var(--bg-color);
    outline: none;
}

input[type="email"]:focus {
    outline: none;
    color: #000;
    border: 1px solid var(--tomato);
}

input[type="submit"] {
    width: 100%;
    background-color: var(--dark-Slate-Grey);
    color: var(--white);
    cursor: pointer;
    transition: transform .1s;
}

input[type="submit"]:active {
    transform: scale(.95);
    background-color: var(--tomato);
}

input[type="submit"]:hover {
    background-color: var(--tomato);
    border: var(--tomato);
    box-shadow: 0px 0px 7px 0px var(--tomato);
}

.Dismiss {
    width: calc(100% - 2em) !important;
    position: absolute;
    bottom: 3em;
}

.attribution {
    display: none;
}
@media screen and (min-width: 380px) {
    body {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        background: var(--dark-Slate-Grey);
    }

    .content {
        margin-inline: 1.2em;
        margin-block: 1em;
        max-width: 300px;
    }

    .suppot-photo.mobile img {
        display: none;
    }

    .suppot-photo.desktop,
    .suppot-photo.desktop img {
        display: block;
        width: calc(25em - 4%);
    }

    .sign-up-page {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: row-reverse;
        background-color: var(--white);
        border: 5px solid #fff;
        border-radius: 20px;
        padding: .8em;
        overflow: hidden;
    }

    .list li {
        display: flex;
        padding-block: .1em;
    }
    .sign-up-Success{
        display: flex;
        flex-direction: column;
        padding: 0;
    }
    .success-svg{
        float: left;
    }

    main.thanksDiv{
        background-color: var(--white);
        border-radius: 20px;
        display: flex;
    }
    input[type="submit"] {
       position: relative;
       bottom: .1em;
    }
    .Dismiss {
        width: calc(100%) !important;
        position: absolute;
        bottom: 3em;
    }

}
```
#### JS <sub>(For This Not Needed)</sub>
```js
const proudOfThisFunc = () => {
  console.log('🎉')
}
```

If you want more help with writing markdown, we'd recommend checking out [The Markdown Guide](https://www.markdownguide.org/) to learn more.


### Continued development

Use this section to outline areas that you want to continue focusing on in future projects. These could be concepts you're still not completely comfortable with or techniques you found useful that you want to refine and perfect.


### Useful resources

- [Css help](./style-guide.md) - This helped me for Style Sheet Color and font optimazies. I really liked this pattern and will use it going forward.
- [For More Help](https://font-end-editor.readme.io/inactive) - This is an amazing article which helped me finally understand. I'd recommend it to anyone still learning this concept.


## Author

- Website - [World information House](http://winfohouse.blogspot.com/)
- Frontend Mentor - [@hasanur82](https://www.frontendmentor.io/profile/hasanur82)
- Facbook - [@hasanur82](https://www.twitter.com/hasanur82)


## Acknowledgments

It was a easy one. For more like those stay with us. <br><sub style="color: #f1d4a7">See you...