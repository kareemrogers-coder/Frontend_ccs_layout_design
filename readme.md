# Question1

Problem Statement:

In the age of mobile devices, creating web layouts that adjust and adapt to various screen sizes is crucial. Traditional CSS layout techniques often fall short of providing the flexibility and responsiveness needed. CSS Flexbox offers a powerful toolset for designing complex layouts that are both fluid and responsive. This assignment challenges you to leverage CSS Flexbox to build a layout that responds gracefully to different viewport sizes.

**Task 1:**
Create a Basic Flexbox Layout Start by creating a simple webpage layout using Flexbox. Your layout should include a header, a navigation menu, a main content area, and a footer. Utilize flex-direction to make sure your navigation menu is reading horizontally and your main content is reading vertically. Requirements for this task:

Navigation Menu should contain at least 3 things (i.e. Home, Profile, About) and be arranged horizontally on the top of the page.

1. Header section should contain a background image and header text.
```css
.header{
    display:flex;
    position: sticky;
    width: 100%;
    height: 400px;
    border: solid green;
    border-radius: 50%;
    justify-content: center;
    align-items: center;
    background-image: url("images/time.jpeg");
    background-size: cover;
}
```

- Header Text should be bold, contrast color and Centered.

```css
.header nav {
    width: auto;
    height: auto;
    font-size: 50px;
    color: whitesmoke;
    font-weight: bold;
    flex-grow: 0;
    
}
```
- Main Content should contain at least 2 different children divs with content and be arranged vertically stacked on top of one another.
```html
    <div class="container">
        <h3 class="Intro">Intro</h3>
           
            <p class="brief">
                Dr. Stephen Strange, known to the world as Doctor Strange, is a prominent figure in the Marvel Universe, celebrated for his extraordinary abilities as the Sorcerer Supreme. Once a renowned neurosurgeon, his life took a dramatic turn following a catastrophic car accident that left him unable to continue his medical career. Driven by desperation and a quest for healing, Strange’s journey led him to the mystical realms, where he would ultimately become one of the most powerful and influential sorcerers.
            </p>
    </div>
```
- below is the respective css code.
```css
.container {
    display: flex;
    position: sticky;
    flex-wrap: wrap;
    width: 50%;
    height: auto;
    border: solid 2px black; 
}
```
- Footer should contain at least 3 sections (i.e. Contact Us, Events, Blog) and be arranged horizontally.
```html
<footer class="footer">
    <a>Contact Us</a>
    <a>Events</a>
    <a>Blog</a>
</footer>
```


***Task 2 (bonus)**: Implement Responsive Design Modify your Flexbox layout to include responsive design elements. Use media queries to adjust the layout for smaller screens, converting the navigation and footer content areas into a column format when the viewport width is less than 600px.

Expected Outcome: The webpage layout adjusts for smaller screens, with the navigation and main content side by side, while the header and footer span the full width of the viewport.

```css
@media screen and (max-width: 600px){
.container { display: flex;
flex-wrap: wrap;
justify-content: space-between;
}

.brief {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
}

}
```

**Task 3:** Enhance the Layout with Flexbox Properties Further enhance your layout by using Flexbox properties such as justify-content,  and align-items. Adjust these properties to ensure that the main content area takes up the remaining space between the header and footer, and centers the content within the navigation and main content areas.

Expected Outcome: The main content area expands to fill the space between the header and footer. Content within the navigation and main areas is centered, providing a balanced and visually appealing layout.
```css
.header{
    display:flex;
    position: sticky;
    width: 100%;
    height: 400px;
    border: solid green;
    border-radius: 50%;
    justify-content: center;
    align-items: center;
    background-image: url("images/time.jpeg");
    background-size: cover;
}

.header nav {
    width: auto;
    height: auto;
    font-size: 50px;
    color: whitesmoke;
    font-weight: bold;
    flex-grow: 0;
    
}


.container {
    display: flex;
    position: sticky;
    flex-wrap: wrap;
    width: 50%;
    height: auto;
    border: solid 2px black;
    
   
}

.container2 {
    display: flex;
    width: 50%;
    height: auto;
    flex-wrap: wrap;
    border: solid 2px black;
   
}
```

# Question 2

Problem Statement: 

Creating web layouts that are both aesthetically pleasing and functional across a variety of devices is a key challenge in modern web design. CSS Grid offers a powerful and flexible approach to designing web page layouts that can dynamically adjust to screen size, enhancing the user experience. This assignment challenges you to apply CSS Grid techniques to design a responsive web layout that gracefully transitions across different viewing devices.

``` css
.container{
    display: grid;
    width:80%;
    border: 2px solid black;
    margin: 0 auto;
    grid-template-columns: 1fr 4fr; 
    grid-template-rows: 200px 690px 50px;
  
}

.header{
    grid-column-start: 1;
    grid-column-end: 3;
    grid-row-start: 1;
    grid-row-end: 2;
    border: 2px solid black;
    text-align: center;
    align-content: center;
    font-size: 30px;
}

.sidebar{
    grid-column-start: 1;
    grid-column-end: 2;
    grid-row-start: 2;
    grid-row-end: 3;
    font-size: small;
    text-wrap: wrap;
    align-content: center;
    border: 2px solid black;
}

.main_content{
    grid-column-start: 2;
    grid-column-end: 4;
    grid-row-start: 2;
    grid-row-end: 3;
    border: 2px solid black;
    text-align: center;
    align-content: center;
    font-size: 20px;
}

.footer{
    grid-column-start: 1;
    grid-column-end: 3;
    grid-row-start: 3;
    grid-row-end: 4;
    border: 2px solid black;
    text-align: center;
}
```
**Task 2 (bonus)**: Implement Responsive Design Using CSS Grid Modify your CSS Grid layout to be responsive. Use media queries to change the layout for smaller screens by stacking the content and sidebar vertically instead of horizontally.

**Expected Outcome:** The layout changes to a single-column format on screens narrower than 768 pixels, stacking the header, content, sidebar, and footer vertically.

```css
@media screen and (max-width: 890px){
    .container{
        display: grid;
        grid-template-columns: 100%;
        grid-template-rows: 300px 900px 450px 50px;
        gap: 5px;
        width: 95%;
        grid-template-areas: 
        "header"
        "sidebar"
        "main_content"
        "footer";
    }

    .header{
        grid-area: header;
    }

    .sidebar{
        grid-area: sidebar;
        font-size: 20px;
    }

    .main_content{
        grid-area: main_content;

    }
    .footer{
        grid-area: footer;
    }
}
```


