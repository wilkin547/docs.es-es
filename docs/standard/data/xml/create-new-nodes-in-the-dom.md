---
title: "Creación de nuevos nodos en el DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c2b9789-b61a-49f9-b33f-db01a945edf2
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 195c0f8184bbbd84826def87ce74daa49965cb93
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="create-new-nodes-in-the-dom"></a><span data-ttu-id="1021e-102">Creación de nuevos nodos en el DOM</span><span class="sxs-lookup"><span data-stu-id="1021e-102">Create New Nodes in the DOM</span></span>
<span data-ttu-id="1021e-103"><xref:System.Xml.XmlDocument> tiene un método de creación para todos los tipos de nodos.</span><span class="sxs-lookup"><span data-stu-id="1021e-103">The <xref:System.Xml.XmlDocument> has a create method for all of the node types.</span></span> <span data-ttu-id="1021e-104">Para crear el nodo, proporcione el método con un nombre cuando sea preciso, y el contenido y otros parámetros para aquellos nodos que tengan contenido (por ejemplo, los nodos de texto).</span><span class="sxs-lookup"><span data-stu-id="1021e-104">Supply the method with a name when required, and content or other parameters for those nodes that have content (for example, a text node), and the node is created.</span></span> <span data-ttu-id="1021e-105">Los siguientes métodos son los que necesitan que se proporcione un nombre y otros cuantos parámetros para crear un nodo apropiado.</span><span class="sxs-lookup"><span data-stu-id="1021e-105">The following methods are ones that need a name and a few other parameters filled to create an appropriate node.</span></span>  
  
