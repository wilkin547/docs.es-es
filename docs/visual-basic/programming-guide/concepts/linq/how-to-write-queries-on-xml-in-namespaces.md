---
title: "Cómo: escribir consultas en XML en espacios de nombres (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d4131b5-3288-414f-b77c-b2edc2a1f465
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5708a2a162132262722f390842f59c9c6a6838e4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-write-queries-on-xml-in-namespaces-visual-basic"></a><span data-ttu-id="c253d-102">Cómo: escribir consultas en XML en espacios de nombres (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c253d-102">How to: Write Queries on XML in Namespaces (Visual Basic)</span></span>
<span data-ttu-id="c253d-103">Para escribir una consulta en XML que esté en un espacio de nombres, debe usar objetos <xref:System.Xml.Linq.XName> que tengan el espacio de nombres correcto.</span><span class="sxs-lookup"><span data-stu-id="c253d-103">To write a query on XML that is in a namespace, you must use <xref:System.Xml.Linq.XName> objects that have the correct namespace.</span></span>  
  
 <span data-ttu-id="c253d-104">En Visual Basic, el enfoque más común consiste en definir un espacio de nombres global y después utilizar literales XML y propiedades XML que usen el espacio de nombres global.</span><span class="sxs-lookup"><span data-stu-id="c253d-104">In Visual Basic, the most common approach is to define a global namespace, and then use XML literals and XML properties that use the global namespace.</span></span> <span data-ttu-id="c253d-105">Puede definir un espacio de nombres predeterminado global, en cuyo caso los elementos de los literales XML estarán en el espacio de nombres de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c253d-105">You can define a global default namespace, in which case elements in the XML literals will be in the namespace by default.</span></span> <span data-ttu-id="c253d-106">De forma alternativa puede definir un espacio de nombres global con un prefijo y después usar el prefijo según se requiera en los literales XML y en las propiedades XML.</span><span class="sxs-lookup"><span data-stu-id="c253d-106">Alternatively, you can define a global namespace with a prefix, and then use the prefix as required in the XML literals, and in XML properties.</span></span> <span data-ttu-id="c253d-107">Al igual que con otras formas de XML, los atributos no están nunca en ningún espacio de nombres de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c253d-107">As with other forms of XML, attributes are always in no namespace by default.</span></span>  
  
 <span data-ttu-id="c253d-108">En el primer conjunto de ejemplos de este tema se muestra cómo crear un árbol XML en un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c253d-108">The first set of examples in this topic shows how to create an XML tree in a default namespace.</span></span> <span data-ttu-id="c253d-109">En el segundo conjunto se muestra cómo crear un árbol XML en un espacio de nombres con un prefijo.</span><span class="sxs-lookup"><span data-stu-id="c253d-109">The second set shows how to create an XML tree in a namespace with a prefix.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c253d-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c253d-110">Example</span></span>  
 <span data-ttu-id="c253d-111">En el ejemplo siguiente se crea un árbol XML que está en un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c253d-111">The following example creates an XML tree that is in a default namespace.</span></span> <span data-ttu-id="c253d-112">A continuación recupera una recopilación de elementos.</span><span class="sxs-lookup"><span data-stu-id="c253d-112">It then retrieves a collection of elements.</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
            From el In root.<Child> _  
            Select el  
        For Each el As XElement In c1  
            Console.WriteLine(el.Value)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="c253d-113">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="c253d-113">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="example"></a><span data-ttu-id="c253d-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c253d-114">Example</span></span>  
 <span data-ttu-id="c253d-115">En Visual Basic, sin embargo, escribir consultas en un árbol XML que utiliza un espacio de nombres con un prefijo es bastante diferente de consultar un árbol XML en un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c253d-115">In Visual Basic, however, writing queries on an XML tree that uses a namespace with a prefix is quite different from querying an XML tree in a default namespace.</span></span> <span data-ttu-id="c253d-116">Normalmente se usa la instrucción `Imports` para importar el espacio de nombres con un prefijo.</span><span class="sxs-lookup"><span data-stu-id="c253d-116">Typically you use the `Imports` statement to import the namespace with a prefix.</span></span> <span data-ttu-id="c253d-117">A continuación se utiliza el prefijo en los nombres del elemento y del atributo cuando se construye el árbol XML.</span><span class="sxs-lookup"><span data-stu-id="c253d-117">You then use the prefix in the element and attribute names when you construct the XML tree.</span></span> <span data-ttu-id="c253d-118">También se utiliza el prefijo al consultar un árbol XML con propiedades XML.</span><span class="sxs-lookup"><span data-stu-id="c253d-118">You also use the prefix when querying an XML tree using XML properties.</span></span>  
  
 <span data-ttu-id="c253d-119">En el ejemplo siguiente se crea un árbol XML que está en un espacio de nombres con un prefijo.</span><span class="sxs-lookup"><span data-stu-id="c253d-119">The following example creates an XML tree that is in a namespace with a prefix.</span></span> <span data-ttu-id="c253d-120">A continuación recupera una recopilación de elementos.</span><span class="sxs-lookup"><span data-stu-id="c253d-120">It then retrieves a collection of elements.</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child>1</aw:Child>  
                <aw:Child>2</aw:Child>  
                <aw:Child>3</aw:Child>  
                <aw:AnotherChild>4</aw:AnotherChild>  
                <aw:AnotherChild>5</aw:AnotherChild>  
                <aw:AnotherChild>6</aw:AnotherChild>  
            </aw:Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
            From el In root.<aw:Child> _  
            Select el  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="c253d-121">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="c253d-121">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="see-also"></a><span data-ttu-id="c253d-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="c253d-122">See Also</span></span>  
 [<span data-ttu-id="c253d-123">Trabajar con espacios de nombres XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c253d-123">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
