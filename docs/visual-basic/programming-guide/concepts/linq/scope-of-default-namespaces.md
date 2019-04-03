---
title: Ámbito de espacio de nombres predeterminado en Visual Basic
ms.date: 07/20/2015
ms.assetid: d4cce80c-342f-4097-be8b-40ab0bfa90ba
ms.openlocfilehash: e33505dd8e8ad94e3c758f15f245d0cbaf6987bc
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836719"
---
# <a name="scope-of-default-namespaces-in-visual-basic"></a><span data-ttu-id="2d84c-102">Ámbito de espacio de nombres predeterminado en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2d84c-102">Scope of Default Namespaces in Visual Basic</span></span>
<span data-ttu-id="2d84c-103">Los espacios de nombres predeterminados del árbol XML no se encuentran en el ámbito de las consultas.</span><span class="sxs-lookup"><span data-stu-id="2d84c-103">Default namespaces as represented in the XML tree are not in scope for queries.</span></span> <span data-ttu-id="2d84c-104">Si tiene código XML en un espacio de nombres predeterminado, debe declarar una variable <xref:System.Xml.Linq.XNamespace> y combinarla con el nombre local para convertirla en un nombre completo que se usará en la consulta.</span><span class="sxs-lookup"><span data-stu-id="2d84c-104">If you have XML that is in a default namespace, you still must declare an <xref:System.Xml.Linq.XNamespace> variable, and combine it with the local name to make a qualified name to be used in the query.</span></span>  
  
 <span data-ttu-id="2d84c-105">Uno de los problemas más habituales al consultar árboles XML es que si el árbol XML tiene un espacio de nombres predeterminado, el desarrollador a veces escribe la consulta como si el código XML no estuviera en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2d84c-105">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="2d84c-106">El primer conjunto de ejemplos de este tema muestra una forma habitual de cargar XML en un espacio de nombres predeterminado con una consulta incorrecta.</span><span class="sxs-lookup"><span data-stu-id="2d84c-106">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, but is queried improperly.</span></span>  
  
 <span data-ttu-id="2d84c-107">El segundo conjunto de ejemplos muestra las correcciones necesarias para que pueda consultar el código XML en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2d84c-107">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d84c-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d84c-108">Example</span></span>  
 <span data-ttu-id="2d84c-109">En este ejemplo se muestra la creación de XML en un espacio de nombres y una consulta que devuelve un conjunto de resultados vacío.</span><span class="sxs-lookup"><span data-stu-id="2d84c-109">This example shows the creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2d84c-110">Código</span><span class="sxs-lookup"><span data-stu-id="2d84c-110">Code</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root xmlns='http://www.adventure-works.com'>  
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
        Console.WriteLine("Result set follows:")  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="2d84c-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d84c-111">Comments</span></span>  
 <span data-ttu-id="2d84c-112">Este ejemplo genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="2d84c-112">This example produces the following result:</span></span>  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="2d84c-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d84c-113">Example</span></span>  
 <span data-ttu-id="2d84c-114">En este ejemplo se muestra la creación de XML en un espacio de nombres y una consulta que se codifica correctamente.</span><span class="sxs-lookup"><span data-stu-id="2d84c-114">This example shows the creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="2d84c-115">A diferencia del ejemplo de código incorrecto anterior, el enfoque correcto al usar Visual Basic es declarar e inicializar un espacio de nombres predeterminado global.</span><span class="sxs-lookup"><span data-stu-id="2d84c-115">In contrast to the incorrectly coded example above, the correct approach when using Visual Basic is to declare and initialize a global default namespace.</span></span> <span data-ttu-id="2d84c-116">Esto coloca todas las propiedades XML en el espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2d84c-116">This places all XML properties in the default namespace.</span></span> <span data-ttu-id="2d84c-117">No se requieren otras modificaciones en el ejemplo para que funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="2d84c-117">No other modifications are required to the example to make it work properly.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2d84c-118">Código</span><span class="sxs-lookup"><span data-stu-id="2d84c-118">Code</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root xmlns='http://www.adventure-works.com'>  
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
        Console.WriteLine("Result set follows:")  
        For Each el As XElement In c1  
            Console.WriteLine(el.Value)  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="2d84c-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d84c-119">Comments</span></span>  
 <span data-ttu-id="2d84c-120">Este ejemplo genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="2d84c-120">This example produces the following result:</span></span>  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d84c-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d84c-121">See also</span></span>

- [<span data-ttu-id="2d84c-122">Trabajar con espacios de nombres XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d84c-122">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
