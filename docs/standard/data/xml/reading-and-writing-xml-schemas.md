---
title: Lectura y escritura de esquemas XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: b5757c4a-ea59-467e-ac62-be2bfe24eb77
ms.openlocfilehash: 889c5f85a2ea3fc08dadefda5509de0fcfab76ec
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710419"
---
# <a name="reading-and-writing-xml-schemas"></a><span data-ttu-id="19240-102">Lectura y escritura de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="19240-102">Reading and Writing XML Schemas</span></span>
<span data-ttu-id="19240-103">La API del Modelo de objetos de esquema (SOM) se puede utilizar para leer y escribir esquemas del lenguaje de definición de esquemas XML (XSD) desde archivos u otros orígenes y compilar esquemas XML en memoria, utilizando las clases del espacio de nombres <xref:System.Xml.Schema?displayProperty=nameWithType> que se asignan a las estructuras definidas en la recomendación de esquemas XML del W3C (World Wide Web Consortium).</span><span class="sxs-lookup"><span data-stu-id="19240-103">The Schema Object Model (SOM) API can be used to read and write XML Schema definition language (XSD) schemas from files or other sources and build XML schemas in-memory using the classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace that map to the structures defined in the World Wide Web Consortium (W3C) XML Schema Recommendation.</span></span>  
  
