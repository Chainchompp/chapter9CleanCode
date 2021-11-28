# Template Method

<br>

### Para evitar la duplicidad de código se puede usar la duplicidad de código:

<br>

- Las partes de dado y cuando en un @Before
- el resto de cuando dentro del @Test

<br>

### Pero igual la idea es minimizar la cantidad de pruebas.

```js
describe('Test de ejemplo', () => {
  
  beforeEach(() => {
    render(<DisableButton />)
  });

  test('El button debe aparecer habilitado', () => {
    expect(screen.getByRole('button')).not.toBeDisabled()
  });
  test('Al presionar el button se debe deshabilitar', () => {
    fireEvent.click(screen.getByText(/Click to disable button/))
    expect(screen.getByRole('button')).toBeDisabled()
  });
}
```