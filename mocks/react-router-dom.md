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

## Use History() setting path

1. render component setting the pathname

```
render(<SettingsView />, {
      history: createMemoryHistory({
        initialEntries: [
          {
            pathname: 'settings/project/644c075a-9969-4ace-9588-2f7db54b51d3',
          },
        ],
      }),
    });
```

2. test the pathname match when the desired one

```
   expect(history.location.pathname).toEqual('settings/project/644c075a-9969-4ace-9588-2f7db54b51d3');
```

## Example

```
  it('should redirect main view when there is no project to display', () => {

    const { history } = render(<SettingsView />, {
      history: createMemoryHistory({
        initialEntries: [
          {
            pathname: 'settings/project/644c075a-9969-4ace-9588-2f7db54b51d3',
          },
        ],
      }),
    });

    expect(history.location.pathname).toEqual('/');
  });

```

[<- Atras](../README.md)