## <a name="reading-and-writing-xml-schemas"></a><span data-ttu-id="19240-104">Lectura y escritura de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="19240-104">Reading and Writing XML Schemas</span></span>  
 <span data-ttu-id="19240-105">La clase <xref:System.Xml.Schema.XmlSchema> incluye los métodos <xref:System.Xml.Schema.XmlSchema.Read%2A> y <xref:System.Xml.Schema.XmlSchema.Write%2A> para leer y escribir esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="19240-105">The <xref:System.Xml.Schema.XmlSchema> class provides the <xref:System.Xml.Schema.XmlSchema.Read%2A> and <xref:System.Xml.Schema.XmlSchema.Write%2A> methods to read and write XML schemas.</span></span> <span data-ttu-id="19240-106">El método <xref:System.Xml.Schema.XmlSchema.Read%2A> devuelve un objeto <xref:System.Xml.Schema.XmlSchema> que representa el esquema XML y toma un parámetro <xref:System.Xml.Schema.ValidationEventHandler> opcional para controlar los errores y advertencias de validación que se encuentran al leer un esquema XML.</span><span class="sxs-lookup"><span data-stu-id="19240-106">The <xref:System.Xml.Schema.XmlSchema.Read%2A> method returns an <xref:System.Xml.Schema.XmlSchema> object representing the XML schema and takes an optional <xref:System.Xml.Schema.ValidationEventHandler> as a parameter to handle schema validation warnings and errors encountered while reading an XML schema.</span></span>  
  
 <span data-ttu-id="19240-107">El método <xref:System.Xml.Schema.XmlSchema.Write%2A> escribe esquemas XML para los objetos <xref:System.IO.Stream>, <xref:System.IO.TextWriter> y <xref:System.Xml.XmlWriter> y puede tomar un objeto <xref:System.Xml.XmlNamespaceManager> opcional como parámetro.</span><span class="sxs-lookup"><span data-stu-id="19240-107">The <xref:System.Xml.Schema.XmlSchema.Write%2A> method writes XML schemas to <xref:System.IO.Stream>, <xref:System.IO.TextWriter> and <xref:System.Xml.XmlWriter> objects and can take an optional <xref:System.Xml.XmlNamespaceManager> object as a parameter.</span></span> <span data-ttu-id="19240-108">Se utiliza un <xref:System.Xml.XmlNamespaceManager> para controlar los espacios de nombres que se encuentran en un esquema XML.</span><span class="sxs-lookup"><span data-stu-id="19240-108">An <xref:System.Xml.XmlNamespaceManager> is used to handle namespaces encountered in an XML schema.</span></span> <span data-ttu-id="19240-109">Para más información sobre la clase <xref:System.Xml.XmlNamespaceManager>, vea [Administrar espacios de nombres en un documento XML](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="19240-109">For more information about the <xref:System.Xml.XmlNamespaceManager> class, see [Managing Namespaces in an XML Document](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md).</span></span>  
  
 <span data-ttu-id="19240-110">El siguiente código de ejemplo ilustra la lectura y escritura de esquemas XML desde un archivo y en él.</span><span class="sxs-lookup"><span data-stu-id="19240-110">The following code example illustrates reading and writing XML schemas from and to a file.</span></span> <span data-ttu-id="19240-111">El código de ejemplo toma el archivo `example.xsd`, lo lee en un objeto <xref:System.Xml.Schema.XmlSchema> utilizando el método `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> y, a continuación, escribe el archivo en la consola y en un archivo `new.xsd` nuevo.</span><span class="sxs-lookup"><span data-stu-id="19240-111">The code example takes the `example.xsd` file, reads it into an <xref:System.Xml.Schema.XmlSchema> object using the `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> method, and then writes the file to the console and a new `new.xsd` file.</span></span> <span data-ttu-id="19240-112">El código de ejemplo también proporciona un <xref:System.Xml.Schema.ValidationEventHandler> como parámetro al método `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> para controlar cualquier error o advertencia de validación de esquemas que se encuentre al leer el esquema XML.</span><span class="sxs-lookup"><span data-stu-id="19240-112">The code example also provides a <xref:System.Xml.Schema.ValidationEventHandler> as a parameter to the `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> method to handle any schema validation warnings or errors encountered while reading the XML schema.</span></span> <span data-ttu-id="19240-113">Si no se especifica el <xref:System.Xml.Schema.ValidationEventHandler> (`null`), no se notifica ningún error ni advertencia.</span><span class="sxs-lookup"><span data-stu-id="19240-113">If the <xref:System.Xml.Schema.ValidationEventHandler> is not specified (`null`), no warnings or errors are reported.</span></span>  
  
 [!code-cpp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaReadWriteExample/CPP/XmlSchemaReadWriteExample.cpp#1)]
 [!code-csharp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaReadWriteExample/CS/XmlSchemaReadWriteExample.cs#1)]
 [!code-vb[XmlSchemaReadWriteExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaReadWriteExample/VB/XmlSchemaReadWriteExample.vb#1)]  
  
 <span data-ttu-id="19240-114">En el ejemplo se toma como entrada `example.xsd`.</span><span class="sxs-lookup"><span data-stu-id="19240-114">The example takes the `example.xsd` as input.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<xs:schema id="play" targetNamespace="http://tempuri.org/play.xsd" elementFormDefault="qualified" xmlns="http://tempuri.org/play.xsd" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name='myShoeSize'>  
        <xs:complexType>  
            <xs:simpleContent>  
                <xs:extension base='xs:decimal'>  
                    <xs:attribute name='sizing' type='xs:string' />  
                </xs:extension>  
            </xs:simpleContent>  
        </xs:complexType>  
    </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="19240-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="19240-115">See also</span></span>

- [<span data-ttu-id="19240-116">Información general sobre el Modelo de objetos de esquema XML</span><span class="sxs-lookup"><span data-stu-id="19240-116">XML Schema Object Model Overview</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)
- [<span data-ttu-id="19240-117">Compilación de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="19240-117">Building XML Schemas</span></span>](../../../../docs/standard/data/xml/building-xml-schemas.md)
- [<span data-ttu-id="19240-118">Recorrido de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="19240-118">Traversing XML Schemas</span></span>](../../../../docs/standard/data/xml/traversing-xml-schemas.md)
- [<span data-ttu-id="19240-119">Edición de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="19240-119">Editing XML Schemas</span></span>](../../../../docs/standard/data/xml/editing-xml-schemas.md)
- [<span data-ttu-id="19240-120">Inclusión o importación de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="19240-120">Including or Importing XML Schemas</span></span>](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)
- [<span data-ttu-id="19240-121">XmlSchemaSet para compilación de esquemas</span><span class="sxs-lookup"><span data-stu-id="19240-121">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="19240-122">Conjunto de información posterior a la compilación de esquemas</span><span class="sxs-lookup"><span data-stu-id="19240-122">Post-Schema Compilation Infoset</span></span>](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
- [<span data-ttu-id="19240-123">Administrar espacios de nombres en un documento XML</span><span class="sxs-lookup"><span data-stu-id="19240-123">Managing Namespaces in an XML Document</span></span>](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md)
