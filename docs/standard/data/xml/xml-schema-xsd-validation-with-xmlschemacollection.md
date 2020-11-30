---
title: Validación de esquemas XML (XSD) con XmlSchemaCollection
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ad0b5717-3d32-41ad-a4d7-072c3e492b82
ms.openlocfilehash: bd6bb440a00b3e485f4e6794e538f761267236b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733014"
---
# <a name="xml-schema-xsd-validation-with-xmlschemacollection"></a>Validación de esquemas XML (XSD) con XmlSchemaCollection

Puede utilizar <xref:System.Xml.Schema.XmlSchemaCollection> para validar un documento XML con esquemas del lenguaje de definición de esquemas XML (XSD). <xref:System.Xml.Schema.XmlSchemaCollection> mejora el rendimiento al almacenar esquemas en la colección para que no se carguen en memoria cada vez que se produce la validación. Si el esquema está en la colección de esquemas, el atributo `schemaLocation` se utiliza para buscarlo en dicha colección.  
  
> [!IMPORTANT]
> La clase <xref:System.Xml.Schema.XmlSchemaCollection> está obsoleta y ha sido reemplazada por la clase <xref:System.Xml.Schema.XmlSchemaSet>. Para más información sobre la clase <xref:System.Xml.Schema.XmlSchemaSet>, vea [XmlSchemaSet para compilación de esquemas](xmlschemaset-for-schema-compilation.md).  
  
 En el ejemplo siguiente se muestra el elemento raíz de un archivo de datos.  
  
```xml  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema"  
    xmlns="urn:bookstore-schema"  
    elementFormDefault="qualified"  
    targetNamespace="urn:bookstore-schema">  
```  
  
 Para este ejemplo, el valor del atributo `targetNamespace` es `urn:bookstore-schema`, que es el mismo espacio de nombres que se ha utilizado al agregar el esquema a <xref:System.Xml.Schema.XmlSchemaCollection>.  
  
 El siguiente código de ejemplo agrega un esquema XML a <xref:System.Xml.Schema.XmlSchemaCollection>.  
  
```vb  
Dim xsc As New XmlSchemaCollection()  
' XML Schema.  
xsc.Add("urn:bookstore-schema", schema)
reader = New XmlTextReader(filename)  
vreader = New XmlValidatingReader(reader)  
vreader.Schemas.Add(xsc)  
```  
  
```csharp  
XmlSchemaCollection xsc = new XmlSchemaCollection();  
// XML Schema.  
xsc.Add("urn:bookstore-schema", schema);  
reader = new XmlTextReader (filename);  
vreader = new XmlValidatingReader (reader);  
vreader.Schemas.Add(xsc);  
```  
  
 Generalmente, se utiliza el atributo `targetNamespace` al agregar la propiedad `namespaceURI` en el método <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A> para <xref:System.Xml.Schema.XmlSchemaCollection>. Puede especificar una referencia nula antes de agregar el esquema a <xref:System.Xml.Schema.XmlSchemaCollection>. Se debería utilizar una cadena vacía ("") para los esquemas que no tengan un espacio de nombres. <xref:System.Xml.Schema.XmlSchemaCollection> solo puede tener un esquema sin espacio de nombres.  
  
 El siguiente código de ejemplo agrega un esquema XML, HeadCount.xsd, a <xref:System.Xml.Schema.XmlSchemaCollection> y valida HeadCount.xml.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Schema  
  
Namespace ValidationSample  
  
   Class Sample  
  
      Public Shared Sub Main()  
         Dim tr As New XmlTextReader("HeadCount.xml")  
         Dim vr As New XmlValidatingReader(tr)  
  
         vr.Schemas.Add("xsdHeadCount", "HeadCount.xsd")  
         vr.ValidationType = ValidationType.Schema  
         AddHandler vr.ValidationEventHandler, AddressOf ValidationHandler  
  
         While vr.Read()  
         End While  
         Console.WriteLine("Validation finished")  
      End Sub  
      ' Main  
  
      Public Shared Sub ValidationHandler(sender As Object, args As ValidationEventArgs)  
         Console.WriteLine("***Validation error")  
         Console.WriteLine("Severity:{0}", args.Severity)  
         Console.WriteLine("Message:{0}", args.Message)  
      End Sub  
      ' ValidationHandler  
   End Class  
   ' Sample  
End Namespace  
' ValidationSample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Schema;  
  
