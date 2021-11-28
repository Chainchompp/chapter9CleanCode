


<div grid="~ cols-2 gap-2">
<div>

```java 

 public void testGetPageHieratchyAsXml() throws Exception
   {
     crawler.addPage(root, PathParser.parse(“PageOne”));
     crawler.addPage(root, PathParser.parse(“PageOne.ChildOne”));
     crawler.addPage(root, PathParser.parse(“PageTwo”));

     request.setResource(“root”);

     request.addInput(“type”, “pages”);

     Responder responder = new SerializedPageResponder();

     SimpleResponse response =
       (SimpleResponse) responder.makeResponse(
          new FitNesseContext(root), request);

     String xml = response.getContent();

     assertEquals(“text/xml”, response.getContentType());
     assertSubString(“<name>PageOne</name>”, xml);
     assertSubString(“<name>PageTwo</name>”, xml);
     assertSubString(“<name>ChildOne</name>”, xml);
   }
```

</div>
<div>

```java 

   public void testGetPageHierarchyAsXml() throws Exception {

     makePages(“PageOne”, “PageOne.ChildOne”, “PageTwo”);

     submitRequest(“root”, “type:pages”);

     assertResponseIsXML();

     assertResponseContains(

       “<name>PageOne</name>”, “<name>PageTwo</name>”, “<name>ChildOne</name>”

     );

   }
```

</div>
</div>



