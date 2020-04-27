---
title: Procesamiento de datos XML con el modelo DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 56b6e9c7-ed82-4a65-a647-7be32c83bcc8
ms.openlocfilehash: 01ef4bef57b8a2e3e13f28a98adb21b111f3f4ed
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710458"
---
# <a name="process-xml-data-using-the-dom-model"></a><span data-ttu-id="5e17f-102">Procesamiento de datos XML con el modelo DOM</span><span class="sxs-lookup"><span data-stu-id="5e17f-102">Process XML Data Using the DOM Model</span></span>
<span data-ttu-id="5e17f-103">El Modelo de objetos de documento (DOM) trata los datos XML como un conjunto estándar de datos y se utiliza para procesar datos XML en memoria.</span><span class="sxs-lookup"><span data-stu-id="5e17f-103">The XML Document Object Model (DOM) treats XML data as a standard set of objects and is used to process XML data in memory.</span></span> <span data-ttu-id="5e17f-104">El espacio de nombres `System.Xml` proporciona una representación mediante programación de documentos XML, fragmentos, nodos o conjuntos de nodos.</span><span class="sxs-lookup"><span data-stu-id="5e17f-104">The `System.Xml` namespace provides a programmatic representation of XML documents, fragments, nodes, or node-sets.</span></span> <span data-ttu-id="5e17f-105">Se basa en la parte principal del nivel 1 del DOM y las recomendaciones de la parte principal del nivel 2 del DOM del W3C (World Wide Web Consortium).</span><span class="sxs-lookup"><span data-stu-id="5e17f-105">It is based on the World Wide Web Consortium (W3C) DOM Level 1 Core and the DOM Level 2 Core recommendations.</span></span>  
  
 <span data-ttu-id="5e17f-106">La clase <xref:System.Xml.XmlDocument> representa un documento XML.</span><span class="sxs-lookup"><span data-stu-id="5e17f-106">The <xref:System.Xml.XmlDocument> class represents an XML document.</span></span> <span data-ttu-id="5e17f-107">Incluye miembros para recuperar y crear el resto de los objetos XML.</span><span class="sxs-lookup"><span data-stu-id="5e17f-107">It includes members for retrieving and creating all other XML objects.</span></span> <span data-ttu-id="5e17f-108">Con <xref:System.Xml.XmlDocument>, y sus clases relacionadas, puede construir documentos XML, cargar datos, tener acceso a ellos, modificarlos y guardar cambios.</span><span class="sxs-lookup"><span data-stu-id="5e17f-108">Using the <xref:System.Xml.XmlDocument>, and its related classes, you can construct XML documents, load and access data, modify data, and save changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5e17f-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5e17f-109">In This Section</span></span>  
  
- [<span data-ttu-id="5e17f-110">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="5e17f-110">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)  
  
- [<span data-ttu-id="5e17f-111">Tipos de nodos XML</span><span class="sxs-lookup"><span data-stu-id="5e17f-111">Types of XML Nodes</span></span>](../../../../docs/standard/data/xml/types-of-xml-nodes.md)  
  
- [<span data-ttu-id="5e17f-112">Jerarquía de Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="5e17f-112">XML Document Object Model (DOM) Hierarchy</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom-hierarchy.md)  
  
- [<span data-ttu-id="5e17f-113">Asignación de la jerarquía de objetos a datos XML</span><span class="sxs-lookup"><span data-stu-id="5e17f-113">Mapping the Object Hierarchy to XML Data</span></span>](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md)  
  
- [<span data-ttu-id="5e17f-114">Creación de documentos XML</span><span class="sxs-lookup"><span data-stu-id="5e17f-114">XML Document Creation</span></span>](../../../../docs/standard/data/xml/xml-document-creation.md)  
  
- [<span data-ttu-id="5e17f-115">Lectura de un documento XML en DOM</span><span class="sxs-lookup"><span data-stu-id="5e17f-115">Reading an XML Document into the DOM</span></span>](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md)  
  
