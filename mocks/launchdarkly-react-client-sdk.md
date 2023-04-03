# MOCKS

## Use Flags()

1. Mock the library

```
  jest.mock('launchdarkly-react-client-sdk');

```

2. Declare mock as a varible

```
 const mockFlags = useFlags as jest.Mock;

```

3. Add return of the function we are going to use

```
beforeEach(() => {
  mockFlags.mockReturnValue({
    veh1618PassesSection: true,
    passesCreationWizard: true,
  });
});
```

> Si queremos usar el mismo mock en cada test, lo pondremos en el método _beforeEach()_

## Example

**index.tsx**

```


import { useFlags } from 'launchdarkly-react-client-sdk';

const function Component = () => {
      const { veh1618PassesSection } = useFlags();

}

```

**index.test.tsx**

```

import { useFlags } from 'launchdarkly-react-client-sdk';

jest.mock('launchdarkly-react-client-sdk');
const mockFlags = useFlags as jest.Mock;

beforeEach(() => {
  mockFlags.mockReturnValue({
    veh1618PassesSection: true,
    passesCreationWizard: true,
  });
});
```

[<- Atras](../README.md)
