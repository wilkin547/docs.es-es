---
title: Crear nuevos atributos para elementos en DOM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: dd6dc920-b011-418a-b3db-f1580a7d9251
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4f3ae0c3db65fe7bda1bcc5bd247fea80a2a9c4e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="creating-new-attributes-for-elements-in-the-dom"></a><span data-ttu-id="fdfe1-102">Crear nuevos atributos para elementos en DOM</span><span class="sxs-lookup"><span data-stu-id="fdfe1-102">Creating New Attributes for Elements in the DOM</span></span>
<span data-ttu-id="fdfe1-103">La creación de nuevos atributos es diferente de la creación de otros tipos de nodo, puesto que los atributos no son nodos, sino propiedades de un nodo de elemento y se incluyen en un **XmlAttributeCollection** asociado al elemento.</span><span class="sxs-lookup"><span data-stu-id="fdfe1-103">Creating new attributes is different than creating other node types, because attributes are not nodes, but are properties of an element node and are contained in an **XmlAttributeCollection** associated with the element.</span></span> <span data-ttu-id="fdfe1-104">Hay varias formas de crear un atributo y adjuntarlo a un elemento:</span><span class="sxs-lookup"><span data-stu-id="fdfe1-104">There are multiple ways to create an attribute and attach it to an element:</span></span>  
  
-   <span data-ttu-id="fdfe1-105">Para agregar un atributo a la colección de atributos de dicho elemento, obtenga el nodo de elemento y utilice **SetAttribute**.</span><span class="sxs-lookup"><span data-stu-id="fdfe1-105">Get the element node and use **SetAttribute** to add an attribute to the attribute collection of that element.</span></span>  
  
-   <span data-ttu-id="fdfe1-106">Cree un nodo **XmlAttribute** mediante el método **CreateAttribute**, obtenga el nodo del elemento y, a continuación, utilice el método **SetAttributeNode** para agregar el nodo a la colección de atributos de dicho elemento.</span><span class="sxs-lookup"><span data-stu-id="fdfe1-106">Create an **XmlAttribute** node using the **CreateAttribute** method, get the element node, then use **SetAttributeNode** to add the node to the attribute collection of that element.</span></span>  
  
 <span data-ttu-id="fdfe1-107">En el ejemplo siguiente se muestra cómo agregar un atributo a un elemento mediante el método **SetAttribute**.</span><span class="sxs-lookup"><span data-stu-id="fdfe1-107">The following example shows how to add an attribute to an element using the **SetAttribute** method.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
public class Sample  
  
  public shared sub Main()  
  
  Dim doc as XmlDocument = new XmlDocument()  
  doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" & _  
              "<title>Pride And Prejudice</title>" & _  
              "</book>")  
  Dim root as XmlElement = doc.DocumentElement  
  
  'Add a new attribute.  
  root.SetAttribute("genre", "urn:samples", "novel")  
  
  Console.WriteLine("Display the modified XML...")  
  Console.WriteLine(doc.InnerXml)  
  
  end sub  
end class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
  public static void Main()  
  {  
    XmlDocument doc = new XmlDocument();  
    doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" +  
                "<title>Pride And Prejudice</title>" +  
                "</book>");  
    XmlElement root = doc.DocumentElement;  
  
    // Add a new attribute.  
    root.SetAttribute("genre", "urn:samples", "novel");  
  
    Console.WriteLine("Display the modified XML...");  
    Console.WriteLine(doc.InnerXml);  
  }  
```  
  
 <span data-ttu-id="fdfe1-108">En el ejemplo siguiente se muestra un nuevo atributo que se crea mediante el método **CreateAttribute**.</span><span class="sxs-lookup"><span data-stu-id="fdfe1-108">The following example shows a new attribute being created using the **CreateAttribute** method.</span></span> <span data-ttu-id="fdfe1-109">Después, se muestra el atributo agregado a la colección de atributos del elemento **book** mediante el método **SetAttributeNode**.</span><span class="sxs-lookup"><span data-stu-id="fdfe1-109">It then shows the attribute added to the attribute collection of the **book** element using the **SetAttributeNode** method.</span></span>  
  
 <span data-ttu-id="fdfe1-110">Dado el siguiente XML:</span><span class="sxs-lookup"><span data-stu-id="fdfe1-110">Given the following XML:</span></span>  
  
```xml  
<book genre='novel' ISBN='1-861001-57-5'>  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 <span data-ttu-id="fdfe1-111">cree un atributo nuevo y asígnele un valor:</span><span class="sxs-lookup"><span data-stu-id="fdfe1-111">create a new attribute and give it a value:</span></span>  
  
```vb  
Dim attr As XmlAttribute = doc.CreateAttribute("publisher")  
   attr.Value = "WorldWide Publishing"  
```  
  
```csharp  
XmlAttribute attr = doc.CreateAttribute("publisher");  
attr.Value = "WorldWide Publishing";  
```  
  
 <span data-ttu-id="fdfe1-112">y asócielo al elemento:</span><span class="sxs-lookup"><span data-stu-id="fdfe1-112">and attach it to the element:</span></span>  
  
```vb  
doc.DocumentElement.SetAttributeNode(attr)  
```  
  
```csharp  
doc.DocumentElement.SetAttributeNode(attr);  
```  
  
 <span data-ttu-id="fdfe1-113">**Salida**</span><span class="sxs-lookup"><span data-stu-id="fdfe1-113">**Output**</span></span>  
  
