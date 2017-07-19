---
title: "Validaci&#243;n de XDR con XmlSchemaCollection | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 00833027-1428-4586-83c1-42f5de3323d1
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Validaci&#243;n de XDR con XmlSchemaCollection
Si el esquema reducido de datos XML \(XDR\) que va a utilizar para la validación se almacena en **XmlSchemaCollection**, se asociará al identificador URI de espacio de nombres que se especificó al agregar el esquema a la colección.  **XmlValidatingReader** asigna el URI de espacio de nombres del documento XML al esquema que corresponde a ese URI en la colección.  
  
> [!IMPORTANT]
>  La clase <xref:System.Xml.Schema.XmlSchemaCollection> está obsoleta y ha sido reemplazada por la clase <xref:System.Xml.Schema.XmlSchemaSet>.  Para obtener más información sobre la clase <xref:System.Xml.Schema.XmlSchemaSet>, vea [XmlSchemaSet para compilación de esquemas](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).  
  
 Por ejemplo, si el elemento raíz del documento XML es `<bookstore xmlns="urn:newbooks-schema">`, cuando el esquema se agrega a la colección **XmlSchemaCollection** hace referencia al mismo espacio de nombres, como se indica a continuación:  
  
```  
xsc.Add("urn:newbooks-schema", "newbooks.xdr")  
```  
  
 En el ejemplo de código siguiente se crea un **XmlValidatingReader** que acepta un **XmlTextReader** y agrega un esquema XDR, HeadCount.xdr, a **XmlSchemaCollection**.  
  
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
  
         vr.Schemas.Add("xdrHeadCount", "HeadCount.xdr")  
         vr.ValidationType = ValidationType.XDR  
         AddHandler vr.ValidationEventHandler, AddressOf ValidationHandler  
  
         While vr.Read()  
            PrintTypeInfo(vr)  
            If vr.NodeType = XmlNodeType.Element Then  
               While vr.MoveToNextAttribute()  
                  PrintTypeInfo(vr)  
               End While  
            End If  
         End While  
         Console.WriteLine("Validation finished")  
      End Sub  
      ' Main  
  
      Public Shared Sub PrintTypeInfo(vr As XmlValidatingReader)  
         If Not (vr.SchemaType Is Nothing) Then  
            If TypeOf vr.SchemaType Is XmlSchemaDatatype Or TypeOf vr.SchemaType Is XmlSchemaSimpleType Then  
               Dim value As Object = vr.ReadTypedValue()  
               Console.WriteLine("{0}({1},{2}):{3}", vr.NodeType, vr.Name, value.GetType().Name, value)  
            End If  
         End If  
      End Sub  
      ' PrintTypeInfo  
  
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
  
         vr.Schemas.Add("xdrHeadCount", "HeadCount.xdr");  
         vr.ValidationType = ValidationType.XDR;  
         vr.ValidationEventHandler += new ValidationEventHandler (ValidationHandler);  
  
         while(vr.Read())  
         {  
            PrintTypeInfo(vr);  
            if(vr.NodeType == XmlNodeType.Element)  
            {  
               while(vr.MoveToNextAttribute())  
                  PrintTypeInfo(vr);  
            }  
         }  
         Console.WriteLine("Validation finished");  
      }  
  
      public static void PrintTypeInfo(XmlValidatingReader vr)  
      {  
         if(vr.SchemaType != null)  
         {  
            if(vr.SchemaType is XmlSchemaDatatype || vr.SchemaType is XmlSchemaSimpleType)  
            {  
               object value = vr.ReadTypedValue();  
               Console.WriteLine("{0}({1},{2}):{3}", vr.NodeType, vr.Name, value.GetType().Name, value);  
            }  
         }  
      }  
  
      public static void ValidationHandler(object sender, ValidationEventArgs args)  
      {  
         Console.WriteLine("***Validation error");  
         Console.WriteLine("\tSeverity:{0}", args.Severity);  
         Console.WriteLine("\tMessage:{0}", args.Message);  
      }  
   }  
}  
```  
  
 A continuación se describe el contenido del archivo de entrada, HeadCount.xml, que se va a validar.  
  
```  
<!--Load HeadCount.xdr in SchemaCollection for Validation-->  
<HeadCount xmlns='xdrHeadCount'>  
   <Name>Waldo Pepper</Name>  
   <Name>Red Pepper</Name>  
</HeadCount>  
```  
  
 A continuación se describe el contenido del archivo de esquema XDR, HeadCount.dtd, que se usará como referencia para la validación.  
  
```  
<Schema xmlns="urn:schemas-microsoft-com:xml-data" xmlns:dt="urn:schemas-microsoft-com:datatypes">  
   <ElementType name="Name" content="textOnly"/>  
   <AttributeType name="Bldg" default="2"/>  
   <ElementType name="HeadCount" content="eltOnly">  
      <element type="Name"/>  
      <attribute type="Bldg"/>  
   </ElementType>  
</Schema>  
```  
  
## Vea también  
 <xref:System.Xml.XmlValidatingReader.ValidationType%2A>   
 <xref:System.Xml.XmlValidatingReader.Settings%2A>   
 [Compilación de esquema XmlSchemaCollection](../../../../docs/standard/data/xml/xmlschemacollection-schema-compilation.md)