namespace ValidationSample  
{  
   class Sample  
   {  
      public static void Main()  
      {  
         XmlTextReader tr = new XmlTextReader("HeadCount.xml");  
         XmlValidatingReader vr = new XmlValidatingReader(tr);  
  
         vr.Schemas.Add("xsdHeadCount", "HeadCount.xsd");  
         vr.ValidationType = ValidationType.Schema;  
         vr.ValidationEventHandler += new ValidationEventHandler (ValidationHandler);  
  
         while(vr.Read());  
         Console.WriteLine("Validation finished");  
      }  
  
      public static void ValidationHandler(object sender, ValidationEventArgs args)  
      {  
         Console.WriteLine("***Validation error");  
         Console.WriteLine("\tSeverity:{0}", args.Severity);  
         Console.WriteLine("\tMessage  :{0}", args.Message);  
      }  
   }  
}  
```  
  
 A continuación se describe el contenido del archivo de entrada, HeadCount.xml, que se va a validar.  
  
```xml  
<!--Load HeadCount.xsd in SchemaCollection for Validation-->  
<hc:HeadCount xmlns:hc='xsdHeadCount'>  
   <Name>Waldo Pepper</Name>  
   <Name>Red Pepper</Name>  
</hc:HeadCount>  
```  
  
 A continuación se describe el contenido del archivo de esquema XML, HeadCount.xsd, con el que se realizará la validación.  
  
```xml  
<xs:schema xmlns="xsdHeadCount" targetNamespace="xsdHeadCount" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
   <xs:element name='HeadCount' type="HEADCOUNT"/>  
   <xs:complexType name="HEADCOUNT">  
      <xs:sequence>  
         <xs:element name='Name' type='xs:string' maxOccurs='unbounded'/>  
      </xs:sequence>  
      <xs:attribute name='division' type='xs:int' use='optional' default='8'/>  
   </xs:complexType>  
</xs:schema>  
```  
  
 El siguiente ejemplo de código crea <xref:System.Xml.XmlValidatingReader> que toma <xref:System.Xml.XmlTextReader>. El archivo de entrada, sample4.xml, se valida con el esquema XML sample4.xsd.  
  
```vb  
Dim tr As New XmlTextReader("sample4.xml")  
Dim vr As New XmlValidatingReader(tr)  
vr.ValidationType = ValidationType.Schema  
vr.Schemas.Add("datatypesTest", "sample4.xsd")  
AddHandler vr.ValidationEventHandler, AddressOf ValidationCallBack  
While vr.Read()  
   Console.WriteLine("NodeType: {0} NodeName: {1}", vr.NodeType, vr.Name)  
End While  
```  
  
```csharp  
XmlTextReader tr = new XmlTextReader("sample4.xml");  
XmlValidatingReader vr = new XmlValidatingReader(tr);  
vr.ValidationType = ValidationType.Schema;  
        vr.Schemas.Add("datatypesTest", "sample4.xsd");  
vr.ValidationEventHandler += new ValidationEventHandler(ValidationCallBack);  
while(vr.Read()) {  
    Console.WriteLine("NodeType: {0} NodeName: {1}", vr.NodeType, vr.Name);  
    }  
```  
  
 A continuación se describe el contenido del archivo de entrada, sample4.xml, que se va a validar.  
  
```xml  
<datatypes xmlns="datatypesTest">  
    <number>  
        <number_1>123</number_1>  
    </number>  
</datatypes>  
```  
  
 A continuación se describe el contenido del archivo de esquema XML, sample4.xsd, con el que se va a realizar la validación.  
  
```xml  
<xs:schema
    xmlns:xs="http://www.w3.org/2001/XMLSchema"
    xmlns:tns="datatypesTest"
    targetNamespace="datatypesTest"  
    elementFormDefault="qualified">  
  
<xs:element name = "datatypes">  
  <xs:complexType>  
    <xs:all>  
        <xs:element name="number">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="number_1" type="xs:decimal" maxOccurs="unbounded"/>  
                </xs:sequence>  
            </xs:complexType>  
        </xs:element>  
    </xs:all>  
  </xs:complexType>  
</xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.XmlParserContext>
- <xref:System.Xml.XmlValidatingReader.ValidationEventHandler?displayProperty=nameWithType>
- <xref:System.Xml.XmlValidatingReader.Schemas%2A?displayProperty=nameWithType>
- [Compilación de esquema XmlSchemaCollection](xmlschemacollection-schema-compilation.md)