-   <xref:System.Xml.XmlDocument.CreateCDataSection%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateComment%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateDocumentFragment%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateDocumentType%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateElement%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateNode%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateProcessingInstruction%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateSignificantWhitespace%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateTextNode%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateWhitespace%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateXmlDeclaration%2A>  
  
 <span data-ttu-id="1021e-106">Otros tipos de nodos tienen más requisitos aparte de que se proporcionen datos a los parámetros.</span><span class="sxs-lookup"><span data-stu-id="1021e-106">Other node types have more requirements than just providing data to parameters.</span></span>  
  
 <span data-ttu-id="1021e-107">Para obtener más información sobre atributos, vea [Crear nuevos atributos para elementos en DOM](../../../../docs/standard/data/xml/creating-new-attributes-for-elements-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="1021e-107">For information on attributes, see [Creating New Attributes for Elements in the DOM](../../../../docs/standard/data/xml/creating-new-attributes-for-elements-in-the-dom.md).</span></span> <span data-ttu-id="1021e-108">Para obtener información sobre la validación de nombres de atributos y elementos, vea [Comprobación de nombres de atributos y elementos XML al crear nuevos nodos](../../../../docs/standard/data/xml/xml-element-and-attribute-name-verification-when-creating-new-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="1021e-108">For information on element and attribute name validation, see [XML Element and Attribute Name Verification when Creating New Nodes](../../../../docs/standard/data/xml/xml-element-and-attribute-name-verification-when-creating-new-nodes.md).</span></span> <span data-ttu-id="1021e-109">Para crear referencias de entidad, vea [Creación de nuevas referencias de entidad](../../../../docs/standard/data/xml/creating-new-entity-references.md).</span><span class="sxs-lookup"><span data-stu-id="1021e-109">For creating entity references, see [Creating New Entity References](../../../../docs/standard/data/xml/creating-new-entity-references.md).</span></span> <span data-ttu-id="1021e-110">Para obtener información sobre cómo los espacios de nombres afectan a la expansión de referencias de entidad, vea [Efecto del espacio de nombres en la expansión de referencias de entidad de nuevos nodos que contienen elementos y atributos](../../../../docs/standard/data/xml/namespace-affect-on-entity-ref-expansion-for-new-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="1021e-110">For information on how namespaces affect the expansion of entity references, see [Namespace Affect on Entity Reference Expansion for New Nodes Containing Elements and Attributes](../../../../docs/standard/data/xml/namespace-affect-on-entity-ref-expansion-for-new-nodes.md).</span></span>  
  
 <span data-ttu-id="1021e-111">Una vez creados los nuevos nodos, hay disponibles varios métodos para insertarlos en el árbol.</span><span class="sxs-lookup"><span data-stu-id="1021e-111">Once new nodes are created, there are several methods available to insert them into the tree.</span></span> <span data-ttu-id="1021e-112">En la tabla se enumeran los métodos con una descripción de dónde aparece el nuevo nodo en el Modelo de objetos de documento (DOM).</span><span class="sxs-lookup"><span data-stu-id="1021e-112">The table lists the methods with a description of where the new node appears in the XML Document Object Model (DOM).</span></span>  
  
|<span data-ttu-id="1021e-113">Método</span><span class="sxs-lookup"><span data-stu-id="1021e-113">Method</span></span>|<span data-ttu-id="1021e-114">Colocación del nodo</span><span class="sxs-lookup"><span data-stu-id="1021e-114">Node placement</span></span>|  
|------------|--------------------|  
|<xref:System.Xml.XmlNode.InsertBefore%2A>|<span data-ttu-id="1021e-115">Insertado antes del nodo de referencia.</span><span class="sxs-lookup"><span data-stu-id="1021e-115">Inserted before the reference node.</span></span> <span data-ttu-id="1021e-116">Por ejemplo, para insertar el nuevo nodo en la posición 5:</span><span class="sxs-lookup"><span data-stu-id="1021e-116">For example, to insert the new node in position 5:</span></span><br /><br /> `Dim refChild As XmlNode = node.ChildNodes(4) 'The reference is zero-based.node.InsertBefore(newChild, refChild);`<br /><br /> `XmlNode refChild = node.ChildNodes[4]; //The reference is zero-based. node.InsertBefore(newChild, refChild);`<br /><br /> <span data-ttu-id="1021e-117">Para obtener más información, vea el método <xref:System.Xml.XmlNode.InsertBefore%2A>.</span><span class="sxs-lookup"><span data-stu-id="1021e-117">For more information, see the <xref:System.Xml.XmlNode.InsertBefore%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.InsertAfter%2A>|<span data-ttu-id="1021e-118">Insertado después del nodo de referencia.</span><span class="sxs-lookup"><span data-stu-id="1021e-118">Inserted after the reference node.</span></span> <span data-ttu-id="1021e-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1021e-119">For example:</span></span><br /><br /> `node.InsertAfter(newChild, refChild)`<br /><br /> `node.InsertAfter(newChild, refChild);`<br /><br /> <span data-ttu-id="1021e-120">Para obtener más información, vea el método <xref:System.Xml.XmlNode.InsertAfter%2A>.</span><span class="sxs-lookup"><span data-stu-id="1021e-120">For more information, see the <xref:System.Xml.XmlNode.InsertAfter%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.AppendChild%2A>|<span data-ttu-id="1021e-121">Agrega el nodo al final de la lista de nodos secundarios del nodo especificado.</span><span class="sxs-lookup"><span data-stu-id="1021e-121">Adds the node to the end of the list of child nodes for the given node.</span></span> <span data-ttu-id="1021e-122">Si el nodo se agrega como un <xref:System.Xml.XmlDocumentFragment>, todo el contenido del fragmento del documento se mueve a la lista secundaria de este nodo.</span><span class="sxs-lookup"><span data-stu-id="1021e-122">If the node being added is an <xref:System.Xml.XmlDocumentFragment>, the entire contents of the document fragment are moved into the child list of this node.</span></span> <span data-ttu-id="1021e-123">Para obtener más información, vea el método <xref:System.Xml.XmlNode.AppendChild%2A>.</span><span class="sxs-lookup"><span data-stu-id="1021e-123">For more information, see the <xref:System.Xml.XmlNode.AppendChild%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.PrependChild%2A>|<span data-ttu-id="1021e-124">Agrega el nodo al principio de la lista de nodos secundarios del nodo especificado.</span><span class="sxs-lookup"><span data-stu-id="1021e-124">Adds the node to the beginning of the list of child nodes of the given node.</span></span> <span data-ttu-id="1021e-125">Si el nodo se agrega como un <xref:System.Xml.XmlDocumentFragment>, todo el contenido del fragmento del documento se mueve a la lista secundaria de este nodo.</span><span class="sxs-lookup"><span data-stu-id="1021e-125">If the node being added is an <xref:System.Xml.XmlDocumentFragment>, the entire contents of the document fragment are moved into the child list of this node.</span></span> <span data-ttu-id="1021e-126">Para obtener más información, vea el método <xref:System.Xml.XmlNode.PrependChild%2A>.</span><span class="sxs-lookup"><span data-stu-id="1021e-126">For more information, see the <xref:System.Xml.XmlNode.PrependChild%2A> method.</span></span>|  
|<xref:System.Xml.XmlAttributeCollection.Append%2A>|<span data-ttu-id="1021e-127">Agrega un nodo <xref:System.Xml.XmlAttribute> al final de la colección de atributos asociada a un elemento.</span><span class="sxs-lookup"><span data-stu-id="1021e-127">Appends an <xref:System.Xml.XmlAttribute> node to the end of the attribute collection associated with an element.</span></span> <span data-ttu-id="1021e-128">Para obtener más información, vea el método <xref:System.Xml.XmlAttributeCollection.Append%2A>.</span><span class="sxs-lookup"><span data-stu-id="1021e-128">For more information, see the <xref:System.Xml.XmlAttributeCollection.Append%2A> method.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1021e-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="1021e-129">See Also</span></span>  
 [<span data-ttu-id="1021e-130">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="1021e-130">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