- [<span data-ttu-id="5e17f-116">Inserción de nodos en un documento XML</span><span class="sxs-lookup"><span data-stu-id="5e17f-116">Inserting Nodes into an XML Document</span></span>](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md)  
  
- [<span data-ttu-id="5e17f-117">Eliminación de nodos, contenido y valores de un documento XML</span><span class="sxs-lookup"><span data-stu-id="5e17f-117">Removing Nodes, Content, and Values from an XML Document</span></span>](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md)  
  
- [<span data-ttu-id="5e17f-118">Modificación de nodos, contenido y valores en un documento XML</span><span class="sxs-lookup"><span data-stu-id="5e17f-118">Modifying Nodes, Content, and Values in an XML Document</span></span>](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md)  
  
- [<span data-ttu-id="5e17f-119">Validación de un documento XML en DOM</span><span class="sxs-lookup"><span data-stu-id="5e17f-119">Validating an XML Document in the DOM</span></span>](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md)  
  
- [<span data-ttu-id="5e17f-120">Guardado y escritura de un documento</span><span class="sxs-lookup"><span data-stu-id="5e17f-120">Saving and Writing a Document</span></span>](../../../../docs/standard/data/xml/saving-and-writing-a-document.md)  
  
- [<span data-ttu-id="5e17f-121">Selección de nodos con la navegación XPath</span><span class="sxs-lookup"><span data-stu-id="5e17f-121">Select Nodes Using XPath Navigation</span></span>](../../../../docs/standard/data/xml/select-nodes-using-xpath-navigation.md)  
  
- [<span data-ttu-id="5e17f-122">Resolución de recursos externos</span><span class="sxs-lookup"><span data-stu-id="5e17f-122">Resolving External Resources</span></span>](../../../../docs/standard/data/xml/resolving-external-resources.md)  
  
- [<span data-ttu-id="5e17f-123">Comparación de objetos mediante XmlNameTable</span><span class="sxs-lookup"><span data-stu-id="5e17f-123">Object Comparison Using XmlNameTable</span></span>](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md)  
  
- [<span data-ttu-id="5e17f-124">Colecciones de nodos en NamedNodeMaps y NodeLists</span><span class="sxs-lookup"><span data-stu-id="5e17f-124">Node Collections in NamedNodeMaps and NodeLists</span></span>](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md)  
  
- [<span data-ttu-id="5e17f-125">Actualizaciones dinámicas en NodeLists y NamedNodeMaps</span><span class="sxs-lookup"><span data-stu-id="5e17f-125">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>](../../../../docs/standard/data/xml/dynamic-updates-to-nodelists-and-namednodemaps.md)  
  
- [<span data-ttu-id="5e17f-126">Compatibilidad con los espacios de nombres en DOM</span><span class="sxs-lookup"><span data-stu-id="5e17f-126">Namespace Support in the DOM</span></span>](../../../../docs/standard/data/xml/namespace-support-in-the-dom.md)  
  
- [<span data-ttu-id="5e17f-127">Control de eventos en un documento XML mediante XmlNodeChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="5e17f-127">Event Handling in an XML Document Using the XmlNodeChangedEventArgs</span></span>](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md)  
  
- [<span data-ttu-id="5e17f-128">Extensión de DOM</span><span class="sxs-lookup"><span data-stu-id="5e17f-128">Extending the DOM</span></span>](../../../../docs/standard/data/xml/extending-the-dom.md)  
  
## <a name="related-sections"></a><span data-ttu-id="5e17f-129">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="5e17f-129">Related Sections</span></span>  
 [<span data-ttu-id="5e17f-130">Procesamiento de datos XML con el modelo de datos XPath</span><span class="sxs-lookup"><span data-stu-id="5e17f-130">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 <span data-ttu-id="5e17f-131">Describe el procesamiento XML mediante la clase <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="5e17f-131">Discusses XML processing using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>
