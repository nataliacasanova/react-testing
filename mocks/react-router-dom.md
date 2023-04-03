# MOCKS

## Use History()

1. Mock the library with the function we need and its return

```
  jest.mock('react-router-dom', () => ({
  ...jest.requireActual('react-router-dom'),
  useHistory: jest.fn(),
}));
```

> We mock the library at the top of the describe to apply to all the test

## Example

**index.tsx**

```
import { useHistory } from 'react-router-dom';

const Button = () => {
      const history = useHistory();
      return ()
}

}));
```

**index.text.tsx**

```
import { useHistory } from 'react-router-dom';

jest.mock('react-router-dom', () => ({
  ...jest.requireActual('react-router-dom'),
  useHistory: jest.fn(),
}));

describe('<Button>', ()=> {
    render(<Button>)
})

```

[<- Atras](../README.md)
