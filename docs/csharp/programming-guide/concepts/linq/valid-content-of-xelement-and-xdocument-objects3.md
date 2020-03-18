---
title: Contenido válido de objetos XElement y XDocument
ms.date: 07/20/2015
ms.assetid: 0d253586-2b97-459f-b1a7-f30f38f3ed9f
ms.openlocfilehash: 1ad5b18e3bbc2143a56f9c8e7b34354761b4e42f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "69590938"
---
# <a name="valid-content-of-xelement-and-xdocument-objects"></a><span data-ttu-id="d8f50-102">Contenido válido de objetos XElement y XDocument</span><span class="sxs-lookup"><span data-stu-id="d8f50-102">Valid Content of XElement and XDocument Objects</span></span>
<span data-ttu-id="d8f50-103">En este tema se describen los argumentos válidos que se pueden pasar a los constructores y los métodos que se usan para agregar contenido a elementos y documentos.</span><span class="sxs-lookup"><span data-stu-id="d8f50-103">This topic describes the valid arguments that can be passed to constructors and methods that you use to add content to elements and documents.</span></span>  
  
## <a name="valid-content"></a><span data-ttu-id="d8f50-104">Contenido válido</span><span class="sxs-lookup"><span data-stu-id="d8f50-104">Valid Content</span></span>  
 <span data-ttu-id="d8f50-105">Las consultas a menudo evalúan a <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement> o a <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d8f50-105">Queries often evaluate to <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> or <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="d8f50-106">Se pueden pasar colecciones de objetos <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute> al constructor <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="d8f50-106">You can pass collections of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects to the <xref:System.Xml.Linq.XElement> constructor.</span></span> <span data-ttu-id="d8f50-107">Por lo tanto, resulta conveniente pasar los resultados de una consulta como contenido a los métodos y constructores que use para rellenar árboles XML.</span><span class="sxs-lookup"><span data-stu-id="d8f50-107">Therefore, it is convenient to pass the results of a query as content into methods and constructors that you use to populate XML trees.</span></span>  
  
 <span data-ttu-id="d8f50-108">Al agregar contenido simple, se pueden pasar varios tipos a este método.</span><span class="sxs-lookup"><span data-stu-id="d8f50-108">When adding simple content, various types can be passed to this method.</span></span> <span data-ttu-id="d8f50-109">Entre los tipos válidos se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d8f50-109">Valid types include the following:</span></span>  
  
- <xref:System.String>  
  
- <xref:System.Double>  
  
- <xref:System.Single>  
  
- <xref:System.Decimal>  
  
- <xref:System.Boolean>  
  
- <xref:System.DateTime>  
  
- <xref:System.TimeSpan>  
  
- <xref:System.DateTimeOffset>  
  
- <span data-ttu-id="d8f50-110">Cualquier tipo que implemente `Object.ToString`.</span><span class="sxs-lookup"><span data-stu-id="d8f50-110">Any type that implements `Object.ToString`.</span></span>  
  
- <span data-ttu-id="d8f50-111">Cualquier tipo que implemente <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="d8f50-111">Any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span>  
  
 <span data-ttu-id="d8f50-112">Al agregar contenido complejo, se pueden pasar varios tipos a este método:</span><span class="sxs-lookup"><span data-stu-id="d8f50-112">When adding complex content, various types can be passed to this method:</span></span>  
  
- <xref:System.Xml.Linq.XObject>  
  
- <xref:System.Xml.Linq.XNode>  
  
- <xref:System.Xml.Linq.XAttribute>  
  
