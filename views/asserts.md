
# Un assert por prueba

#### Esas pruebas llegan a una única conclusión que es rápida y fácil de entender.

```java
   public void testGetPageHierarchyAsXml() throws Exception {

       givenPages(“PageOne”, “PageOne.ChildOne”, “PageTwo”);

       whenRequestIsIssued(“root”, “type:pages”);

       thenResponseShouldBeXML();

   }

   public void testGetPageHierarchyHasRightTags() throws Exception {

       givenPages(“PageOne”, “PageOne.ChildOne”, “PageTwo”);

       whenRequestIsIssued(“root”, “type:pages”);

       thenResponseShouldContain(
         “<name>PageOne</name>”, “<name>PageTwo</name>”, “<name>ChildOne</name>”
       );

   }
```