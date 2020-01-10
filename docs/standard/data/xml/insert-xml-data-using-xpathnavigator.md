---
title: Inserción de datos XML con XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 2ed8c28b-b88d-4be7-9c87-92df01f0821f
ms.openlocfilehash: 68c003467d837fe79d5e275968e47fa5dc3490cc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710731"
---
# <a name="insert-xml-data-using-xpathnavigator"></a><span data-ttu-id="00735-102">Inserción de datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="00735-102">Insert XML Data using XPathNavigator</span></span>
<span data-ttu-id="00735-103">La clase <xref:System.Xml.XPath.XPathNavigator> incluye un conjunto de métodos que se utilizan para insertar nodos de atributos, secundarios y relacionados en un documento XML.</span><span class="sxs-lookup"><span data-stu-id="00735-103">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to insert sibling, child, and attribute nodes in an XML document.</span></span> <span data-ttu-id="00735-104">Para utilizar estos métodos, el objeto <xref:System.Xml.XPath.XPathNavigator> debe ser editable, es decir, su propiedad <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> debe ser `true`.</span><span class="sxs-lookup"><span data-stu-id="00735-104">In order to use these methods, the <xref:System.Xml.XPath.XPathNavigator> object must be editable, that is, its <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property must be `true`.</span></span>  
  
 <span data-ttu-id="00735-105">El método <xref:System.Xml.XPath.XPathNavigator> de la clase <xref:System.Xml.XmlDocument.CreateNavigator%2A> crea los objetos <xref:System.Xml.XmlDocument> que pueden editar un documento XML.</span><span class="sxs-lookup"><span data-stu-id="00735-105"><xref:System.Xml.XPath.XPathNavigator> objects that can edit an XML document are created by the <xref:System.Xml.XmlDocument.CreateNavigator%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="00735-106">Los objetos <xref:System.Xml.XPath.XPathNavigator> que crea la clase <xref:System.Xml.XPath.XPathDocument> son de solo lectura y cualquier intento de utilizar los métodos de edición de un objeto <xref:System.Xml.XPath.XPathNavigator> creado por un objeto <xref:System.Xml.XPath.XPathDocument> producirá una excepción <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="00735-106"><xref:System.Xml.XPath.XPathNavigator> objects created by the <xref:System.Xml.XPath.XPathDocument> class are read-only and any attempt to use the editing methods of an <xref:System.Xml.XPath.XPathNavigator> object created by an <xref:System.Xml.XPath.XPathDocument> object results in a <xref:System.NotSupportedException>.</span></span>  
  
 <span data-ttu-id="00735-107">Para más información sobre cómo crear objetos <xref:System.Xml.XPath.XPathNavigator> editables, vea [Lectura de datos XML con XPathDocument y XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).</span><span class="sxs-lookup"><span data-stu-id="00735-107">For more information about creating editable <xref:System.Xml.XPath.XPathNavigator> objects, see [Reading XML Data using XPathDocument and XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).</span></span>  
  
## <a name="inserting-nodes"></a><span data-ttu-id="00735-108">Inserción de nodos</span><span class="sxs-lookup"><span data-stu-id="00735-108">Inserting Nodes</span></span>  
 <span data-ttu-id="00735-109">La clase <xref:System.Xml.XPath.XPathNavigator> incluye métodos que se utilizan para insertar nodos de atributos, secundarios y relacionados en un documento XML.</span><span class="sxs-lookup"><span data-stu-id="00735-109">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to insert sibling, child, and attribute nodes in an XML document.</span></span> <span data-ttu-id="00735-110">Estos métodos permiten insertar nodos y atributos en diferentes ubicaciones en relación con la posición actual de un objeto <xref:System.Xml.XPath.XPathNavigator> y se describen en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="00735-110">These methods allow you to insert nodes and attributes in different locations in relation to the current position of an <xref:System.Xml.XPath.XPathNavigator> object and are described in the following sections.</span></span>  
  
