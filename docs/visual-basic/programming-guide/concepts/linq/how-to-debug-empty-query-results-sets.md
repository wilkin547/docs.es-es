---
title: 'Cómo: Depurar conjuntos de resultados de consulta vacíos'
ms.date: 07/20/2015
ms.assetid: b242c90a-d2b8-4309-8a1e-e4e70736c727
ms.openlocfilehash: 21c161a702338c0c6943fa09212deaea7fdd72f9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353076"
---
# <a name="how-to-debug-empty-query-results-sets-visual-basic"></a><span data-ttu-id="5366c-102">How to: Debug Empty Query Results Sets (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5366c-102">How to: Debug Empty Query Results Sets (Visual Basic)</span></span>

<span data-ttu-id="5366c-103">Uno de los problemas más habituales al consultar árboles XML es que si el árbol XML tiene un espacio de nombres predeterminado, el desarrollador a veces escribe la consulta como si el código XML no estuviera en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="5366c-103">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>

<span data-ttu-id="5366c-104">El primer conjunto de ejemplos de este tema muestra una forma habitual de cargar XML en un espacio de nombres predeterminado con una consulta incorrecta.</span><span class="sxs-lookup"><span data-stu-id="5366c-104">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, and is queried improperly.</span></span>

<span data-ttu-id="5366c-105">El segundo conjunto de ejemplos muestra las correcciones necesarias para que pueda consultar el código XML en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="5366c-105">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>

<span data-ttu-id="5366c-106">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="5366c-106">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>

## <a name="example"></a><span data-ttu-id="5366c-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5366c-107">Example</span></span>

<span data-ttu-id="5366c-108">Este ejemplo muestra la creación de XML en un espacio de nombres, y una consulta que devuelve un conjunto de resultados vacío.</span><span class="sxs-lookup"><span data-stu-id="5366c-108">This example shows creation of XML in a namespace, and a query that returns an empty result set.</span></span>

```vb
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
```

<span data-ttu-id="5366c-109">Este ejemplo genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="5366c-109">This example produces the following result:</span></span>

```console
Result set follows:
End of result set
```

## <a name="example"></a><span data-ttu-id="5366c-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5366c-110">Example</span></span>

<span data-ttu-id="5366c-111">Este ejemplo muestra la creación de XML en un espacio de nombres, y una consulta que se codifica correctamente.</span><span class="sxs-lookup"><span data-stu-id="5366c-111">This example shows creation of XML in a namespace, and a query that is coded properly.</span></span>

<span data-ttu-id="5366c-112">The solution is to declare and initialize a global default namespace.</span><span class="sxs-lookup"><span data-stu-id="5366c-112">The solution is to declare and initialize a global default namespace.</span></span> <span data-ttu-id="5366c-113">Esto coloca todas las propiedades XML en el espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5366c-113">This places all XML properties in the default namespace.</span></span> <span data-ttu-id="5366c-114">No se requieren otras modificaciones en el ejemplo para que funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="5366c-114">No other modifications are required to the example to make it work properly.</span></span>

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
            Console.WriteLine(CInt(el))
        Next
        Console.WriteLine("End of result set")
    End Sub
End Module
```

<span data-ttu-id="5366c-115">Este ejemplo genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="5366c-115">This example produces the following result:</span></span>

```console
Result set follows:
1
2
3
End of result set
```

## <a name="see-also"></a><span data-ttu-id="5366c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5366c-116">See also</span></span>

- [<span data-ttu-id="5366c-117">Basic Queries (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5366c-117">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
