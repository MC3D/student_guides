# HTML Forms

## [<form>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)

The <form> element is a container element. It does not have visual impact.

We use <input>, <select>, <checkbox>, <button> elements, and others, to build the body of the <form>.

A form ...

- represents a document section containing interactive controls for submitting information
- the `action` attribute specifies WHERE to send the form data (it specifies the URL that processes the form submission)
- the `method` attribute specifies WHICH `HTTP` method to use (the `HTTP` method to submit the form with)

## The [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element

- used to create a variety of different interactive controls, including:

  - button
  - date
  - number
  - password
  - submit
  - text
  - time

- The [type](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#type) attribute specifies the type of control (`type` impacts behavior and appearance).
- The [`placeholder`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#placeholder) attribute specifices the text that appears when no value is set (provides a brief hint to the user as to what kind of information is expected in the field).
- The [`name`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#name) attribute specifies a name for the input control, and the name is sumbitted along with it's value when the form data is submitted to the server. UNLESS YOU HAVE A REASON NOT TO, ALWAYS ADD THE NAME ATTRIBUTE!

## The [`label`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label) element

Associating a `<label>` with an `<input>` element offers some major advantages:

- a screen reader will read out the label when the user is focused on the form input, making it easier for an assistive technology user to understand what data should be entered
- when a user clicks or touches a label, the browser passes the focus to its associated input

To associate a `<label>` with an `<input>`, give the `<input>` an `id` attribute that matches the `<label>` `for` attribute.

```
<label for="username">Enter your username:</label>
<input id="username">
```

Alternatively, you can nest the `<input>` directly inside the `<label>`, in which case the `for` and `id` attributes are not needed because the association is implicit. THIS IS LESS COMMON.

```
<label>Do you like peas?
  <input type="checkbox" name="peas">
</label>
```

## HTML [`button`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) element

The <button> HTML element is an interactive element that, when activated, performs a programmable action, such as submitting form data to a server or opening a dialog.

**The [type](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button#attr-type) attribute**

The `type` attribute sets a `<button>`'s default behavior.

- If you have a `<button>` inside a `<form>`, the button will submit the `<form>` data to the server if (1) no value is set or (2) if the value is set to `submit`. ALWAYS SET THE VALUE!
- If the `type` attribute value is set to 'button', the button has no default behavior when pressed.

**Should you use `<button>` or `<input>`?**

Buttons created with the `<button>` element function just like buttons created with the IN`<input>` element, but they offer richer rendering possibilities.

- you can nest elements within a `<button>` (it can have content)
- elements that have content, can also have pseudo elements

You will see both `<input>` and `<button>` elements used professionally.

## Instructor Demo

Create a form that, when submitted, navigates the user to a Google search results page.

- <form action='https://www.google.com/search'></form>
- <input type='text' name='q' />
- <button type='submit'>Google it!<button>

## HTML [<input type="checkbox>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox)

<input> elements of type **checkbox** are rendered by default as boxes that are checked (ticked) when activated

- Make sure you label your checkboxes, otherwise, it is confusing!
- You can set whether or not the checkbox is checked by default by adding the `checked` attribute.

## HTML [<input type="radio">](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/radio)

<input> elements of type `radio` are generally used in radio groups—collections of radio buttons describing a set of related options.

- Unlike a `checkbox`, only one `radio` button in a given group can be selected at the same time.
- A radio group is defined by giving each of radio buttons in the group the same `name`.
- The `value` attribute is a string containing the radio button's value. This is the value that is submitted with the form

## HTML [<select>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) and [<option>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) elements

The <select> HTML element represents a control that provides a menu of options.

The <option> HTML element is used to define an item contained in a <select>, an <optgroup>, or a <datalist> element. As such, <option> can represent menu items in popups and other lists of items in an HTML document.

- The <select> `name` attribute is used to specify the name of the control.
- The <option> `value` attribute is the value to be submitted with the form.

**In case you were wondering?**

The [<datalist>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/datalist) HTML element contains a set of <option> elements that represent recommended options and users are free to select one of the suggested values or type in their own value.

The [<optgroup>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/optgroup) HTML element creates a grouping of options within a <select> element.

## HTML [<input type="range">](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/range) element

<input> elements of type range let the user specify a numeric value which must be no less than a given value (`min` attribute), and no more than another given value (`max` attribute).

```
<input type="range" id="volume" name="volume"
         min="0" max="11">
```

## HTML [<textarea>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element

The <textarea> HTML element represents a multi-line plain-text editing control, useful when you want to allow users to enter a sizeable amount of free-form text.

## [Client-side form validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)

There are two different types of client-side validation that you'll encounter on the web:

- Built-in form validation uses HTML form validation features
- JavaScript validation is coded using JavaScript

For now, we're focusing on built-in form validation.

- [required](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/required): Specifies whether a form field needs to be filled in before the form can be submitted.
- [minlength](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/minlength) and [maxlength](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/maxlength): Specifies the minimum and maximum length of textual data (strings).
- [min](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/min) and [max](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/max): Specifies the minimum and maximum values of numerical input types.
- type: Specifies whether the data needs to be a number, an email address, or some other specific preset type.
- [pattern](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/pattern): Specifies a regular expression that defines a pattern the entered data needs to follow.

## Validating forms using JavaScript (before server side validation takes hold)!

You must use JavaScript if you want to take control over the look and feel of native error messages.

You can read about the different ways of doing this [here](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#validating_forms_using_javascript).