### <a name="inserting-sibling-nodes"></a><span data-ttu-id="00735-111">Inserción de nodos relacionados</span><span class="sxs-lookup"><span data-stu-id="00735-111">Inserting Sibling Nodes</span></span>  
 <span data-ttu-id="00735-112">La clase <xref:System.Xml.XPath.XPathNavigator> incluye los siguientes métodos para insertar nodos relacionados.</span><span class="sxs-lookup"><span data-stu-id="00735-112">The <xref:System.Xml.XPath.XPathNavigator> class provides the following methods to insert sibling nodes.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A>  
  
 <span data-ttu-id="00735-113">Estos métodos insertan nodos relacionados antes y después del nodo en el que está situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="00735-113">These methods insert sibling nodes before and after the node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="00735-114">Los métodos <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> y <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> están sobrecargados y aceptan un objeto `string`, <xref:System.Xml.XmlReader>, o un objeto <xref:System.Xml.XPath.XPathNavigator> que contiene el nodo relacionado para agregarlos como parámetros.</span><span class="sxs-lookup"><span data-stu-id="00735-114">The <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> and <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> methods are overloaded and accept a `string`, <xref:System.Xml.XmlReader> object, or <xref:System.Xml.XPath.XPathNavigator> object containing the sibling node to add as parameters.</span></span> <span data-ttu-id="00735-115">Ambos métodos también devuelven un objeto <xref:System.Xml.XmlWriter> que se utiliza para insertar nodos relacionados.</span><span class="sxs-lookup"><span data-stu-id="00735-115">Both methods also return an <xref:System.Xml.XmlWriter> object used to insert sibling nodes.</span></span>  
  
 <span data-ttu-id="00735-116">Los métodos <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> y <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> insertan un solo nodo relacionado antes y después del nodo en el que está situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>, utilizando como parámetros el prefijo de espacio de nombres, el nombre local, el identificador URI de espacio de nombres y el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="00735-116">The <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> and <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> methods insert a single sibling node before and after the node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on using the namespace prefix, local name, namespace URI, and value specified as parameters.</span></span>  
  
 <span data-ttu-id="00735-117">En el siguiente ejemplo, se inserta un elemento `pages` nuevo antes del elemento secundario `price` del primer elemento `book` en el archivo `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="00735-117">In the following example a new `pages` element is inserted before the `price` child element of the first `book` element in the `contosoBooks.xml` file.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#19](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#19)]
 [!code-csharp[XPathNavigatorMethods#19](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#19)]
 [!code-vb[XPathNavigatorMethods#19](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#19)]  
  
 <span data-ttu-id="00735-118">En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="00735-118">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="00735-119">Para obtener más información sobre los métodos <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> y <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A>, vea la documentación de referencia de la clase <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="00735-119">For more information about the <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> and <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> methods, see the <xref:System.Xml.XPath.XPathNavigator> class reference documentation.</span></span>  
  
### <a name="inserting-child-nodes"></a><span data-ttu-id="00735-120">Inserción de nodos secundarios</span><span class="sxs-lookup"><span data-stu-id="00735-120">Inserting Child Nodes</span></span>  
 <span data-ttu-id="00735-121">La clase <xref:System.Xml.XPath.XPathNavigator> incluye los siguientes métodos para insertar nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="00735-121">The <xref:System.Xml.XPath.XPathNavigator> class provides the following methods to insert child nodes.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A>  
  
 <span data-ttu-id="00735-122">Estos métodos agregan nodos secundarios al final y al principio de la lista de nodos secundarios del nodo en el que se encuentra situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="00735-122">These methods append and prepend child nodes to the end of and the beginning of the list of child nodes of the node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="00735-123">Al igual que los métodos que se indican en la sección "Inserción de nodos relacionados", los métodos <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> y <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> aceptan un objeto `string`, <xref:System.Xml.XmlReader> o un objeto <xref:System.Xml.XPath.XPathNavigator> que contiene el nodo secundario, para agregarlos como parámetros.</span><span class="sxs-lookup"><span data-stu-id="00735-123">Like the methods in the "Inserting Sibling Nodes" section, the <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> and <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> methods accept a `string`, <xref:System.Xml.XmlReader> object, or <xref:System.Xml.XPath.XPathNavigator> object containing the child node to add as parameters.</span></span> <span data-ttu-id="00735-124">Ambos métodos también devuelven un objeto <xref:System.Xml.XmlWriter> que se utiliza para insertar nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="00735-124">Both methods also return an <xref:System.Xml.XmlWriter> object used to insert child nodes.</span></span>  
  
 <span data-ttu-id="00735-125">Además, al igual que los métodos que se indican en la sección "Inserción de nodos relacionados", los métodos <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> y <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> insertan un solo nodo secundario al final y al principio de la lista de nodos secundarios del nodo en el que se encuentra situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>, utilizando como parámetros el prefijo de espacio de nombres, el nombre local, el identificador URI de espacio de nombres y el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="00735-125">Also like the methods in the "Inserting Sibling Nodes" section, the <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> and <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> methods insert a single child node to the end of and the beginning of the list of child nodes of the node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on using the namespace prefix, local name, namespace URI, and value specified as parameters.</span></span>  
  
 <span data-ttu-id="00735-126">En el siguiente ejemplo se agrega un nuevo elemento secundario `pages` a la lista de elementos secundarios del primer elemento `book` del archivo `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="00735-126">In the following example, a new `pages` child element is appended to the list of child elements of the first `book` element in the `contosoBooks.xml` file.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#2](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#2)]
 [!code-csharp[XPathNavigatorMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#2)]
 [!code-vb[XPathNavigatorMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#2)]  
  
 <span data-ttu-id="00735-127">En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="00735-127">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="00735-128">Para obtener más información sobre los métodos <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> y <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A>, vea la documentación de referencia de la clase <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="00735-128">For more information about the <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> and <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> methods, see the <xref:System.Xml.XPath.XPathNavigator> class reference documentation.</span></span>  
  
### <a name="inserting-attribute-nodes"></a><span data-ttu-id="00735-129">Inserción de nodos de atributos</span><span class="sxs-lookup"><span data-stu-id="00735-129">Inserting Attribute Nodes</span></span>  
 <span data-ttu-id="00735-130">La clase <xref:System.Xml.XPath.XPathNavigator> incluye los siguientes métodos para insertar nodos de atributos.</span><span class="sxs-lookup"><span data-stu-id="00735-130">The <xref:System.Xml.XPath.XPathNavigator> class provides the following methods to insert attribute nodes.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>  
  
 <span data-ttu-id="00735-131">Estos métodos insertan nodos de atributos en el nodo de elementos en el que está situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="00735-131">These methods insert attribute nodes on the element node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span> <span data-ttu-id="00735-132">El método <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> crea un nodo de atributos en el nodo de elementos en el que está situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>, utilizando como parámetros el prefijo de espacio de nombres, el nombre local, el identificador URI de espacio de nombres y el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="00735-132">The <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> method creates an attribute node on the element node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on using the namespace prefix, local name, namespace URI, and value specified as parameters.</span></span> <span data-ttu-id="00735-133">El método <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> devuelve un objeto <xref:System.Xml.XmlWriter> que se utiliza para insertar nodos de atributos.</span><span class="sxs-lookup"><span data-stu-id="00735-133">The <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> method returns an <xref:System.Xml.XmlWriter> object used to insert attribute nodes.</span></span>  
  
 <span data-ttu-id="00735-134">En el siguiente ejemplo se crean nuevos atributos `discount` y `currency` en el elemento secundario `price` del primer elemento `book` del archivo `contosoBooks.xml` utilizando el objeto <xref:System.Xml.XmlWriter> devuelto desde el método <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>.</span><span class="sxs-lookup"><span data-stu-id="00735-134">In the following example, new `discount` and `currency` attributes are created on the `price` child element of the first `book` element in the `contosoBooks.xml` file using the <xref:System.Xml.XmlWriter> object returned from the <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> method.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#8](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#8)]
 [!code-csharp[XPathNavigatorMethods#8](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#8)]
 [!code-vb[XPathNavigatorMethods#8](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#8)]  
  
 <span data-ttu-id="00735-135">En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="00735-135">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="00735-136">Para obtener más información sobre los métodos <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> y <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>, vea la documentación de referencia de la clase <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="00735-136">For more information about the <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> and <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> methods, see the <xref:System.Xml.XPath.XPathNavigator> class reference documentation.</span></span>  
  
## <a name="copying-nodes"></a><span data-ttu-id="00735-137">Copia de nodos</span><span class="sxs-lookup"><span data-stu-id="00735-137">Copying Nodes</span></span>  
 <span data-ttu-id="00735-138">En determinados casos, puede que desee llenar un documento XML con el contenido de otro documento XML.</span><span class="sxs-lookup"><span data-stu-id="00735-138">In certain cases you may want to populate an XML document with the contents from another XML document.</span></span> <span data-ttu-id="00735-139">Tanto la clase <xref:System.Xml.XPath.XPathNavigator> como la clase <xref:System.Xml.XmlWriter> pueden copiar nodos en un objeto <xref:System.Xml.XmlDocument> desde un objeto <xref:System.Xml.XmlReader> existente o desde un objeto <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="00735-139">Both the <xref:System.Xml.XPath.XPathNavigator> class and the <xref:System.Xml.XmlWriter> class can copy nodes to an <xref:System.Xml.XmlDocument> object from an existing <xref:System.Xml.XmlReader> object or <xref:System.Xml.XPath.XPathNavigator> object.</span></span>  
  
 <span data-ttu-id="00735-140">Los métodos <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> y <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> tienen sobrecargas que pueden aceptar como parámetro un objeto <xref:System.Xml.XPath.XPathNavigator> o un objeto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="00735-140">The <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> and <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class all have overloads that can accept an <xref:System.Xml.XPath.XPathNavigator> object or an <xref:System.Xml.XmlReader> object as a parameter.</span></span>  
  
 <span data-ttu-id="00735-141">El método <xref:System.Xml.XmlWriter.WriteNode%2A> de la clase <xref:System.Xml.XmlWriter> tiene sobrecargas que pueden aceptar un objeto <xref:System.Xml.XmlNode>, <xref:System.Xml.XmlReader> o <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="00735-141">The <xref:System.Xml.XmlWriter.WriteNode%2A> method of the <xref:System.Xml.XmlWriter> class has overloads that can accept an <xref:System.Xml.XmlNode>, <xref:System.Xml.XmlReader>, or <xref:System.Xml.XPath.XPathNavigator> object.</span></span>  
  
 <span data-ttu-id="00735-142">En el siguiente ejemplo se copian todos los elementos `book` de un documento a otro.</span><span class="sxs-lookup"><span data-stu-id="00735-142">The following example copies all the `book` elements from one document to another.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", String.Empty)  
  
Dim newBooks As XPathDocument = New XPathDocument("newBooks.xml")  
Dim newBooksNavigator As XPathNavigator = newBooks.CreateNavigator()  
  
Dim nav As XPathNavigator  
For Each nav in newBooksNavigator.SelectDescendants("book", "", false)  
    navigator.AppendChild(nav)  
Next  
  
document.Save("newBooks.xml");  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", String.Empty);  
  
XPathDocument newBooks = new XPathDocument("newBooks.xml");  
XPathNavigator newBooksNavigator = newBooks.CreateNavigator();  
  
foreach (XPathNavigator nav in newBooksNavigator.SelectDescendants("book", "", false))  
{  
    navigator.AppendChild(nav);  
}  
  
document.Save("newBooks.xml");  
```  
  
## <a name="inserting-values"></a><span data-ttu-id="00735-143">Inserción de valores</span><span class="sxs-lookup"><span data-stu-id="00735-143">Inserting Values</span></span>  
 <span data-ttu-id="00735-144">La clase <xref:System.Xml.XPath.XPathNavigator> incluye los métodos <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> y <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> para insertar valores de un nodo en un objeto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="00735-144">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> and <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> methods to insert values for a node into an <xref:System.Xml.XmlDocument> object.</span></span>  
  
### <a name="inserting-untyped-values"></a><span data-ttu-id="00735-145">Inserción de valores sin información de tipos</span><span class="sxs-lookup"><span data-stu-id="00735-145">Inserting Untyped Values</span></span>  
 <span data-ttu-id="00735-146">El método <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> simplemente inserta el valor `string` sin información de tipos, que se pasa como parámetro, como valor del nodo en el que se encuentra situado actualmente el objeto <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="00735-146">The <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method simply inserts the untyped `string` value passed as a parameter as the value of the node the <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span> <span data-ttu-id="00735-147">Este valor se inserta sin ningún tipo o sin comprobar si el nuevo valor es válido de acuerdo con el tipo del nodo si hay disponible información de esquema.</span><span class="sxs-lookup"><span data-stu-id="00735-147">The value is inserted without any type or without verifying that the new value is valid according to the type of the node if schema information is available.</span></span>  
  
 <span data-ttu-id="00735-148">En el siguiente ejemplo, el método <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> se utiliza para actualizar todos los elementos `price` del archivo `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="00735-148">In the following example, the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method is used to update all `price` elements in the `contosoBooks.xml` file.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#47](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#47)]
 [!code-csharp[XPathNavigatorMethods#47](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#47)]
 [!code-vb[XPathNavigatorMethods#47](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#47)]  
  
 <span data-ttu-id="00735-149">En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="00735-149">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="inserting-typed-values"></a><span data-ttu-id="00735-150">Inserción de valores con información de tipos</span><span class="sxs-lookup"><span data-stu-id="00735-150">Inserting Typed Values</span></span>  
 <span data-ttu-id="00735-151">Cuando un nodo es de un tipo simple de esquema XML del W3C, el valor nuevo que ha insertado el método <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> se comprueba en las facetas del tipo simple antes de establecer el valor.</span><span class="sxs-lookup"><span data-stu-id="00735-151">When the type of a node is a W3C XML Schema simple type, the new value inserted by the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method is checked against the facets of the simple type before the value is set.</span></span> <span data-ttu-id="00735-152">Si el valor nuevo no es válido de acuerdo con el tipo del nodo (por ejemplo, si se establece un valor de `-1` en un elemento cuyo tipo es `xs:positiveInteger`), se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="00735-152">If the new value is not valid according to the type of the node (for example, setting a value of `-1` on an element whose type is `xs:positiveInteger`), it results in an exception.</span></span>  
  
 <span data-ttu-id="00735-153">En el siguiente ejemplo se intenta cambiar el valor del elemento `price` del primer elemento `book` en el archivo `contosoBooks.xml` por un valor <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="00735-153">The following example attempts to change the value of the `price` element of the first `book` element in the `contosoBooks.xml` file to a <xref:System.DateTime> value.</span></span> <span data-ttu-id="00735-154">Dado que el tipo de esquema XML del elemento `price` está definido como `xs:decimal` en los archivos `contosoBooks.xsd`, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="00735-154">Because the XML Schema type of the `price` element is defined as `xs:decimal` in the `contosoBooks.xsd` files, this results in an exception.</span></span>  
  
```vb  
Dim settings As XmlReaderSettings = New XmlReaderSettings()  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
settings.ValidationType = ValidationType.Schema  
  
Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
Dim document As XmlDocument = New XmlDocument()  
document.Load(reader)  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.SetTypedValue(DateTime.Now)  
```  
  
```csharp  
XmlReaderSettings settings = new XmlReaderSettings();  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
settings.ValidationType = ValidationType.Schema;  
  
XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
XmlDocument document = new XmlDocument();  
document.Load(reader);  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.SetTypedValue(DateTime.Now);  
```  
  
 <span data-ttu-id="00735-155">En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="00735-155">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="00735-156">En el ejemplo también se toma como entrada el archivo `contosoBooks.xsd`.</span><span class="sxs-lookup"><span data-stu-id="00735-156">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
## <a name="the-innerxml-and-outerxml-properties"></a><span data-ttu-id="00735-157">Propiedades InnerXml y OuterXml</span><span class="sxs-lookup"><span data-stu-id="00735-157">The InnerXml and OuterXml Properties</span></span>  
 <span data-ttu-id="00735-158">Las propiedades <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> y <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> cambian el marcado XML de los nodos en los que se encuentra situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="00735-158">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties of the <xref:System.Xml.XPath.XPathNavigator> class change the XML markup of the nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="00735-159">La propiedad <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> cambia el marcado XML de los nodos secundarios en los que se encuentra situado actualmente el objeto <xref:System.Xml.XPath.XPathNavigator> por el contenido analizado de la `string` XML especificada.</span><span class="sxs-lookup"><span data-stu-id="00735-159">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on with the parsed contents of the given XML `string`.</span></span> <span data-ttu-id="00735-160">Igualmente, la propiedad <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> cambia el marcado XML de los nodos secundarios en los que se encuentra situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>, así como el propio nodo actual.</span><span class="sxs-lookup"><span data-stu-id="00735-160">Similarly, the <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on as well as the current node itself.</span></span>  
  
 <span data-ttu-id="00735-161">Además de los métodos que se describen en este tema, se pueden utilizar las propiedades <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> y <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> para insertar nodos y valores en un documento XML.</span><span class="sxs-lookup"><span data-stu-id="00735-161">In addition to the methods described in this topic, the <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties can be used to insert nodes and values in an XML document.</span></span> <span data-ttu-id="00735-162">Para más información sobre el uso de las propiedades <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> y <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> para insertar nodos y valores, vea el tema [Modificación de datos XML con XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="00735-162">For more information about using the <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties to insert nodes and values, see the [Modify XML Data using XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md) topic.</span></span>  
  
## <a name="namespace-and-xmllang-conflicts"></a><span data-ttu-id="00735-163">Conflictos de xml:lang y espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="00735-163">Namespace and xml:lang Conflicts</span></span>  
 <span data-ttu-id="00735-164">Se pueden producir determinados conflictos relacionados con el ámbito del espacio de nombres y las declaraciones `xml:lang` al insertar datos XML utilizando los métodos <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> y <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> que toman objetos <xref:System.Xml.XmlReader> como parámetros.</span><span class="sxs-lookup"><span data-stu-id="00735-164">Certain conflicts related to the scope of namespace and `xml:lang` declarations can occur when inserting XML data using the <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> and <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class that take <xref:System.Xml.XmlReader> objects as parameters.</span></span>  
  
 <span data-ttu-id="00735-165">A continuación, se indican los posibles conflictos de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="00735-165">The following are the possible namespace conflicts.</span></span>  
  
- <span data-ttu-id="00735-166">Si hay un espacio de nombres en el ámbito dentro del contexto del objeto <xref:System.Xml.XmlReader>, en donde el prefijo de la asignación del identificador URI del espacio de nombres no está en el contexto del objeto <xref:System.Xml.XPath.XPathNavigator>, se agrega una nueva declaración de espacio de nombres al nodo que se acaba de insertar.</span><span class="sxs-lookup"><span data-stu-id="00735-166">If there is a namespace in-scope within the <xref:System.Xml.XmlReader> object's context, where the prefix to namespace URI mapping is not in the <xref:System.Xml.XPath.XPathNavigator> object's context, a new namespace declaration is added to the newly inserted node.</span></span>  
  
- <span data-ttu-id="00735-167">Si el mismo identificador URI de espacio de nombres está en el ámbito dentro del contexto del objeto <xref:System.Xml.XmlReader> y del objeto <xref:System.Xml.XPath.XPathNavigator>, pero tiene otro prefijo asignado en ambos contextos, se agrega una nueva declaración de espacio de nombres al nodo que se acaba de insertar, con el prefijo y el identificador URI de espacio de nombres tomados del objeto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="00735-167">If the same namespace URI is in-scope within both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context, but has a different prefix mapped to it in both contexts, a new namespace declaration is added to the newly inserted node, with the prefix and namespace URI taken from the <xref:System.Xml.XmlReader> object.</span></span>  
  
- <span data-ttu-id="00735-168">Si el mismo prefijo de espacio de nombres está en el ámbito dentro del contexto del objeto <xref:System.Xml.XmlReader> y del objeto <xref:System.Xml.XPath.XPathNavigator>, pero tiene otro identificador URI de espacio de nombres asignado en ambos contextos, se agrega una nueva declaración de espacio de nombres al nodo que se acaba de insertar, que vuelve a declarar ese prefijo con el identificador URI de espacio de nombres tomado del objeto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="00735-168">If the same namespace prefix is in-scope within both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context, but has a different namespace URI mapped to it in both contexts, a new namespace declaration is added to the newly inserted node which re-declares that prefix with the namespace URI taken from <xref:System.Xml.XmlReader> object.</span></span>  
  
- <span data-ttu-id="00735-169">Si el prefijo y el identificador URI de espacio de nombres en el contexto del objeto <xref:System.Xml.XmlReader> y del objeto <xref:System.Xml.XPath.XPathNavigator> son los mismos, no se agrega ninguna declaración de espacio de nombres nueva al nodo que se acaba de insertar.</span><span class="sxs-lookup"><span data-stu-id="00735-169">If the prefix as well as the namespace URI in both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context is the same, no new namespace declaration is added to the newly inserted node.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="00735-170">La descripción anterior también se aplica a declaraciones de espacios de nombres con la `string` vacía como prefijo (por ejemplo, la declaración de espacio de nombres predeterminada).</span><span class="sxs-lookup"><span data-stu-id="00735-170">The description above also applies to namespace declarations with the empty `string` as a prefix (for example, the default namespace declaration).</span></span>  
  
 <span data-ttu-id="00735-171">A continuación, se indican los posibles conflictos de `xml:lang`.</span><span class="sxs-lookup"><span data-stu-id="00735-171">The following are the possible `xml:lang` conflicts.</span></span>  
  
- <span data-ttu-id="00735-172">Si hay un atributo `xml:lang` en el ámbito dentro del contexto del objeto <xref:System.Xml.XmlReader>, pero no en el contexto del objeto <xref:System.Xml.XPath.XPathNavigator>, se agrega al nodo que se acaba de insertar un atributo `xml:lang` cuyo valor se toma del objeto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="00735-172">If there is an `xml:lang` attribute in-scope within the <xref:System.Xml.XmlReader> object's context but not in the <xref:System.Xml.XPath.XPathNavigator> object's context, an `xml:lang` attribute whose value is taken from the <xref:System.Xml.XmlReader> object is added to the newly inserted node.</span></span>  
  
- <span data-ttu-id="00735-173">Si hay un atributo `xml:lang` en el ámbito dentro del contexto del objeto <xref:System.Xml.XmlReader> y del objeto <xref:System.Xml.XPath.XPathNavigator>, pero cada uno con un valor diferente, se agrega al nodo que se acaba de insertar un atributo `xml:lang` cuyo valor se toma del objeto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="00735-173">If there is an `xml:lang` attribute in-scope within both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context, but each has a different value, an `xml:lang` attribute whose value is taken from the <xref:System.Xml.XmlReader> object is added to the newly inserted node.</span></span>  
  
- <span data-ttu-id="00735-174">Si hay un atributo en el ámbito `xml:lang` dentro del contexto del objeto <xref:System.Xml.XmlReader> y del objeto<xref:System.Xml.XPath.XPathNavigator> y cada uno tiene el mismo valor, no se agrega al nodo que se acaba de insertar ningún atributo `xml:lang` nuevo.</span><span class="sxs-lookup"><span data-stu-id="00735-174">If there is an `xml:lang` attribute in-scope within both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context, but each with the same value, no new `xml:lang` attribute is added on the newly inserted node.</span></span>  
  
- <span data-ttu-id="00735-175">Si hay un atributo `xml:lang` en el ámbito dentro del contexto del objeto <xref:System.Xml.XPath.XPathNavigator>, pero no existe ninguno en el contexto del objeto <xref:System.Xml.XmlReader>, no se agrega al nodo que se acaba de insertar ningún atributo `xml:lang`.</span><span class="sxs-lookup"><span data-stu-id="00735-175">If there is an `xml:lang` attribute in-scope within the <xref:System.Xml.XPath.XPathNavigator> object's context, but none existing in the <xref:System.Xml.XmlReader> object's context, no `xml:lang` attribute is added to the newly inserted node.</span></span>  
  
## <a name="inserting-nodes-with-xmlwriter"></a><span data-ttu-id="00735-176">Inserción de nodos con XmlWriter</span><span class="sxs-lookup"><span data-stu-id="00735-176">Inserting Nodes with XmlWriter</span></span>  
 <span data-ttu-id="00735-177">Los métodos que se utilizan para insertar nodos de atributos, secundarios y relacionados que se describen en la sección "Inserción de nodos y valores" están sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="00735-177">The methods used to insert sibling, child and attribute nodes described in the "Inserting Nodes and Values" section are overloaded.</span></span> <span data-ttu-id="00735-178">Los métodos <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> y <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> devuelven un objeto <xref:System.Xml.XmlWriter> que se utiliza para insertar nodos.</span><span class="sxs-lookup"><span data-stu-id="00735-178">The <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> and <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class return an <xref:System.Xml.XmlWriter> object used to insert nodes.</span></span>  
  
### <a name="unsupported-xmlwriter-methods"></a><span data-ttu-id="00735-179">Métodos XmlWriter incompatibles</span><span class="sxs-lookup"><span data-stu-id="00735-179">Unsupported XmlWriter Methods</span></span>  
 <span data-ttu-id="00735-180">No todos los métodos que se utilizan para escribir información en un documento XML con la clase <xref:System.Xml.XmlWriter> son compatibles con la clase <xref:System.Xml.XPath.XPathNavigator>. Esto se debe a la diferencia entre el modelo de datos XPath y el Modelo de objetos de documento (DOM).</span><span class="sxs-lookup"><span data-stu-id="00735-180">Not all of the methods used for writing information to an XML document using the <xref:System.Xml.XmlWriter> class are supported by the <xref:System.Xml.XPath.XPathNavigator> class due to difference between the XPath data model and the Document Object Model (DOM).</span></span>  
  
 <span data-ttu-id="00735-181">En la siguiente tabla se describen los métodos de la clase <xref:System.Xml.XmlWriter> que no son compatibles con la clase <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="00735-181">The following table describes the <xref:System.Xml.XmlWriter> class methods not supported by the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
|<span data-ttu-id="00735-182">Método</span><span class="sxs-lookup"><span data-stu-id="00735-182">Method</span></span>|<span data-ttu-id="00735-183">Descripción</span><span class="sxs-lookup"><span data-stu-id="00735-183">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.XmlWriter.WriteEntityRef%2A>|<span data-ttu-id="00735-184">Inicia una excepción <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="00735-184">Throws a <xref:System.NotSupportedException> exception.</span></span>|  
|<xref:System.Xml.XmlWriter.WriteDocType%2A>|<span data-ttu-id="00735-185">Se omite en el nivel raíz e inicia una excepción <xref:System.NotSupportedException> si se llama desde cualquier otro nivel del documento XML.</span><span class="sxs-lookup"><span data-stu-id="00735-185">Ignored at the root level and throws a <xref:System.NotSupportedException> exception if called at any other level in the XML document.</span></span>|  
|<xref:System.Xml.XmlWriter.WriteCData%2A>|<span data-ttu-id="00735-186">Se trata como una llamada al método <xref:System.Xml.XmlWriter.WriteString%2A> para el carácter o caracteres equivalentes.</span><span class="sxs-lookup"><span data-stu-id="00735-186">Treated as a call to the <xref:System.Xml.XmlWriter.WriteString%2A> method for the equivalent character or characters.</span></span>|  
|<xref:System.Xml.XmlWriter.WriteCharEntity%2A>|<span data-ttu-id="00735-187">Se trata como una llamada al método <xref:System.Xml.XmlWriter.WriteString%2A> para el carácter o caracteres equivalentes.</span><span class="sxs-lookup"><span data-stu-id="00735-187">Treated as a call to the <xref:System.Xml.XmlWriter.WriteString%2A> method for the equivalent character or characters.</span></span>|  
|<xref:System.Xml.XmlWriter.WriteSurrogateCharEntity%2A>|<span data-ttu-id="00735-188">Se trata como una llamada al método <xref:System.Xml.XmlWriter.WriteString%2A> para el carácter o caracteres equivalentes.</span><span class="sxs-lookup"><span data-stu-id="00735-188">Treated as a call to the <xref:System.Xml.XmlWriter.WriteString%2A> method for the equivalent character or characters.</span></span>|  
  
 <span data-ttu-id="00735-189">Para obtener más información sobre la clase <xref:System.Xml.XmlWriter>, vea la documentación de referencia de la clase <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="00735-189">For more information about the <xref:System.Xml.XmlWriter> class, see the <xref:System.Xml.XmlWriter> class reference documentation.</span></span>  
  
### <a name="multiple-xmlwriter-objects"></a><span data-ttu-id="00735-190">Varios objetos XmlWriter</span><span class="sxs-lookup"><span data-stu-id="00735-190">Multiple XmlWriter Objects</span></span>  
 <span data-ttu-id="00735-191">Es posible tener varios objetos <xref:System.Xml.XPath.XPathNavigator> apuntando a diferentes partes de un documento XML con uno o varios objetos <xref:System.Xml.XmlWriter> abiertos.</span><span class="sxs-lookup"><span data-stu-id="00735-191">It is possible to have multiple <xref:System.Xml.XPath.XPathNavigator> objects pointing to different parts of an XML document with one or more open <xref:System.Xml.XmlWriter> objects.</span></span> <span data-ttu-id="00735-192">Se permite tener varios objetos <xref:System.Xml.XmlWriter> en situaciones en las que solo hay un subproceso.</span><span class="sxs-lookup"><span data-stu-id="00735-192">Multiple <xref:System.Xml.XmlWriter> objects are allowed and supported in single-threaded scenarios.</span></span>  
  
 <span data-ttu-id="00735-193">A continuación se indican una serie de puntos importantes que hay que tener en cuenta al utilizar varios objetos <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="00735-193">The following are important notes to consider when using multiple <xref:System.Xml.XmlWriter> objects.</span></span>  
  
- <span data-ttu-id="00735-194">Se agregan fragmentos XML escritos por objetos <xref:System.Xml.XmlWriter> al documento XML cuando se llama al método <xref:System.Xml.XmlWriter.Close%2A> de cada objeto <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="00735-194">XML fragments written by <xref:System.Xml.XmlWriter> objects are added to the XML document when the <xref:System.Xml.XmlWriter.Close%2A> method of each <xref:System.Xml.XmlWriter> object is called.</span></span> <span data-ttu-id="00735-195">Hasta ese punto, el objeto <xref:System.Xml.XmlWriter> está escribiendo un fragmento desconectado.</span><span class="sxs-lookup"><span data-stu-id="00735-195">Until that point, the <xref:System.Xml.XmlWriter> object is writing a disconnected fragment.</span></span> <span data-ttu-id="00735-196">Si se realiza una operación en el documento XML, cualquier fragmento que estuviera escribiendo un objeto <xref:System.Xml.XmlWriter> antes de que se haya llamado a <xref:System.Xml.XmlWriter.Close%2A>, no resulta afectado.</span><span class="sxs-lookup"><span data-stu-id="00735-196">If an operation is performed on the XML document, any fragments being written by an <xref:System.Xml.XmlWriter> object, before the <xref:System.Xml.XmlWriter.Close%2A> has been called, are not affected.</span></span>  
  
- <span data-ttu-id="00735-197">Si hay un objeto <xref:System.Xml.XmlWriter> abierto en un subárbol XML en concreto y ese subárbol se elimina, todavía es posible agregar el objeto <xref:System.Xml.XmlWriter> al subárbol.</span><span class="sxs-lookup"><span data-stu-id="00735-197">If there is an open <xref:System.Xml.XmlWriter> object on a particular XML subtree and that subtree is deleted, the <xref:System.Xml.XmlWriter> object may still add to the sub-tree.</span></span> <span data-ttu-id="00735-198">El subárbol se convierte simplemente en un fragmento eliminado.</span><span class="sxs-lookup"><span data-stu-id="00735-198">The subtree simply becomes a deleted fragment.</span></span>  
  
- <span data-ttu-id="00735-199">Si se abren varios objetos <xref:System.Xml.XmlWriter> en el mismo punto del documento XML, se agregan al documento XML en el orden en el que se cierran los objetos <xref:System.Xml.XmlWriter>, no en el orden en el que se han abierto.</span><span class="sxs-lookup"><span data-stu-id="00735-199">If multiple <xref:System.Xml.XmlWriter> objects are opened at the same point in the XML document, they are added to the XML document in the order in which the <xref:System.Xml.XmlWriter> objects are closed, not in the order in which they were opened.</span></span>  
  
 <span data-ttu-id="00735-200">En el siguiente ejemplo se crea un objeto <xref:System.Xml.XmlDocument> y un objeto <xref:System.Xml.XPath.XPathNavigator> y, a continuación, se utiliza el objeto <xref:System.Xml.XmlWriter> que devuelve el método <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> para crear la estructura del primer libro en el archivo `books.xml`.</span><span class="sxs-lookup"><span data-stu-id="00735-200">The following example creates an <xref:System.Xml.XmlDocument> object, creates an <xref:System.Xml.XPath.XPathNavigator> object, and then uses the <xref:System.Xml.XmlWriter> object returned by the <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> method to create the structure of the first book in the `books.xml` file.</span></span> <span data-ttu-id="00735-201">A continuación, se guarda como el archivo `book.xml` en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="00735-201">The example then saves it as the `book.xml` file.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
Using writer As XmlWriter = navigator.PrependChild()  
  
    writer.WriteStartElement("bookstore")  
    writer.WriteStartElement("book")  
    writer.WriteAttributeString("genre", "autobiography")  
    writer.WriteAttributeString("publicationdate", "1981-03-22")  
    writer.WriteAttributeString("ISBN", "1-861003-11-0")  
    writer.WriteElementString("title", "The Autobiography of Benjamin Franklin")  
    writer.WriteStartElement("author")  
    writer.WriteElementString("first-name", "Benjamin")  
    writer.WriteElementString("last-name", "Franklin")  
    writer.WriteElementString("price", "8.99")  
    writer.WriteEndElement()  
    writer.WriteEndElement()  
    writer.WriteEndElement()  
  
End Using  
  
document.Save("book.xml")  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
XPathNavigator navigator = document.CreateNavigator();  
  
using (XmlWriter writer = navigator.PrependChild())  
{  
    writer.WriteStartElement("bookstore");  
    writer.WriteStartElement("book");  
    writer.WriteAttributeString("genre", "autobiography");  
    writer.WriteAttributeString("publicationdate", "1981-03-22");  
    writer.WriteAttributeString("ISBN", "1-861003-11-0");  
    writer.WriteElementString("title", "The Autobiography of Benjamin Franklin");  
    writer.WriteStartElement("author");  
    writer.WriteElementString("first-name", "Benjamin");  
    writer.WriteElementString("last-name", "Franklin");  
    writer.WriteElementString("price", "8.99");  
    writer.WriteEndElement();  
    writer.WriteEndElement();  
    writer.WriteEndElement();  
}  
document.Save("book.xml");  
```  
  
## <a name="saving-an-xml-document"></a><span data-ttu-id="00735-202">Cómo guardar un documento XML</span><span class="sxs-lookup"><span data-stu-id="00735-202">Saving an XML Document</span></span>  
 <span data-ttu-id="00735-203">Para guardar los cambios realizados en un objeto <xref:System.Xml.XmlDocument> como resultado de los métodos que se describen en este tema, se utilizan los métodos de la clase <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="00735-203">Saving changes made to an <xref:System.Xml.XmlDocument> object as the result of the methods described in this topic is performed using the methods of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="00735-204">Para obtener más información sobre cómo guardar los cambios realizados en un objeto <xref:System.Xml.XmlDocument>, vea [Guardar y escribir un documento](../../../../docs/standard/data/xml/saving-and-writing-a-document.md).</span><span class="sxs-lookup"><span data-stu-id="00735-204">For more information about saving changes made to an <xref:System.Xml.XmlDocument> object, see [Saving and Writing a Document](../../../../docs/standard/data/xml/saving-and-writing-a-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00735-205">Vea también</span><span class="sxs-lookup"><span data-stu-id="00735-205">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="00735-206">Procesamiento de datos XML con el modelo de datos XPath</span><span class="sxs-lookup"><span data-stu-id="00735-206">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="00735-207">Modificación de datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="00735-207">Modify XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="00735-208">Eliminación de datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="00735-208">Remove XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/remove-xml-data-using-xpathnavigator.md)
