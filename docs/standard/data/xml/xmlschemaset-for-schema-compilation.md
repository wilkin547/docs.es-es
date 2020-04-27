---
title: XmlSchemaSet para compilación de esquemas
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 55c4b175-3170-4071-9d60-dd5a42f79b54
ms.openlocfilehash: 55347de81c65b7390584415dd29044f4ca4ba02a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709821"
---
# <a name="xmlschemaset-for-schema-compilation"></a>XmlSchemaSet para compilación de esquemas
Describe la clase <xref:System.Xml.Schema.XmlSchemaSet>, una caché en la que se pueden almacenar y validar esquemas del lenguaje de definición de esquemas XML (XSD).  
  
## <a name="the-xmlschemaset-class"></a>La clase XmlSchemaSet  
 <xref:System.Xml.Schema.XmlSchemaSet> es una caché en la que se pueden almacenar y validar esquemas del lenguaje de definición de esquemas XML (XSD).  
  
 En la versión 1.0 de <xref:System.Xml?displayProperty=nameWithType>, los esquemas se cargaban en una clase <xref:System.Xml.Schema.XmlSchemaCollection> como una biblioteca de esquemas. En la versión 2.0 de <xref:System.Xml?displayProperty=nameWithType>, las clases <xref:System.Xml.XmlValidatingReader> y <xref:System.Xml.Schema.XmlSchemaCollection> están obsoletas y se han reemplazado por los métodos <xref:System.Xml.XmlReader.Create%2A> y la clase <xref:System.Xml.Schema.XmlSchemaSet>, respectivamente.  
  
 <xref:System.Xml.Schema.XmlSchemaSet> se introdujo para solucionar una serie de problemas, entre los que se incluyen la compatibilidad con estándares, el rendimiento y el formato obsoleto de esquemas reducidos de datos XML (XDR) de Microsoft.  
  
 A continuación se ofrece una comparación entre la clase <xref:System.Xml.Schema.XmlSchemaCollection> y la clase <xref:System.Xml.Schema.XmlSchemaSet>.  
  
|XmlSchemaCollection|XmlSchemaSet|  
|-------------------------|------------------|  
|Es compatible con los esquemas XML del W3C y del XDR de Microsoft.|Solo es compatible con los esquemas XML del W3C.|  
|Los esquemas se compilan cuando se llama al método <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A>.|Los esquemas no se compilan cuando se llama al método <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>. Esto proporciona una mejora del rendimiento durante la creación de la biblioteca de esquemas.|  
|Cada esquema genera una versión compilada individual que puede generar "islas de esquemas". Como resultado, todas las inclusiones e importaciones solo tienen el ámbito de ese esquema.|Los esquemas compilados generan un esquema único lógico, es decir, un "conjunto" de esquemas. Cualquier esquema importado a un esquema que se haya agregado al conjunto, también se agrega directamente al conjunto. Esto significa que todos los tipos están disponibles para todos los esquemas.|  
|Solo puede haber en la colección un esquema para un espacio de nombres de destino concreto.|Se pueden agregar varios esquemas para el mismo espacio de nombres de destino siempre y cuando no haya conflictos de tipo.|  
  
## <a name="migrating-to-the-xmlschemaset"></a>Migración a XmlSchemaSet  
 En el siguiente código muestra se proporciona una guía para realizar la migración a la nueva clase <xref:System.Xml.Schema.XmlSchemaSet> desde la clase <xref:System.Xml.Schema.XmlSchemaCollection> obsoleta. El código muestra ilustra las siguientes diferencias principales entre las dos clases.  
  
- Al contrario que el método <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A> de la clase <xref:System.Xml.Schema.XmlSchemaCollection>, los esquemas no se compilan al llamar al método <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> de <xref:System.Xml.Schema.XmlSchemaSet>. El método <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> de <xref:System.Xml.Schema.XmlSchemaSet> se llama explícitamente en el código muestra.  
  
- Para iterar sobre <xref:System.Xml.Schema.XmlSchemaSet>, se debe utilizar la propiedad <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> de <xref:System.Xml.Schema.XmlSchemaSet>.  
  
 Éste es el código muestra de <xref:System.Xml.Schema.XmlSchemaCollection> obsoleto.  
  