```xml  
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 <span data-ttu-id="fdfe1-114">El ejemplo de código completo se puede encontrar en <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span><span class="sxs-lookup"><span data-stu-id="fdfe1-114">The full code sample can be found at <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span></span>  
  
 <span data-ttu-id="fdfe1-115">También se puede crear un nodo **XmlAttribute** y utilizar los métodos **InsertBefore** o **InsertAfter** para colocarlo en la posición adecuada en la colección.</span><span class="sxs-lookup"><span data-stu-id="fdfe1-115">You can also create an **XmlAttribute** node and use the **InsertBefore** or **InsertAfter** methods to place it in the appropriate position in the collection.</span></span> <span data-ttu-id="fdfe1-116">Si en la colección de atributos ya hay uno con el mismo nombre, el nodo **XmlAttribute** existente se quita de la colección y se inserta el nuevo nodo **XmlAttribute**.</span><span class="sxs-lookup"><span data-stu-id="fdfe1-116">If an attribute with the same name is already present in the attribute collection, the existing **XmlAttribute** node is removed from the collection and the new **XmlAttribute** node is inserted.</span></span> <span data-ttu-id="fdfe1-117">Funciona del mismo modo que el método **SetAttribute**.</span><span class="sxs-lookup"><span data-stu-id="fdfe1-117">This performs the same way as the **SetAttribute** method.</span></span> <span data-ttu-id="fdfe1-118">Estos métodos aceptan, como parámetro, un nodo existente como punto de referencia para ejecutar los métodos **InsertBefore** e **InsertAfter**.</span><span class="sxs-lookup"><span data-stu-id="fdfe1-118">These methods take, as a parameter, an existing node as a reference point to do the **InsertBefore** and **InsertAfter**.</span></span> <span data-ttu-id="fdfe1-119">Si no se proporciona un nodo de referencia que indique dónde insertar el nodo nuevo, con la configuración predeterminada del método **InsertAfter** el nodo nuevo se inserta al principio de la colección.</span><span class="sxs-lookup"><span data-stu-id="fdfe1-119">If you do not provide a reference node indicating where to insert the new node, the default for the **InsertAfter** method is to insert the new node at the beginning of the collection.</span></span> <span data-ttu-id="fdfe1-120">La posición predeterminada para **InsertBefore**, si no se proporciona ningún nodo de referencia, es el final de la colección.</span><span class="sxs-lookup"><span data-stu-id="fdfe1-120">The default position for the **InsertBefore**, if no reference node is provided, is at the end of the collection.</span></span>  
  
 <span data-ttu-id="fdfe1-121">Si creó una clase **XmlNamedNodeMap** de atributos, puede agregar un atributo por nombre mediante el método <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="fdfe1-121">If you created an **XmlNamedNodeMap** of attributes, you can add an attribute by name using the <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>.</span></span> <span data-ttu-id="fdfe1-122">Para obtener más información, vea [Colecciones de nodos en NamedNodeMaps y NodeLists](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).</span><span class="sxs-lookup"><span data-stu-id="fdfe1-122">For more information, see [Node Collections in NamedNodeMaps and NodeLists](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).</span></span>  
  
## <a name="default-attributes"></a><span data-ttu-id="fdfe1-123">Atributos predeterminados</span><span class="sxs-lookup"><span data-stu-id="fdfe1-123">Default Attributes</span></span>  
 <span data-ttu-id="fdfe1-124">Si creó un elemento declarado para tener un atributo predeterminado, el Modelo de objetos de documento (DOM) crea un nuevo atributo predeterminado con su valor predeterminado y lo adjunta al elemento.</span><span class="sxs-lookup"><span data-stu-id="fdfe1-124">If you create an element that is declared to have a default attribute, then a new default attribute with its default value is created by the XML Document Object Model (DOM) and attached to the element.</span></span> <span data-ttu-id="fdfe1-125">Los nodos secundarios del atributo predeterminado se crean también en este momento.</span><span class="sxs-lookup"><span data-stu-id="fdfe1-125">The child nodes of the default attribute are also created at this time.</span></span>  
  
## <a name="attribute-child-nodes"></a><span data-ttu-id="fdfe1-126">Nodos secundarios de atributo</span><span class="sxs-lookup"><span data-stu-id="fdfe1-126">Attribute Child Nodes</span></span>  
 <span data-ttu-id="fdfe1-127">El valor de un nodo de atributo se convierte en sus nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="fdfe1-127">The value of an attribute node becomes its child nodes.</span></span> <span data-ttu-id="fdfe1-128">Hay solo dos tipos válidos de nodos secundarios: los nodos **XmlText** y **XmlEntityReference**.</span><span class="sxs-lookup"><span data-stu-id="fdfe1-128">There are only two types of valid child nodes: **XmlText** nodes, and **XmlEntityReference** nodes.</span></span> <span data-ttu-id="fdfe1-129">Se trata de nodos secundarios en el sentido de que métodos como **FirstChild** y **LastChild** los procesan como tales.</span><span class="sxs-lookup"><span data-stu-id="fdfe1-129">These are child nodes in the sense that methods such as **FirstChild** and **LastChild** process them as child nodes.</span></span> <span data-ttu-id="fdfe1-130">Esta distinción de un atributo con nodos secundarios es importante cuando se intenta quitar atributos o nodos secundarios de atributo.</span><span class="sxs-lookup"><span data-stu-id="fdfe1-130">This distinction of an attribute having child nodes is important when trying to remove attributes or attribute child nodes.</span></span> <span data-ttu-id="fdfe1-131">Para obtener más información, vea [Cómo quitar atributos de un nodo de elemento en DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="fdfe1-131">For more information, see [Removing Attributes from an Element Node in the DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdfe1-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdfe1-132">See Also</span></span>  
 [<span data-ttu-id="fdfe1-133">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="fdfe1-133">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
