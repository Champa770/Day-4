# Day-4
Forms &amp; Input Elements
**What a form is**
A `<form>` collects user input and sends it somewhere (usually to a server, though we're not covering that submission/backend part yet — just structure and input types today).

```html
<form>
  <!-- inputs go here -->
</form>
```

**Basic form attributes**

```html
<form action="/submit" method="POST">
  ...
</form>
```

- `action` — where the form data is sent
- `method` — how it's sent (`GET` appends data to the URL, `POST` sends it in the request body — don't go deep here, just plant the term, backend weeks will cover it properly)

**Labels — always pair with inputs**

```html
<label for="username">Username</label>
<input type="text" id="username" name="username">
```

`for` on the label must match `id` on the input. This links them — clicking the label focuses the input, and screen readers announce it correctly. Skipping this is a very common beginner mistake.

**Common input types**

```html
<input type="text" placeholder="Enter name">
<input type="email" placeholder="Enter email">
<input type="password" placeholder="Enter password">
<input type="number" placeholder="Enter age">
<input type="date">
<input type="checkbox" id="agree">
<input type="radio" name="gender" value="male"> Male
<input type="radio" name="gender" value="female"> Female
<input type="file">
<input type="submit" value="Submit">
```

- `text` / `email` / `password` / `number` — basic single-line inputs, browser applies built-in validation for `email`/`number`
- `checkbox` — multiple can be selected independently
- `radio` — only one can be selected *within the same `name` group* — this is why `name="gender"` is shared above but `id`s differ
- `file` — lets user upload a file
- `submit` — triggers form submission

**`placeholder` vs `value`**

```html
<input type="text" placeholder="Type here">   <!-- greyed out hint, disappears on typing -->
<input type="text" value="Default text">      <!-- actual pre-filled value, stays until changed -->
```

**Textarea — multi-line input**

```html
<textarea rows="4" cols="30" placeholder="Write your message"></textarea>
```

Not self-closing like `<input>` — it wraps its content (even though it's usually empty).

**Dropdown — select**

```html
<select name="city">
  <option value="delhi">Delhi</option>
  <option value="mumbai">Mumbai</option>
  <option value="dehradun" selected>Dehradun</option>
</select>
```

`selected` pre-selects an option.

**Grouping related fields**

```html
<fieldset>
  <legend>Personal Info</legend>
  <label for="name">Name</label>
  <input type="text" id="name">
</fieldset>
```

`<fieldset>` visually/semantically groups fields, `<legend>` is its title.

**Useful validation attributes**

```html
<input type="text" required>
<input type="text" minlength="3" maxlength="10">
<input type="number" min="1" max="100">
```

`required` blocks submission if empty — built-in browser validation, no JS needed yet.

**Common mistakes**

- Missing `for`/`id` link between `<label>` and `<input>`
- Forgetting `name` attribute — without it, the field's data won't be sent on submit
- Same `name` used for unrelated fields (breaks radio grouping logic, or overwrites data)
- Using `<input type="submit">` and expecting it to work without wrapping everything in `<form>`

**Small practice task**
Build a simple registration form with:

- Text input for name (with proper label)
- Email input
- Password input
- Radio buttons for gender
- A dropdown for city
- A submit button
- Wrap related fields in a `fieldset`
