# Custom Radio Button Styling

This project demonstrates how to create a custom-styled radio button using HTML and CSS. The radio button features dynamic styles for both checked and unchecked states.

## Features

- **Custom Appearance:** The default radio button appearance is overridden to provide a custom design.
- **Unchecked State:** 
  - Border is black.
  - The inner dot is white.
- **Checked State:**
  - Border color changes to `#8BD3C8`.
  - The inner dot changes to black.

## Code Overview

The custom styling is achieved using CSS, particularly with the use of `appearance: none` to remove the default browser styling of the radio button. The project also uses `::after` pseudo-elements to create the inner dot and apply different styles based on whether the radio button is checked or unchecked.

### HTML Structure

The HTML structure is minimal, consisting of an input element of type `radio` and a corresponding label:

```html
<center>
    <h3>Custom Radio Button with Dynamic Styles</h3>
    <input type="radio" id="specifyColor" name="radio1" value="GFG">
    <label for="specifyColor">GFG</label>
</center>
/* Hide the default radio button appearance */
input[type="radio"] {
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    border: 2px solid black;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    position: relative;
    background-color: white;
}

/* Unchecked state: inner dot is white */
input[type="radio"]::after {
    content: '';
    width: 12px;
    height: 12px;
    background-color: white; /* White inner dot */
    border-radius: 50%;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}

/* Checked state: inner dot is black and border color changes */
input[type="radio"]:checked {
    border-color: #8BD3C8;
}

input[type="radio"]:checked::after {
    background-color: black; /* Black inner dot when checked */
}
