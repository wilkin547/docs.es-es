---
title: Lectura y escritura de esquemas XML
description: Lea y escriba esquemas de lenguaje de definición de esquema XML (XSD) en archivos u otros orígenes en .NET, con la API del modelo de objetos de esquema (SOM).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
ms.assetid: b5757c4a-ea59-467e-ac62-be2bfe24eb77
ms.openlocfilehash: ae951efafd68d0ddf4f74876edd4c12564d68dde
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830888"
---
# <a name="reading-and-writing-xml-schemas"></a><span data-ttu-id="bce2f-103">Lectura y escritura de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="bce2f-103">Reading and Writing XML Schemas</span></span>
<span data-ttu-id="bce2f-104">La API del Modelo de objetos de esquema (SOM) se puede utilizar para leer y escribir esquemas del lenguaje de definición de esquemas XML (XSD) desde archivos u otros orígenes y compilar esquemas XML en memoria, utilizando las clases del espacio de nombres <xref:System.Xml.Schema?displayProperty=nameWithType> que se asignan a las estructuras definidas en la recomendación de esquemas XML del W3C (World Wide Web Consortium).</span><span class="sxs-lookup"><span data-stu-id="bce2f-104">The Schema Object Model (SOM) API can be used to read and write XML Schema definition language (XSD) schemas from files or other sources and build XML schemas in-memory using the classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace that map to the structures defined in the World Wide Web Consortium (W3C) XML Schema Recommendation.</span></span>  
  
