---
title: 'Cómo: Escribir consultas de XML en espacios de nombres'
ms.date: 07/20/2015
ms.assetid: 7d4131b5-3288-414f-b77c-b2edc2a1f465
ms.openlocfilehash: 496cf8daf5136e8aafff000312bbd730a5152e9f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344471"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-visual-basic"></a><span data-ttu-id="760b7-102">How to: Write Queries on XML in Namespaces (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="760b7-102">How to: Write Queries on XML in Namespaces (Visual Basic)</span></span>
<span data-ttu-id="760b7-103">Para escribir una consulta en XML que esté en un espacio de nombres, debe usar objetos <xref:System.Xml.Linq.XName> que tengan el espacio de nombres correcto.</span><span class="sxs-lookup"><span data-stu-id="760b7-103">To write a query on XML that is in a namespace, you must use <xref:System.Xml.Linq.XName> objects that have the correct namespace.</span></span>  
  
 <span data-ttu-id="760b7-104">En Visual Basic, el enfoque más común consiste en definir un espacio de nombres global y después utilizar literales XML y propiedades XML que usen el espacio de nombres global.</span><span class="sxs-lookup"><span data-stu-id="760b7-104">In Visual Basic, the most common approach is to define a global namespace, and then use XML literals and XML properties that use the global namespace.</span></span> <span data-ttu-id="760b7-105">Puede definir un espacio de nombres predeterminado global, en cuyo caso los elementos de los literales XML estarán en el espacio de nombres de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="760b7-105">You can define a global default namespace, in which case elements in the XML literals will be in the namespace by default.</span></span> <span data-ttu-id="760b7-106">De forma alternativa puede definir un espacio de nombres global con un prefijo y después usar el prefijo según se requiera en los literales XML y en las propiedades XML.</span><span class="sxs-lookup"><span data-stu-id="760b7-106">Alternatively, you can define a global namespace with a prefix, and then use the prefix as required in the XML literals, and in XML properties.</span></span> <span data-ttu-id="760b7-107">Al igual que con otras formas de XML, los atributos no están nunca en ningún espacio de nombres de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="760b7-107">As with other forms of XML, attributes are always in no namespace by default.</span></span>  
  
 <span data-ttu-id="760b7-108">En el primer conjunto de ejemplos de este tema se muestra cómo crear un árbol XML en un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="760b7-108">The first set of examples in this topic shows how to create an XML tree in a default namespace.</span></span> <span data-ttu-id="760b7-109">En el segundo conjunto se muestra cómo crear un árbol XML en un espacio de nombres con un prefijo.</span><span class="sxs-lookup"><span data-stu-id="760b7-109">The second set shows how to create an XML tree in a namespace with a prefix.</span></span>  
  
## <a name="example"></a><span data-ttu-id="760b7-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="760b7-110">Example</span></span>  
 <span data-ttu-id="760b7-111">En el ejemplo siguiente se crea un árbol XML que está en un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="760b7-111">The following example creates an XML tree that is in a default namespace.</span></span> <span data-ttu-id="760b7-112">A continuación recupera una recopilación de elementos.</span><span class="sxs-lookup"><span data-stu-id="760b7-112">It then retrieves a collection of elements.</span></span>  
  
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
  
 <span data-ttu-id="760b7-113">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="760b7-113">This example produces the following output:</span></span>  
  
```console  
1  
2  
3  
```  
  
## <a name="example"></a><span data-ttu-id="760b7-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="760b7-114">Example</span></span>  
 <span data-ttu-id="760b7-115">En Visual Basic, sin embargo, escribir consultas en un árbol XML que utiliza un espacio de nombres con un prefijo es bastante diferente de consultar un árbol XML en un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="760b7-115">In Visual Basic, however, writing queries on an XML tree that uses a namespace with a prefix is quite different from querying an XML tree in a default namespace.</span></span> <span data-ttu-id="760b7-116">Normalmente se usa la instrucción `Imports` para importar el espacio de nombres con un prefijo.</span><span class="sxs-lookup"><span data-stu-id="760b7-116">Typically you use the `Imports` statement to import the namespace with a prefix.</span></span> <span data-ttu-id="760b7-117">A continuación se utiliza el prefijo en los nombres del elemento y del atributo cuando se construye el árbol XML.</span><span class="sxs-lookup"><span data-stu-id="760b7-117">You then use the prefix in the element and attribute names when you construct the XML tree.</span></span> <span data-ttu-id="760b7-118">También se utiliza el prefijo al consultar un árbol XML con propiedades XML.</span><span class="sxs-lookup"><span data-stu-id="760b7-118">You also use the prefix when querying an XML tree using XML properties.</span></span>  
  
 <span data-ttu-id="760b7-119">En el ejemplo siguiente se crea un árbol XML que está en un espacio de nombres con un prefijo.</span><span class="sxs-lookup"><span data-stu-id="760b7-119">The following example creates an XML tree that is in a namespace with a prefix.</span></span> <span data-ttu-id="760b7-120">A continuación recupera una recopilación de elementos.</span><span class="sxs-lookup"><span data-stu-id="760b7-120">It then retrieves a collection of elements.</span></span>  
  
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
  
 <span data-ttu-id="760b7-121">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="760b7-121">This example produces the following output:</span></span>  
  
```console  
1  
2  
3  
```  
  
## <a name="see-also"></a><span data-ttu-id="760b7-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="760b7-122">See also</span></span>

- [<span data-ttu-id="760b7-123">Namespaces Overview (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="760b7-123">Namespaces Overview (LINQ to XML) (Visual Basic)</span></span>](namespaces-overview-linq-to-xml.md)
