---
title: Procedimiento Depurar conjuntos de resultados de consulta vacíos (Visual Basic)
ms.date: 07/20/2015
ms.assetid: b242c90a-d2b8-4309-8a1e-e4e70736c727
ms.openlocfilehash: 6fc194432b1d44c1214da32d2c6978a4eeb316dc
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "71351779"
---
# <a name="how-to-debug-empty-query-results-sets-visual-basic"></a><span data-ttu-id="ec558-102">Procedimiento Depurar conjuntos de resultados de consulta vacíos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec558-102">How to: Debug Empty Query Results Sets (Visual Basic)</span></span>

<span data-ttu-id="ec558-103">Uno de los problemas más habituales al consultar árboles XML es que si el árbol XML tiene un espacio de nombres predeterminado, el desarrollador a veces escribe la consulta como si el código XML no estuviera en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="ec558-103">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>

<span data-ttu-id="ec558-104">El primer conjunto de ejemplos de este tema muestra una forma habitual de cargar XML en un espacio de nombres predeterminado con una consulta incorrecta.</span><span class="sxs-lookup"><span data-stu-id="ec558-104">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, and is queried improperly.</span></span>

<span data-ttu-id="ec558-105">El segundo conjunto de ejemplos muestra las correcciones necesarias para que pueda consultar el código XML en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="ec558-105">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>

<span data-ttu-id="ec558-106">Para obtener más información, vea [información general sobre los espacios de nombres (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="ec558-106">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>

## <a name="example"></a><span data-ttu-id="ec558-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ec558-107">Example</span></span>

<span data-ttu-id="ec558-108">Este ejemplo muestra la creación de XML en un espacio de nombres, y una consulta que devuelve un conjunto de resultados vacío.</span><span class="sxs-lookup"><span data-stu-id="ec558-108">This example shows creation of XML in a namespace, and a query that returns an empty result set.</span></span>

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

<span data-ttu-id="ec558-109">Este ejemplo genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="ec558-109">This example produces the following result:</span></span>

```console
Result set follows:
End of result set
```

## <a name="example"></a><span data-ttu-id="ec558-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ec558-110">Example</span></span>

<span data-ttu-id="ec558-111">Este ejemplo muestra la creación de XML en un espacio de nombres, y una consulta que se codifica correctamente.</span><span class="sxs-lookup"><span data-stu-id="ec558-111">This example shows creation of XML in a namespace, and a query that is coded properly.</span></span>

<span data-ttu-id="ec558-112">La solución consiste en declarar e inicializar un espacio de nombres predeterminado global.</span><span class="sxs-lookup"><span data-stu-id="ec558-112">The solution is to declare and initialize a global default namespace.</span></span> <span data-ttu-id="ec558-113">Esto coloca todas las propiedades XML en el espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ec558-113">This places all XML properties in the default namespace.</span></span> <span data-ttu-id="ec558-114">No se requieren otras modificaciones en el ejemplo para que funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="ec558-114">No other modifications are required to the example to make it work properly.</span></span>

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

<span data-ttu-id="ec558-115">Este ejemplo genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="ec558-115">This example produces the following result:</span></span>

```console
Result set follows:
1
2
3
End of result set
```

## <a name="see-also"></a><span data-ttu-id="ec558-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec558-116">See also</span></span>

- [<span data-ttu-id="ec558-117">Consultas básicas (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec558-117">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
