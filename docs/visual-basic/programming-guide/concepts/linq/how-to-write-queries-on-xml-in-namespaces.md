---
title: Procedimiento Escribir consultas en XML en espacios de nombres (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 7d4131b5-3288-414f-b77c-b2edc2a1f465
ms.openlocfilehash: 71e66791b41e26ea13f828ef6239a8db9a9365b0
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "71835007"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-visual-basic"></a><span data-ttu-id="c6273-102">Procedimiento Escribir consultas en XML en espacios de nombres (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6273-102">How to: Write Queries on XML in Namespaces (Visual Basic)</span></span>
<span data-ttu-id="c6273-103">Para escribir una consulta en XML que esté en un espacio de nombres, debe usar objetos <xref:System.Xml.Linq.XName> que tengan el espacio de nombres correcto.</span><span class="sxs-lookup"><span data-stu-id="c6273-103">To write a query on XML that is in a namespace, you must use <xref:System.Xml.Linq.XName> objects that have the correct namespace.</span></span>  
  
 <span data-ttu-id="c6273-104">En Visual Basic, el enfoque más común consiste en definir un espacio de nombres global y después utilizar literales XML y propiedades XML que usen el espacio de nombres global.</span><span class="sxs-lookup"><span data-stu-id="c6273-104">In Visual Basic, the most common approach is to define a global namespace, and then use XML literals and XML properties that use the global namespace.</span></span> <span data-ttu-id="c6273-105">Puede definir un espacio de nombres predeterminado global, en cuyo caso los elementos de los literales XML estarán en el espacio de nombres de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c6273-105">You can define a global default namespace, in which case elements in the XML literals will be in the namespace by default.</span></span> <span data-ttu-id="c6273-106">De forma alternativa puede definir un espacio de nombres global con un prefijo y después usar el prefijo según se requiera en los literales XML y en las propiedades XML.</span><span class="sxs-lookup"><span data-stu-id="c6273-106">Alternatively, you can define a global namespace with a prefix, and then use the prefix as required in the XML literals, and in XML properties.</span></span> <span data-ttu-id="c6273-107">Al igual que con otras formas de XML, los atributos no están nunca en ningún espacio de nombres de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c6273-107">As with other forms of XML, attributes are always in no namespace by default.</span></span>  
  
 <span data-ttu-id="c6273-108">En el primer conjunto de ejemplos de este tema se muestra cómo crear un árbol XML en un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c6273-108">The first set of examples in this topic shows how to create an XML tree in a default namespace.</span></span> <span data-ttu-id="c6273-109">En el segundo conjunto se muestra cómo crear un árbol XML en un espacio de nombres con un prefijo.</span><span class="sxs-lookup"><span data-stu-id="c6273-109">The second set shows how to create an XML tree in a namespace with a prefix.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6273-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6273-110">Example</span></span>  
 <span data-ttu-id="c6273-111">En el ejemplo siguiente se crea un árbol XML que está en un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c6273-111">The following example creates an XML tree that is in a default namespace.</span></span> <span data-ttu-id="c6273-112">A continuación recupera una recopilación de elementos.</span><span class="sxs-lookup"><span data-stu-id="c6273-112">It then retrieves a collection of elements.</span></span>  
  
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
  
 <span data-ttu-id="c6273-113">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="c6273-113">This example produces the following output:</span></span>  
  
```console  
1  
2  
3  
```  
  
## <a name="example"></a><span data-ttu-id="c6273-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6273-114">Example</span></span>  
 <span data-ttu-id="c6273-115">En Visual Basic, sin embargo, escribir consultas en un árbol XML que utiliza un espacio de nombres con un prefijo es bastante diferente de consultar un árbol XML en un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c6273-115">In Visual Basic, however, writing queries on an XML tree that uses a namespace with a prefix is quite different from querying an XML tree in a default namespace.</span></span> <span data-ttu-id="c6273-116">Normalmente se usa la instrucción `Imports` para importar el espacio de nombres con un prefijo.</span><span class="sxs-lookup"><span data-stu-id="c6273-116">Typically you use the `Imports` statement to import the namespace with a prefix.</span></span> <span data-ttu-id="c6273-117">A continuación se utiliza el prefijo en los nombres del elemento y del atributo cuando se construye el árbol XML.</span><span class="sxs-lookup"><span data-stu-id="c6273-117">You then use the prefix in the element and attribute names when you construct the XML tree.</span></span> <span data-ttu-id="c6273-118">También se utiliza el prefijo al consultar un árbol XML con propiedades XML.</span><span class="sxs-lookup"><span data-stu-id="c6273-118">You also use the prefix when querying an XML tree using XML properties.</span></span>  
  
 <span data-ttu-id="c6273-119">En el ejemplo siguiente se crea un árbol XML que está en un espacio de nombres con un prefijo.</span><span class="sxs-lookup"><span data-stu-id="c6273-119">The following example creates an XML tree that is in a namespace with a prefix.</span></span> <span data-ttu-id="c6273-120">A continuación recupera una recopilación de elementos.</span><span class="sxs-lookup"><span data-stu-id="c6273-120">It then retrieves a collection of elements.</span></span>  
  
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
  
 <span data-ttu-id="c6273-121">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="c6273-121">This example produces the following output:</span></span>  
  
```console  
1  
2  
3  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6273-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6273-122">See also</span></span>

- [<span data-ttu-id="c6273-123">Información general sobre espacios de nombres (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6273-123">Namespaces Overview (LINQ to XML) (Visual Basic)</span></span>](namespaces-overview-linq-to-xml.md)
