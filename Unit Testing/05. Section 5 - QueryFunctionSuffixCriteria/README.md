### Querying for Elements With Different Criteria

React Testing Library provides various query functions, each designed to find elements in different ways. Below are the query functions and their corresponding criteria:

| End of Function Name | Search Criteria                                                    |
|----------------------|--------------------------------------------------------------------|
| `ByRole`             | Finds elements based on their implicit or explicit ARIA role       |
| `ByLabelText`        | Finds form elements based on the text their paired labels contain |
| `ByPlaceholderText`  | Finds form elements based on their placeholder text               |
| `ByText`             | Finds elements based on the text they contain                     |
| `ByDisplayValue`     | Finds elements based on their current value                       |
| `ByAltText`          | Finds elements based on their `alt` attribute                     |
| `ByTitle`            | Finds elements based on their `title` attribute                   |
| `ByTestId`           | Finds elements based on their `data-testid` attribute             |

### When to Use Each Query Function

- Always prefer using query functions ending with `ByRole`. Only use the other query functions if `ByRole` is not an option.

---

### Code Example for DataForm Component

```javascript
import { screen, render } from '@testing-library/react';
import { useState } from 'react';

function DataForm() {
  const [email, setEmail] = useState('asdf@asdf.com');

  return (
    <form>
      <h3>Enter Data</h3>

      <div data-testid="image wrapper">
        <img alt="data" src="data.jpg" />
      </div>

      <label htmlFor="email">Email</label>
      <input 
        id="email"
        value={email}
        onChange={e => setEmail(e.target.value)}
      />

      <label htmlFor="color">Color</label>
      <input id="color" placeholder="Red" />

      <button title="Click when ready to submit">
        Submit
      </button>
    </form>
  );
}

render(<DataForm />);
```

---

`title` attribute in a button tells the text of the onHovering tooltip.

---

### Test Case for Selecting Different Elements

```javascript
test('selecting different elements', () => {
  render(<DataForm />);

  const elements = [
    screen.getByRole('button'),
    screen.getByText(/enter/i),

    screen.getByLabelText(/email/i),
    screen.getByPlaceholderText('Red'),
    screen.getByDisplayValue('asdf@asdf.com'),
    screen.getByAltText('data'),
    screen.getByTitle(/ready to submit/i),

    screen.getByTestId('image wrapper')
  ];

  for (let element of elements) {
    expect(element).toBeInTheDocument();
  }
});
```
