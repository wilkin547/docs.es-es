---
title: "Información general sobre el Modelo de objetos de esquema XML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 896a1e12-5655-42c6-8cdd-89c12862b34b
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6a06de3f8fb6351d340e1c8f1bfe8f4105967e25
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xml-schema-object-model-overview"></a><span data-ttu-id="3323a-102">Información general sobre el Modelo de objetos de esquema XML</span><span class="sxs-lookup"><span data-stu-id="3323a-102">XML Schema Object Model Overview</span></span>
<span data-ttu-id="3323a-103">El Modelo de objetos de esquema (SOM) de Microsoft .NET Framework es una API enriquecida que le permite crear, editar y validar esquemas mediante programación.</span><span class="sxs-lookup"><span data-stu-id="3323a-103">The Schema Object Model (SOM) in the Microsoft .NET Framework is a rich API that allows you to create, edit, and validate schemas programmatically.</span></span> <span data-ttu-id="3323a-104">El SOM funciona en los documentos de esquemas XML de forma similar a cómo funciona el Modelo de objetos de documento (DOM) en los documentos XML.</span><span class="sxs-lookup"><span data-stu-id="3323a-104">The SOM operates on XML schema documents similarly to the way the Document Object Model (DOM) operates on XML documents.</span></span> <span data-ttu-id="3323a-105">Los documentos de esquemas XML son archivos XML válidos que, una vez cargados en el SOM, transmiten significado sobre la estructura y la validez de otros documentos XML que cumplen el esquema.</span><span class="sxs-lookup"><span data-stu-id="3323a-105">XML schema documents are valid XML files that, once loaded into the SOM, convey meaning about the structure and validity of other XML documents which conform to the schema.</span></span>  
  
 <span data-ttu-id="3323a-106">Un esquema es un documento XML que define una clase de documentos XML especificando la estructura o el modelo de los documentos XML de un esquema en particular.</span><span class="sxs-lookup"><span data-stu-id="3323a-106">A schema is an XML document that defines a class of XML documents by specifying the structure or model of XML documents for a particular schema.</span></span> <span data-ttu-id="3323a-107">Un esquema identifica las restricciones del contenido de los documentos XML y describe el vocabulario (reglas o gramática) que deben seguir los documentos conforme a XML para que se consideren válidos en ese esquema en particular.</span><span class="sxs-lookup"><span data-stu-id="3323a-107">A schema identifies the constraints on the content of the XML documents, and describes the vocabulary (rules or grammar) that compliant XML documents must follow in order to be considered schema-valid with that particular schema.</span></span> <span data-ttu-id="3323a-108">La validación de un documento XML es el proceso que garantiza que el documento sigue la gramática que especifica el esquema.</span><span class="sxs-lookup"><span data-stu-id="3323a-108">Validation of an XML document is the process that ensures that the document conforms to the grammar specified by the schema.</span></span>  
  
 <span data-ttu-id="3323a-109">A continuación se indican las formas en las que la API del SOM de .NET Framework le permite crear, editar y validar esquemas.</span><span class="sxs-lookup"><span data-stu-id="3323a-109">The following are ways the SOM API in the .NET Framework enables you to create, edit, and validate schemas.</span></span>  
  
-   <span data-ttu-id="3323a-110">Cargue esquemas validos desde archivos y guárdelos en ellos.</span><span class="sxs-lookup"><span data-stu-id="3323a-110">Load and save valid schemas to and from files.</span></span>  
  
-   <span data-ttu-id="3323a-111">Cree esquemas en memoria utilizando clases fuertemente tipadas.</span><span class="sxs-lookup"><span data-stu-id="3323a-111">Create in-memory schemas using strongly typed classes.</span></span>  
  
-   <span data-ttu-id="3323a-112">Interactúe con la clase <xref:System.Xml.Schema.XmlSchemaSet> para guardar en caché, compilar y recuperar esquemas.</span><span class="sxs-lookup"><span data-stu-id="3323a-112">Interact with the <xref:System.Xml.Schema.XmlSchemaSet> class to cache, compile, and retrieve schemas.</span></span>  
  
-   <span data-ttu-id="3323a-113">Interactúe con el método <xref:System.Xml.XmlReader.Create%2A> de la clase <xref:System.Xml.XmlReader> para validar documentos de instancias XML con esquemas.</span><span class="sxs-lookup"><span data-stu-id="3323a-113">Interact with the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class to validate XML instance documents against schemas.</span></span>  
  
-   <span data-ttu-id="3323a-114">Compile editores para crear y mantener esquemas.</span><span class="sxs-lookup"><span data-stu-id="3323a-114">Build editors for creating and maintaining schemas.</span></span>  
  
-   <span data-ttu-id="3323a-115">Edite dinámicamente un esquema que se pueda compilar y guardar para utilizarlo en la validación de documentos de instancias XML.</span><span class="sxs-lookup"><span data-stu-id="3323a-115">Dynamically edit a schema that can be complied and saved for use in the validation of XML instance documents.</span></span>  
  