```vb  
Dim schemaCollection As XmlSchemaCollection = New XmlSchemaCollection()  
schemaCollection.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd")  
schemaCollection.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
  
Dim schema As XmlSchema  
  
For Each schema in schemaCollection  
  
   Console.WriteLine(schema.TargetNamespace)  
  
Next  
```  
  
```csharp  
XmlSchemaCollection schemaCollection = new XmlSchemaCollection();  
schemaCollection.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd");  
schemaCollection.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
  
foreach(XmlSchema schema in schemaCollection)  
{  
   Console.WriteLine(schema.TargetNamespace);  
}  
```  
  
 Éste es el código muestra de <xref:System.Xml.Schema.XmlSchemaSet> equivalente.  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd")  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
schemaSet.Compile()  
  
Dim schema As XmlSchema  
  
For Each schema in schemaSet.Schemas()  
  
   Console.WriteLine(schema.TargetNamespace)  
  
Next  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd");  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
schemaSet.Compile();  
  
foreach(XmlSchema schema in schemaSet.Schemas())  
{  
   Console.WriteLine(schema.TargetNamespace);  
}  
```  
  
## <a name="adding-and-retrieving-schemas"></a>Adición y recuperación de esquemas  
 Los esquemas se agregan a <xref:System.Xml.Schema.XmlSchemaSet> con el método <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> de <xref:System.Xml.Schema.XmlSchemaSet>. Cuando se agrega un esquema a <xref:System.Xml.Schema.XmlSchemaSet>, se asocia a un identificador URI de espacio de nombres de destino. El identificador URI de espacio de nombres de destino se puede especificar como parámetro para el método <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> o, si no se especifica ningún espacio de nombres de destino, <xref:System.Xml.Schema.XmlSchemaSet> utiliza el espacio de nombres de destino que se ha definido en el esquema.  
  
 Los esquemas se recuperan de <xref:System.Xml.Schema.XmlSchemaSet> con la propiedad <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> de <xref:System.Xml.Schema.XmlSchemaSet>. La propiedad <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> de <xref:System.Xml.Schema.XmlSchemaSet> permite iterar sobre los objetos <xref:System.Xml.Schema.XmlSchema> contenidos en <xref:System.Xml.Schema.XmlSchemaSet>. La propiedad <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> devuelve todos los objetos <xref:System.Xml.Schema.XmlSchema> contenidos en <xref:System.Xml.Schema.XmlSchemaSet> o, dado un parámetro de espacio de nombres de destino, devuelve todos los objetos <xref:System.Xml.Schema.XmlSchema> que pertenecen al espacio de nombres de destino. Si se especifica `null` como el parámetro del espacio de nombres de destino, la propiedad <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> devuelve todos los esquemas sin un espacio de nombres.  
  
 En el siguiente ejemplo se agrega el esquema `books.xsd` del espacio de nombres `http://www.contoso.com/books` a <xref:System.Xml.Schema.XmlSchemaSet>, se recuperan todos los esquemas que pertenecen al espacio de nombres `http://www.contoso.com/books` del <xref:System.Xml.Schema.XmlSchemaSet> y, a continuación, se escriben dichos esquemas en <xref:System.Console>.  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet  
schemaSet.Add("http://www.contoso.com/books", "books.xsd")  
  
Dim schema As XmlSchema  
  
For Each schema In schemaSet.Schemas("http://www.contoso.com/books")  
  
   schema.Write(Console.Out)  
  
Next  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/books", "books.xsd");  
  
