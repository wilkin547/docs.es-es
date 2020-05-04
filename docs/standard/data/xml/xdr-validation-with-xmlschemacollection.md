---
title: Validación de XDR con XmlSchemaCollection
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 00833027-1428-4586-83c1-42f5de3323d1
ms.openlocfilehash: c1383dbb5419eadbfb7c07f288ee46b1ca11cf5c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710003"
---
# <a name="xdr-validation-with-xmlschemacollection"></a><span data-ttu-id="8e684-102">Validación de XDR con XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="8e684-102">XDR Validation with XmlSchemaCollection</span></span>

<span data-ttu-id="8e684-103">Si el esquema reducido de datos XML (XDR) que va a utilizar para la validación se almacena en **XmlSchemaCollection**, se asociará al identificador URI de espacio de nombres que se especificó al agregar el esquema a la colección.</span><span class="sxs-lookup"><span data-stu-id="8e684-103">If the XML-Data Reduced (XDR) schema you are validating against is stored in the **XmlSchemaCollection**, it is associated with the namespace URI specified when the schema was added to the collection.</span></span> <span data-ttu-id="8e684-104">**XmlValidatingReader** asigna el URI de espacio de nombres del documento XML al esquema que corresponde a ese URI en la colección.</span><span class="sxs-lookup"><span data-stu-id="8e684-104">**XmlValidatingReader** maps the namespace URI in the XML document to the schema that corresponds to that URI in the collection.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e684-105">La clase <xref:System.Xml.Schema.XmlSchemaCollection> está obsoleta y ha sido reemplazada por la clase <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="8e684-105">The <xref:System.Xml.Schema.XmlSchemaCollection> class is now obsolete and has been replaced with the <xref:System.Xml.Schema.XmlSchemaSet> class.</span></span> <span data-ttu-id="8e684-106">Para más información sobre la clase <xref:System.Xml.Schema.XmlSchemaSet>, vea [XmlSchemaSet para compilación de esquemas](xmlschemaset-for-schema-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="8e684-106">For more information about the <xref:System.Xml.Schema.XmlSchemaSet> class see, [XmlSchemaSet for Schema Compilation](xmlschemaset-for-schema-compilation.md).</span></span>

<span data-ttu-id="8e684-107">Por ejemplo, si el elemento raíz del documento XML es `<bookstore xmlns="urn:newbooks-schema">`, cuando el esquema se agrega a la colección **XmlSchemaCollection** hace referencia al mismo espacio de nombres, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="8e684-107">For example, if the root element of the XML document is `<bookstore xmlns="urn:newbooks-schema">`, when the schema is added to the **XmlSchemaCollection** it references the same namespace, as follows:</span></span>

```vb
xsc.Add("urn:newbooks-schema", "newbooks.xdr")
```

```csharp
xsc.Add("urn:newbooks-schema", "newbooks.xdr");
```

<span data-ttu-id="8e684-108">En el ejemplo de código siguiente se crea una clase **XmlValidatingReader** que acepta una clase **XmlTextReader** y agrega un esquema XDR, HeadCount.xdr, a **XmlSchemaCollection**:</span><span class="sxs-lookup"><span data-stu-id="8e684-108">The following code example creates an **XmlValidatingReader** that takes an **XmlTextReader** and adds an XDR schema, HeadCount.xdr, to the **XmlSchemaCollection**:</span></span>

```vb
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

        Public Shared Sub PrintTypeInfo(vr As XmlValidatingReader)
            If vr.SchemaType IsNot Nothing Then
                If TypeOf vr.SchemaType Is XmlSchemaDatatype Or TypeOf vr.SchemaType Is XmlSchemaSimpleType Then
                    Dim value As Object = vr.ReadTypedValue()
                    Console.WriteLine($"{vr.NodeType}({vr.Name},{value.GetType().Name}):{value}")
                End If
            End If
        End Sub

        Public Shared Sub ValidationHandler(sender As Object, args As ValidationEventArgs)
            Console.WriteLine("***Validation error")
            Console.WriteLine($"Severity:{args.Severity}")
            Console.WriteLine($"Message:{args.Message}")
        End Sub
    End Class
End Namespace
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
            var tr = new XmlTextReader("HeadCount.xml");
            var vr = new XmlValidatingReader(tr);

            vr.Schemas.Add("xdrHeadCount", "HeadCount.xdr");
            vr.ValidationType = ValidationType.XDR;
            vr.ValidationEventHandler += new ValidationEventHandler (ValidationHandler);

            while(vr.Read())
            {
                PrintTypeInfo(vr);
                if (vr.NodeType == XmlNodeType.Element)
                {
                   while(vr.MoveToNextAttribute())
                       PrintTypeInfo(vr);
                }
            }
            Console.WriteLine("Validation finished");
        }

        public static void PrintTypeInfo(XmlValidatingReader vr)
        {
            if (vr.SchemaType != null)
            {
                if(vr.SchemaType is XmlSchemaDatatype || vr.SchemaType is XmlSchemaSimpleType)
                {
                    object value = vr.ReadTypedValue();
                    Console.WriteLine($"{vr.NodeType}({vr.Name},{value.GetType().Name}):{value}");
                }
            }
        }

        public static void ValidationHandler(object sender, ValidationEventArgs args)
        {
            Console.WriteLine("***Validation error");
            Console.WriteLine($"\tSeverity:{args.Severity}");
            Console.WriteLine($"\tMessage:{args.Message}");
        }
    }
}
```

<span data-ttu-id="8e684-109">A continuación se describe el contenido del archivo de entrada, *HeadCount.xml*, que se va a validar:</span><span class="sxs-lookup"><span data-stu-id="8e684-109">The following outlines the contents of the input file, *HeadCount.xml*, to be validated:</span></span>

```xml
<!--Load HeadCount.xdr in SchemaCollection for Validation-->
<HeadCount xmlns='xdrHeadCount'>
   <Name>Waldo Pepper</Name>
   <Name>Red Pepper</Name>
</HeadCount>
```

<span data-ttu-id="8e684-110">A continuación se describe el contenido del archivo de esquema XDR, *HeadCount.xdr*, sobre el que se va realizar la validación:</span><span class="sxs-lookup"><span data-stu-id="8e684-110">The following outlines the contents of the XDR schema file, *HeadCount.xdr*, to be validated against:</span></span>

```xml
<Schema xmlns="urn:schemas-microsoft-com:xml-data" xmlns:dt="urn:schemas-microsoft-com:datatypes">
   <ElementType name="Name" content="textOnly"/>
   <AttributeType name="Bldg" default="2"/>
   <ElementType name="HeadCount" content="eltOnly">
      <element type="Name"/>
      <attribute type="Bldg"/>
   </ElementType>
</Schema>
```

## <a name="see-also"></a><span data-ttu-id="8e684-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e684-111">See also</span></span>

- <xref:System.Xml.XmlValidatingReader.ValidationType%2A>
- [<span data-ttu-id="8e684-112">Compilación de esquema XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="8e684-112">XmlSchemaCollection Schema Compilation</span></span>](xmlschemacollection-schema-compilation.md)