## <a name="the-schema-object-model"></a><span data-ttu-id="3323a-116">El Modelo de objetos de esquema</span><span class="sxs-lookup"><span data-stu-id="3323a-116">The Schema Object Model</span></span>  
 <span data-ttu-id="3323a-117">El SOM consta de un amplio conjunto de clases en el espacio de nombres <xref:System.Xml.Schema?displayProperty=nameWithType> que se corresponde a los elementos de un esquema XML.</span><span class="sxs-lookup"><span data-stu-id="3323a-117">The SOM consists of an extensive set of classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace corresponding to the elements in an XML schema.</span></span> <span data-ttu-id="3323a-118">Por ejemplo, el elemento `<xsd:schema>...</xsd:schema>` se asigna a la clase <xref:System.Xml.Schema.XmlSchema?displayProperty=nameWithType> y toda la información que puede contener un elemento `<xsd:schema/>` se puede representar utilizando la clase <xref:System.Xml.Schema.XmlSchema>.</span><span class="sxs-lookup"><span data-stu-id="3323a-118">For example, the `<xsd:schema>...</xsd:schema>` element maps to the <xref:System.Xml.Schema.XmlSchema?displayProperty=nameWithType> class, and all the information that can be contained within an `<xsd:schema/>` element can be represented using the <xref:System.Xml.Schema.XmlSchema> class.</span></span> <span data-ttu-id="3323a-119">Igualmente, los elementos `<xsd:element>...</xsd:element>` y `<xsd:attribute>...</xsd:attribute>` se asignan a las clases <xref:System.Xml.Schema.XmlSchemaElement?displayProperty=nameWithType> y <xref:System.Xml.Schema.XmlSchemaAttribute?displayProperty=nameWithType>, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="3323a-119">Similarly, the `<xsd:element>...</xsd:element>` and `<xsd:attribute>...</xsd:attribute>` elements map to the <xref:System.Xml.Schema.XmlSchemaElement?displayProperty=nameWithType> and <xref:System.Xml.Schema.XmlSchemaAttribute?displayProperty=nameWithType> classes respectively.</span></span> <span data-ttu-id="3323a-120">Esta asignación continúa para todos los elementos de un esquema XML que creen un Modelo de objetos de esquema XML en el espacio de nombres <xref:System.Xml.Schema>, tal y como se ilustra en el siguiente diagrama.</span><span class="sxs-lookup"><span data-stu-id="3323a-120">This mapping continues for all the elements of an XML schema creating an XML schema object model in the <xref:System.Xml.Schema> namespace illustrated in the diagram that follows.</span></span>  
  
 <span data-ttu-id="3323a-121">![Modelo de objetos System.Xml.Schema](../../../../docs/standard/data/xml/media/xmlschemaobjmodeloverview.gif "XMLSchemaObjModelOverview")</span><span class="sxs-lookup"><span data-stu-id="3323a-121">![System.Xml.Schema Object Model](../../../../docs/standard/data/xml/media/xmlschemaobjmodeloverview.gif "XMLSchemaObjModelOverview")</span></span>  
  
 <span data-ttu-id="3323a-122">Para obtener más información sobre cada clase del espacio de nombres <xref:System.Xml.Schema>, vea la documentación de referencia del espacio de nombres <xref:System.Xml.Schema> en la biblioteca de clases de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3323a-122">For more information about each class in the <xref:System.Xml.Schema> namespace, see the <xref:System.Xml.Schema> namespace reference documentation in the .NET Framework class library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3323a-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="3323a-123">See Also</span></span>  
 [<span data-ttu-id="3323a-124">Leer y escribir esquemas XML</span><span class="sxs-lookup"><span data-stu-id="3323a-124">Reading and Writing XML Schemas</span></span>](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)  
 [<span data-ttu-id="3323a-125">Compilar esquemas XML</span><span class="sxs-lookup"><span data-stu-id="3323a-125">Building XML Schemas</span></span>](../../../../docs/standard/data/xml/building-xml-schemas.md)  
 [<span data-ttu-id="3323a-126">Cómo atravesar esquemas XML</span><span class="sxs-lookup"><span data-stu-id="3323a-126">Traversing XML Schemas</span></span>](../../../../docs/standard/data/xml/traversing-xml-schemas.md)  
 [<span data-ttu-id="3323a-127">Edición de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="3323a-127">Editing XML Schemas</span></span>](../../../../docs/standard/data/xml/editing-xml-schemas.md)  
 [<span data-ttu-id="3323a-128">Inclusión o importación de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="3323a-128">Including or Importing XML Schemas</span></span>](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)  
 [<span data-ttu-id="3323a-129">XmlSchemaSet para compilación de esquemas</span><span class="sxs-lookup"><span data-stu-id="3323a-129">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 [<span data-ttu-id="3323a-130">Conjunto de información de compilación del esquema posterior</span><span class="sxs-lookup"><span data-stu-id="3323a-130">Post-Schema Compilation Infoset</span></span>](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