foreach (XmlSchema schema in schemaSet.Schemas("http://www.contoso.com/books"))  
{  
   schema.Write(Console.Out);  
}  
```  
  
 Para obtener más información sobre cómo agregar y recuperar esquemas de un objeto <xref:System.Xml.Schema.XmlSchemaSet>, vea la documentación de referencia del método <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> y la propiedad <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>  
  
## <a name="compiling-schemas"></a>Compilación de esquemas  
 Los esquemas de <xref:System.Xml.Schema.XmlSchemaSet> se compilan en un solo esquema lógico por medio del método <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> de <xref:System.Xml.Schema.XmlSchemaSet>.  
  
> [!NOTE]
> A diferencia de la clase <xref:System.Xml.Schema.XmlSchemaCollection> obsoleta, los esquemas no se compilan cuando se llama al método <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>.  
  
 Si el método <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> se ejecuta correctamente, la propiedad <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> de <xref:System.Xml.Schema.XmlSchemaSet> se establece en `true`.  
  
> [!NOTE]
> La propiedad <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> no resulta afectada si se editan los esquemas mientras está en <xref:System.Xml.Schema.XmlSchemaSet>. No se realiza un seguimiento de las actualizaciones de los esquemas individuales en <xref:System.Xml.Schema.XmlSchemaSet>. Como resultado, la propiedad <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> puede ser `true` aunque se haya modificado uno de los esquemas contenidos en <xref:System.Xml.Schema.XmlSchemaSet>, siempre y cuando no se hayan agregado ni quitado esquemas de <xref:System.Xml.Schema.XmlSchemaSet>.  
  
 En el siguiente ejemplo, se agrega el archivo `books.xsd` a <xref:System.Xml.Schema.XmlSchemaSet> y, a continuación, se llama al método <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>.  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
schemaSet.Add("http://www.contoso.com/books", "books.xsd")  
schemaSet.Compile()  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/books", "books.xsd");  
schemaSet.Compile();  
```  
  
 Para obtener más información sobre la compilación de esquemas en <xref:System.Xml.Schema.XmlSchemaSet>, vea la documentación de referencia del método <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>.  
  
## <a name="reprocessing-schemas"></a>Reprocesamiento de esquemas  
 El reprocesamiento de un esquema en <xref:System.Xml.Schema.XmlSchemaSet> realiza todos los pasos previos al procesamiento que se deben realizar en un esquema cuando se llama al método <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> de <xref:System.Xml.Schema.XmlSchemaSet>. Si la llamada al método <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> es correcta, la propiedad <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> de <xref:System.Xml.Schema.XmlSchemaSet> se establece en `false`.  
  
 El método <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> se debería utilizar cuando se haya modificado un esquema de <xref:System.Xml.Schema.XmlSchemaSet> después de que <xref:System.Xml.Schema.XmlSchemaSet> haya realizado la compilación.  
  
 En el siguiente ejemplo se ilustra el reprocesamiento de un esquema agregado a <xref:System.Xml.Schema.XmlSchemaSet> utilizando el método <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>. Después de compilar <xref:System.Xml.Schema.XmlSchemaSet> con el método <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> y después de modificar el esquema agregado a <xref:System.Xml.Schema.XmlSchemaSet>, se establece la propiedad <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> en `true` aunque se haya modificado un esquema en <xref:System.Xml.Schema.XmlSchemaSet>. Al llamar al método <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>, se realiza todo el procesamiento previo mediante el método <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> y la propiedad <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> se establece en `false`.  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
Dim schema As XmlSchema = schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
schemaSet.Compile()  
  
Dim element As XmlSchemaElement = New XmlSchemaElement()  
schema.Items.Add(element)  
element.Name = "book"  
element.SchemaTypeName = New XmlQualifiedName("string", "http://www.w3.org/2001/XMLSchema")  
  
schemaSet.Reprocess(schema)  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
XmlSchema schema = schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
schemaSet.Compile();  
  
XmlSchemaElement element = new XmlSchemaElement();  
schema.Items.Add(element);  
element.Name = "book";  
element.SchemaTypeName = new XmlQualifiedName("string", "http://www.w3.org/2001/XMLSchema");  
  