## <a name="reading-and-writing-xml-schemas"></a><span data-ttu-id="bce2f-105">Lectura y escritura de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="bce2f-105">Reading and Writing XML Schemas</span></span>  
 <span data-ttu-id="bce2f-106">La clase <xref:System.Xml.Schema.XmlSchema> incluye los métodos <xref:System.Xml.Schema.XmlSchema.Read%2A> y <xref:System.Xml.Schema.XmlSchema.Write%2A> para leer y escribir esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="bce2f-106">The <xref:System.Xml.Schema.XmlSchema> class provides the <xref:System.Xml.Schema.XmlSchema.Read%2A> and <xref:System.Xml.Schema.XmlSchema.Write%2A> methods to read and write XML schemas.</span></span> <span data-ttu-id="bce2f-107">El método <xref:System.Xml.Schema.XmlSchema.Read%2A> devuelve un objeto <xref:System.Xml.Schema.XmlSchema> que representa el esquema XML y toma un parámetro <xref:System.Xml.Schema.ValidationEventHandler> opcional para controlar los errores y advertencias de validación que se encuentran al leer un esquema XML.</span><span class="sxs-lookup"><span data-stu-id="bce2f-107">The <xref:System.Xml.Schema.XmlSchema.Read%2A> method returns an <xref:System.Xml.Schema.XmlSchema> object representing the XML schema and takes an optional <xref:System.Xml.Schema.ValidationEventHandler> as a parameter to handle schema validation warnings and errors encountered while reading an XML schema.</span></span>  
  
 <span data-ttu-id="bce2f-108">El método <xref:System.Xml.Schema.XmlSchema.Write%2A> escribe esquemas XML para los objetos <xref:System.IO.Stream>, <xref:System.IO.TextWriter> y <xref:System.Xml.XmlWriter> y puede tomar un objeto <xref:System.Xml.XmlNamespaceManager> opcional como parámetro.</span><span class="sxs-lookup"><span data-stu-id="bce2f-108">The <xref:System.Xml.Schema.XmlSchema.Write%2A> method writes XML schemas to <xref:System.IO.Stream>, <xref:System.IO.TextWriter> and <xref:System.Xml.XmlWriter> objects and can take an optional <xref:System.Xml.XmlNamespaceManager> object as a parameter.</span></span> <span data-ttu-id="bce2f-109">Se utiliza un <xref:System.Xml.XmlNamespaceManager> para controlar los espacios de nombres que se encuentran en un esquema XML.</span><span class="sxs-lookup"><span data-stu-id="bce2f-109">An <xref:System.Xml.XmlNamespaceManager> is used to handle namespaces encountered in an XML schema.</span></span> <span data-ttu-id="bce2f-110">Para más información sobre la clase <xref:System.Xml.XmlNamespaceManager>, vea [Administrar espacios de nombres en un documento XML](managing-namespaces-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="bce2f-110">For more information about the <xref:System.Xml.XmlNamespaceManager> class, see [Managing Namespaces in an XML Document](managing-namespaces-in-an-xml-document.md).</span></span>  
  
 <span data-ttu-id="bce2f-111">El siguiente código de ejemplo ilustra la lectura y escritura de esquemas XML desde un archivo y en él.</span><span class="sxs-lookup"><span data-stu-id="bce2f-111">The following code example illustrates reading and writing XML schemas from and to a file.</span></span> <span data-ttu-id="bce2f-112">El código de ejemplo toma el archivo `example.xsd`, lo lee en un objeto <xref:System.Xml.Schema.XmlSchema> utilizando el método `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> y, a continuación, escribe el archivo en la consola y en un archivo `new.xsd` nuevo.</span><span class="sxs-lookup"><span data-stu-id="bce2f-112">The code example takes the `example.xsd` file, reads it into an <xref:System.Xml.Schema.XmlSchema> object using the `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> method, and then writes the file to the console and a new `new.xsd` file.</span></span> <span data-ttu-id="bce2f-113">El código de ejemplo también proporciona un <xref:System.Xml.Schema.ValidationEventHandler> como parámetro al método `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> para controlar cualquier error o advertencia de validación de esquemas que se encuentre al leer el esquema XML.</span><span class="sxs-lookup"><span data-stu-id="bce2f-113">The code example also provides a <xref:System.Xml.Schema.ValidationEventHandler> as a parameter to the `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> method to handle any schema validation warnings or errors encountered while reading the XML schema.</span></span> <span data-ttu-id="bce2f-114">Si no se especifica el <xref:System.Xml.Schema.ValidationEventHandler> (`null`), no se notifica ningún error ni advertencia.</span><span class="sxs-lookup"><span data-stu-id="bce2f-114">If the <xref:System.Xml.Schema.ValidationEventHandler> is not specified (`null`), no warnings or errors are reported.</span></span>  
  
 [!code-cpp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaReadWriteExample/CPP/XmlSchemaReadWriteExample.cpp#1)]
 [!code-csharp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaReadWriteExample/CS/XmlSchemaReadWriteExample.cs#1)]
 [!code-vb[XmlSchemaReadWriteExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaReadWriteExample/VB/XmlSchemaReadWriteExample.vb#1)]  
  
 <span data-ttu-id="bce2f-115">En el ejemplo se toma como entrada `example.xsd`.</span><span class="sxs-lookup"><span data-stu-id="bce2f-115">The example takes the `example.xsd` as input.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bce2f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="bce2f-116">See also</span></span>

- [<span data-ttu-id="bce2f-117">Información general sobre el Modelo de objetos de esquema XML</span><span class="sxs-lookup"><span data-stu-id="bce2f-117">XML Schema Object Model Overview</span></span>](xml-schema-object-model-overview.md)
- [<span data-ttu-id="bce2f-118">Compilación de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="bce2f-118">Building XML Schemas</span></span>](building-xml-schemas.md)
- [<span data-ttu-id="bce2f-119">Recorrido de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="bce2f-119">Traversing XML Schemas</span></span>](traversing-xml-schemas.md)
- [<span data-ttu-id="bce2f-120">Edición de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="bce2f-120">Editing XML Schemas</span></span>](editing-xml-schemas.md)
- [<span data-ttu-id="bce2f-121">Inclusión o importación de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="bce2f-121">Including or Importing XML Schemas</span></span>](including-or-importing-xml-schemas.md)
- [<span data-ttu-id="bce2f-122">XmlSchemaSet para compilación de esquemas</span><span class="sxs-lookup"><span data-stu-id="bce2f-122">XmlSchemaSet for Schema Compilation</span></span>](xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="bce2f-123">Conjunto de información posterior a la compilación de esquemas</span><span class="sxs-lookup"><span data-stu-id="bce2f-123">Post-Schema Compilation Infoset</span></span>](post-schema-compilation-infoset.md)
- [<span data-ttu-id="bce2f-124">Administrar espacios de nombres en un documento XML</span><span class="sxs-lookup"><span data-stu-id="bce2f-124">Managing Namespaces in an XML Document</span></span>](managing-namespaces-in-an-xml-document.md)