- <span data-ttu-id="d8f50-113">Cualquier tipo que implemente <xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="d8f50-113">Any type that implements <xref:System.Collections.Generic.IEnumerable%601></span></span>  
  
 <span data-ttu-id="d8f50-114">Si un objeto implementa <xref:System.Collections.Generic.IEnumerable%601>, se enumera la colección del objeto y se agregan todos los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="d8f50-114">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="d8f50-115">Si la colección contiene objetos <xref:System.Xml.Linq.XNode> o <xref:System.Xml.Linq.XAttribute>, cada elemento de la colección se agrega por separado.</span><span class="sxs-lookup"><span data-stu-id="d8f50-115">If the collection contains <xref:System.Xml.Linq.XNode> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="d8f50-116">Si la colección contiene texto (u objetos convertidos a texto), el texto de la colección se concatena y se agrega como un nodo de texto.</span><span class="sxs-lookup"><span data-stu-id="d8f50-116">If the collection contains text (or objects that are converted to text), the text in the collection is concatenated and added as a single text node.</span></span>  
  
 <span data-ttu-id="d8f50-117">Si el contenido es `null`, no se agrega nada.</span><span class="sxs-lookup"><span data-stu-id="d8f50-117">If content is `null`, nothing is added.</span></span> <span data-ttu-id="d8f50-118">Al pasar una colección, se permite que los elementos de la colección sean `null`.</span><span class="sxs-lookup"><span data-stu-id="d8f50-118">When passing a collection items in the collection can be `null`.</span></span> <span data-ttu-id="d8f50-119">Un elemento `null` de la colección no tiene ningún efecto en el árbol.</span><span class="sxs-lookup"><span data-stu-id="d8f50-119">A `null` item in the collection has no effect on the tree.</span></span>  
  
 <span data-ttu-id="d8f50-120">Un atributo agregado debe tener un nombre único en el elemento contenedor.</span><span class="sxs-lookup"><span data-stu-id="d8f50-120">An added attribute must have a unique name within its containing element.</span></span>  
  
 <span data-ttu-id="d8f50-121">Cuando se asocian objetos <xref:System.Xml.Linq.XNode> o <xref:System.Xml.Linq.XAttribute>, si el contenido nuevo no tiene un elemento primario, los objetos simplemente se adjuntan al árbol XML.</span><span class="sxs-lookup"><span data-stu-id="d8f50-121">When adding <xref:System.Xml.Linq.XNode> or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, then the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="d8f50-122">Si el contenido nuevo ya tiene un elemento primario y forma parte de otro árbol XML, el nuevo contenido se clonará y dicho clon se adjuntará al árbol XML.</span><span class="sxs-lookup"><span data-stu-id="d8f50-122">If the new content already is parented and is part of another XML tree, then the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span>  
  
## <a name="valid-content-for-documents"></a><span data-ttu-id="d8f50-123">Contenido válido para documentos</span><span class="sxs-lookup"><span data-stu-id="d8f50-123">Valid Content for Documents</span></span>  
 <span data-ttu-id="d8f50-124">Los atributos y el contenido simple no se pueden agregar a un documento.</span><span class="sxs-lookup"><span data-stu-id="d8f50-124">Attributes and simple content cannot be added to a document.</span></span>  
  
 <span data-ttu-id="d8f50-125">No existen muchos escenarios que requieran la creación de un objeto <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="d8f50-125">There are not many scenarios that require you to create an <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="d8f50-126">En su lugar, normalmente puede crear los árboles XML con un nodo raíz <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="d8f50-126">Instead, you can usually create your XML trees with an <xref:System.Xml.Linq.XElement> root node.</span></span> <span data-ttu-id="d8f50-127">A menos que exista un requisito específico de crear un documento (por ejemplo, porque deba crear instrucciones y comentarios de procesamiento en el nivel superior, o bien deba admitir tipos de documento), a menudo resulta más conveniente usar <xref:System.Xml.Linq.XElement> como nodo raíz.</span><span class="sxs-lookup"><span data-stu-id="d8f50-127">Unless you have a specific requirement to create a document (for example, because you have to create processing instructions and comments at the top level, or you have to support document types), it is often more convenient to use <xref:System.Xml.Linq.XElement> as your root node.</span></span>  
  
 <span data-ttu-id="d8f50-128">El contenido válido para un documento incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d8f50-128">Valid content for a document includes the following:</span></span>  
  
