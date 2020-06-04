---
title: Procedimiento para crear un documento con espacios de nombres (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: cc5b0d4d-360c-4ada-94fa-2d2916e989be
ms.openlocfilehash: a440c9d810798eb5ebd025a336cbb17fface23b4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414639"
---
# <a name="how-to-create-a-document-with-namespaces-linq-to-xml-visual-basic"></a><span data-ttu-id="e0bc3-102">Cómo: Crear un documento con espacios de nombres (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0bc3-102">How to: Create a Document with Namespaces (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="e0bc3-103">En este tema se muestra cómo crear un documento con espacios de nombres en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e0bc3-103">This topic shows how to create a document with namespaces in Visual Basic.</span></span>  
  
 <span data-ttu-id="e0bc3-104">Cuando se utilizan literales XML en Visual Basic, los usuarios pueden definir un espacio de nombres XML predeterminado que sea global.</span><span class="sxs-lookup"><span data-stu-id="e0bc3-104">When using XML literals in Visual Basic, users can define one global default XML namespace.</span></span> <span data-ttu-id="e0bc3-105">Este espacio de nombres será el predeterminado tanto para los literales XML como para las propiedades XML.</span><span class="sxs-lookup"><span data-stu-id="e0bc3-105">This namespace is the default namespace for both XML literals and XML properties.</span></span> <span data-ttu-id="e0bc3-106">Es posible definir el espacio de nombres XML predeterminado tanto en el nivel de proyecto como en el nivel de archivo.</span><span class="sxs-lookup"><span data-stu-id="e0bc3-106">The default XML namespace can be defined at either the project level or the file level.</span></span> <span data-ttu-id="e0bc3-107">En caso de definirlo a nivel de archivo, éste reemplazará al espacio de nombres predeterminado que se definió a nivel del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0bc3-107">If it is defined at the file level, it overrides the default namespace at the project level.</span></span>  
  
 <span data-ttu-id="e0bc3-108">También puede definir otros espacios de nombres y especificar para ellos los prefijos de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e0bc3-108">You can also define other namespaces, and specify the namespace prefixes for those namespaces.</span></span>  
  
 <span data-ttu-id="e0bc3-109">Mediante la palabra clave `Imports` podrá definir espacios de nombres predeterminados y espacios de nombres con un prefijo.</span><span class="sxs-lookup"><span data-stu-id="e0bc3-109">You define both default namespaces and namespaces with a prefix by using the `Imports` keyword.</span></span>  
  
 <span data-ttu-id="e0bc3-110">Para obtener más información, vea [Introducción a los literales XML en Visual Basic](introduction-to-xml-literals.md).</span><span class="sxs-lookup"><span data-stu-id="e0bc3-110">For more information, see [Introduction to XML Literals in Visual Basic](introduction-to-xml-literals.md).</span></span>  
  
 <span data-ttu-id="e0bc3-111">Observe que el espacio de nombres XML predeterminado solo puede aplicarse a los elementos, no a los atributos.</span><span class="sxs-lookup"><span data-stu-id="e0bc3-111">Note that the default XML namespace only applies to elements and not to attributes.</span></span> <span data-ttu-id="e0bc3-112">De forma predeterminada, los atributos nunca se encuentran en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e0bc3-112">Attributes are by default always in no namespace.</span></span> <span data-ttu-id="e0bc3-113">No obstante, puede utilizar un prefijo de espacio de nombres para colocar un atributo en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e0bc3-113">However, you can use a namespace prefix to put an attribute in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0bc3-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0bc3-114">Example</span></span>  
 <span data-ttu-id="e0bc3-115">Este ejemplo crea un documento que contiene un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e0bc3-115">This example creates a document that contains a namespace.</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child aw:Att="attvalue"/>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="e0bc3-116">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="e0bc3-116">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child aw:Att="attvalue" />  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="e0bc3-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0bc3-117">Example</span></span>  
 <span data-ttu-id="e0bc3-118">Este ejemplo crea un documento que contiene dos espacios de nombres, uno de los cuales es el predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e0bc3-118">This example creates a document that contains two namespaces, one of which is the default namespace.</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child Att="attvalue"/>  
                <fc:Child2>child2 content</fc:Child2>  
            </Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="e0bc3-119">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="e0bc3-119">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns:fc="www.fourthcoffee.com" xmlns="http://www.adventure-works.com">  
  <Child Att="attvalue" />  
  <fc:Child2>child2 content</fc:Child2>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="e0bc3-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0bc3-120">Example</span></span>  
 <span data-ttu-id="e0bc3-121">El ejemplo siguiente crea un documento que contiene varios espacios de nombres, todos ellos con prefijos de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e0bc3-121">The following example creates a document that contains multiple namespaces, both with namespace prefixes.</span></span>  
  
 <span data-ttu-id="e0bc3-122">Cuando se serializa un árbol XML, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] emite declaraciones de espacios de nombres a medida que se necesitan, para que cada elemento se encuentre en su espacio de nombres designado.</span><span class="sxs-lookup"><span data-stu-id="e0bc3-122">When serializing an XML tree, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] emits namespace declarations as required so that each element is in its designated namespace.</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <fc:Child>  
                    <aw:DifferentChild>other content</aw:DifferentChild>  
                </fc:Child>  
                <aw:Child2>c2 content</aw:Child2>  
                <fc:Child3>c3 content</fc:Child3>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="e0bc3-123">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="e0bc3-123">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e0bc3-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0bc3-124">See also</span></span>

- [<span data-ttu-id="e0bc3-125">Información general sobre espacios de nombres (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0bc3-125">Namespaces Overview (LINQ to XML) (Visual Basic)</span></span>](namespaces-overview-linq-to-xml.md)
