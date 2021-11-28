# Un solo concepto por prueba

<div grid="~ cols-2 gap-2">
<div>

```java

public void testAddMonths() {

    SerialDate d1 = SerialDate.createInstance(31, 5, 2004);

    SerialDate d2 = SerialDate.addMonths(1, d1);

    assertEquals(30, d2.getDayOfMonth());
    assertEquals(6, d2.getMonth());
    assertEquals(2004, d2.getYYYY());

    SerialDate d3 = SerialDate.addMonths(2, d1);

    assertEquals(31, d3.getDayOfMonth());
    assertEquals(7, d3.getMonth());
    assertEquals(2004, d3.getYYYY());

    SerialDate d4 = SerialDate.addMonths(1, SerialDate.addMonths(1, d1));

    assertEquals(30, d4.getDayOfMonth());
    assertEquals(7, d4.getMonth());
    assertEquals(2004, d4.getYYYY());

   }
```

</div>
<div>

```js
describe('Prueba para añadir meses al final de un mes' {
    test('Añadir meses a un mes de 31 días.', () => {
        day1 = serialDate.createInstance(31, 5, 2004);
        day2 = serialDate.addMonths(1, day1);

        expect(day2.getDayOfMonth()).toBe(30);
        expect(day2.getMonth()).toBe(6);
        expect(day2.getYear()).toBe(2004);

        day3 = serialDate.addMonths(2, day1)
        expect(day3.getDayOfMonth()).toBe(31);
        expect(day3.getMonth()).toBe(7);
        expect(day3.getYear()).toBe(2004);
    });
    test('Añadir meses a un mes de 30 días.  ', () => {

        day1 = serialDate.createInstance(30, 6, 2004);
        day2 = serialDate.addMonths(1,day1)

        expect(day4.getDayOfMonth()).toBe(30);
        expect(day4.getMonth()).toBe(7);
        expect(day4.getYear()).toBe(2004);

    });

}
```
</div>
</div>