- <span data-ttu-id="d8f50-129">Cero o un objeto <xref:System.Xml.Linq.XDocumentType>.</span><span class="sxs-lookup"><span data-stu-id="d8f50-129">Zero or one <xref:System.Xml.Linq.XDocumentType> objects.</span></span> <span data-ttu-id="d8f50-130">Los tipos de documento deben ir antes del elemento.</span><span class="sxs-lookup"><span data-stu-id="d8f50-130">The document types must come before the element.</span></span>  
  
- <span data-ttu-id="d8f50-131">Cero o un elemento.</span><span class="sxs-lookup"><span data-stu-id="d8f50-131">Zero or one element.</span></span>  
  
- <span data-ttu-id="d8f50-132">Cero o más comentarios.</span><span class="sxs-lookup"><span data-stu-id="d8f50-132">Zero or more comments.</span></span>  
  
- <span data-ttu-id="d8f50-133">Cero o más instrucciones de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="d8f50-133">Zero or more processing instructions.</span></span>  
  
- <span data-ttu-id="d8f50-134">Cero o más nodos de texto que contengan solo espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="d8f50-134">Zero or more text nodes that contain only white space.</span></span>  
  
## <a name="constructors-and-functions-that-allow-adding-content"></a><span data-ttu-id="d8f50-135">Constructores y funciones que permiten agregar contenido</span><span class="sxs-lookup"><span data-stu-id="d8f50-135">Constructors and Functions that Allow Adding Content</span></span>  
 <span data-ttu-id="d8f50-136">Los métodos siguientes permiten agregar contenido secundario a un objeto <xref:System.Xml.Linq.XElement> o a un objeto <xref:System.Xml.Linq.XDocument>:</span><span class="sxs-lookup"><span data-stu-id="d8f50-136">The following methods allow you to add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="d8f50-137">Método</span><span class="sxs-lookup"><span data-stu-id="d8f50-137">Method</span></span>|<span data-ttu-id="d8f50-138">Description</span><span class="sxs-lookup"><span data-stu-id="d8f50-138">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.%23ctor%2A>|<span data-ttu-id="d8f50-139">Construye un objeto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="d8f50-139">Constructs an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<xref:System.Xml.Linq.XDocument.%23ctor%2A>|<span data-ttu-id="d8f50-140">Construye un objeto <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="d8f50-140">Constructs a <xref:System.Xml.Linq.XDocument>.</span></span>|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|<span data-ttu-id="d8f50-141">Agrega al final del contenido secundario del objeto <xref:System.Xml.Linq.XElement> o del objeto <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="d8f50-141">Adds to the end of the child content of the <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>.</span></span>|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|<span data-ttu-id="d8f50-142">Añade un contenido detrás de <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="d8f50-142">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|<span data-ttu-id="d8f50-143">Agrega contenido antes de <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="d8f50-143">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|<span data-ttu-id="d8f50-144">Agrega un contenido al comienzo de los contenidos secundarios del <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="d8f50-144">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A>|<span data-ttu-id="d8f50-145">Reemplaza todo el contenido (atributos y nodos secundarios) de un objeto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="d8f50-145">Replaces all content (child nodes and attributes) of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A>|<span data-ttu-id="d8f50-146">Reemplaza los atributos de un objeto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="d8f50-146">Replaces the attributes of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A>|<span data-ttu-id="d8f50-147">Reemplaza los nodos secundarios por contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="d8f50-147">Replaces the children nodes with new content.</span></span>|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A>|<span data-ttu-id="d8f50-148">Reemplaza un nodo por contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="d8f50-148">Replaces a node with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8f50-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8f50-149">See also</span></span>

- [<span data-ttu-id="d8f50-150">Crear árboles XML (C#)</span><span class="sxs-lookup"><span data-stu-id="d8f50-150">Creating XML Trees (C#)</span></span>](./linq-to-xml-overview.md)