schemaSet.Reprocess(schema);  
```  
  
 Para obtener más información sobre el reprocesamiento de un esquema en <xref:System.Xml.Schema.XmlSchemaSet>, vea la documentación de referencia del método <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>.  
  
## <a name="checking-for-a-schema"></a>Comprobación de un esquema  
 Puede utilizar el método <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> de <xref:System.Xml.Schema.XmlSchemaSet> para comprobar si hay contenido un esquema en <xref:System.Xml.Schema.XmlSchemaSet>. El método <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> toma un espacio de nombres de destino o un objeto <xref:System.Xml.Schema.XmlSchema> para comprobarlos. En cualquiera de los casos, el método <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> devuelve `true` si el esquema está contenido en <xref:System.Xml.Schema.XmlSchemaSet>; de lo contrario, devuelve `false`.  
  
 Para obtener más información sobre la comprobación de un esquema, vea la documentación de referencia del método <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A>.  
  
## <a name="removing-schemas"></a>Cómo quitar esquemas  
 Los esquemas se quitan de un <xref:System.Xml.Schema.XmlSchemaSet> utilizando los métodos <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> y <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> de <xref:System.Xml.Schema.XmlSchemaSet>. El método <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> elimina el esquema especificado de <xref:System.Xml.Schema.XmlSchemaSet>, mientras el método <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> quita el esquema especificado y el resto de los esquemas que importa desde <xref:System.Xml.Schema.XmlSchemaSet>.  
  
 El siguiente ejemplo ilustra cómo agregar varios esquemas a <xref:System.Xml.Schema.XmlSchemaSet> y, a continuación, cómo utilizar el método <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> para quitar uno de los esquemas y todos los esquemas que importa.  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd")  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
schemaSet.Add("http://www.contoso.com/music", "http://www.contoso.com/music.xsd")  
  
Dim schema As XmlSchema  
  
For Each schema In schemaSet.Schemas()  
  
   If schema.TargetNamespace = "http://www.contoso.com/music" Then  
      schemaSet.RemoveRecursive(schema)  
   End If  
  
Next  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd");  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
schemaSet.Add("http://www.contoso.com/music", "http://www.contoso.com/music.xsd");  
  
foreach (XmlSchema schema in schemaSet.Schemas())  
{  
   if (schema.TargetNamespace == "http://www.contoso.com/music")  
   {  
      schemaSet.RemoveRecursive(schema);  
   }  
}  
```  
  
 Para obtener más información sobre cómo quitar esquemas de <xref:System.Xml.Schema.XmlSchemaSet>, vea <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> y la documentación de referencia del método <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A>.  
  
## <a name="schema-resolution-and-xsimport"></a>Resolución de esquemas y xs:import  
 En los siguientes ejemplos se describe el comportamiento de <xref:System.Xml.Schema.XmlSchemaSet> para importar esquemas cuando existen varios esquemas para un espacio de nombres determinado en <xref:System.Xml.Schema.XmlSchemaSet>.  
  
 Por ejemplo, piense en un <xref:System.Xml.Schema.XmlSchemaSet> que contiene múltiples esquemas para el espacio de nombres `http://www.contoso.com`. Se agrega un esquema con la directiva `xs:import` siguiente a <xref:System.Xml.Schema.XmlSchemaSet>.  
  
```xml  
<xs:import namespace="http://www.contoso.com" schemaLocation="http://www.contoso.com/schema.xsd" />  
```  
  
 <xref:System.Xml.Schema.XmlSchemaSet> intenta importar un esquema para el espacio de nombres `http://www.contoso.com` cargándolo desde la URL `http://www.contoso.com/schema.xsd`. En el esquema de importación solo están disponibles los tipos y la declaración de esquema que se declaran en el documento de esquema, aunque hay otros documentos de esquema para el espacio de nombres `http://www.contoso.com` en <xref:System.Xml.Schema.XmlSchemaSet>. Si no se puede encontrar el archivo `schema.xsd` en la URL `http://www.contoso.com/schema.xsd`, no se importa ningún esquema para el espacio de nombres `http://www.contoso.com` al esquema de importación.  
  
## <a name="validating-xml-documents"></a>Validación de documentos XML  
 Los documentos XML se pueden validar con esquemas en <xref:System.Xml.Schema.XmlSchemaSet>. Para validar un documento XML, agregue un esquema a la propiedad <xref:System.Xml.Schema.XmlSchemaSet><xref:System.Xml.XmlReaderSettings.Schemas%2A> de un objeto <xref:System.Xml.XmlReaderSettings> o agregue <xref:System.Xml.Schema.XmlSchemaSet> a la propiedad <xref:System.Xml.XmlReaderSettings.Schemas%2A> de un objeto <xref:System.Xml.XmlReaderSettings>. A continuación, el método <xref:System.Xml.XmlReaderSettings> de la clase <xref:System.Xml.XmlReader.Create%2A> utiliza el objeto <xref:System.Xml.XmlReader> para crear un objeto <xref:System.Xml.XmlReader> y validar el documento XML.  
  
 Para más información sobre la validación de documentos XML con una clase <xref:System.Xml.Schema.XmlSchemaSet>, vea [Validación de esquema XML (XSD) con XmlSchemaSet](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemaset.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A>
- [XmlSchemaSet como una memoria caché de esquema](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [Validación de esquema XML (XSD) con XmlSchemaSet](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemaset.md)
