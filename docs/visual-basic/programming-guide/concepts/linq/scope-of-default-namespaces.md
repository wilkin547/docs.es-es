---
title: Ámbito de los espacios de nombres predeterminado
ms.date: 07/20/2015
ms.assetid: d4cce80c-342f-4097-be8b-40ab0bfa90ba
ms.openlocfilehash: 8ba4d13b6d40180a88651f0503d1323f2b78f36c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343646"
---
# <a name="scope-of-default-namespaces-in-visual-basic"></a><span data-ttu-id="e796b-102">Ámbito de los espacios de nombres predeterminados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e796b-102">Scope of Default Namespaces in Visual Basic</span></span>
<span data-ttu-id="e796b-103">Los espacios de nombres predeterminados del árbol XML no se encuentran en el ámbito de las consultas.</span><span class="sxs-lookup"><span data-stu-id="e796b-103">Default namespaces as represented in the XML tree are not in scope for queries.</span></span> <span data-ttu-id="e796b-104">Si tiene código XML en un espacio de nombres predeterminado, debe declarar una variable <xref:System.Xml.Linq.XNamespace> y combinarla con el nombre local para convertirla en un nombre completo que se usará en la consulta.</span><span class="sxs-lookup"><span data-stu-id="e796b-104">If you have XML that is in a default namespace, you still must declare an <xref:System.Xml.Linq.XNamespace> variable, and combine it with the local name to make a qualified name to be used in the query.</span></span>  
  
 <span data-ttu-id="e796b-105">Uno de los problemas más habituales al consultar árboles XML es que si el árbol XML tiene un espacio de nombres predeterminado, el desarrollador a veces escribe la consulta como si el código XML no estuviera en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e796b-105">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="e796b-106">El primer conjunto de ejemplos de este tema muestra una forma habitual de cargar XML en un espacio de nombres predeterminado con una consulta incorrecta.</span><span class="sxs-lookup"><span data-stu-id="e796b-106">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, but is queried improperly.</span></span>  
  
 <span data-ttu-id="e796b-107">El segundo conjunto de ejemplos muestra las correcciones necesarias para que pueda consultar el código XML en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e796b-107">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e796b-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e796b-108">Example</span></span>  
 <span data-ttu-id="e796b-109">En este ejemplo se muestra la creación de XML en un espacio de nombres y una consulta que devuelve un conjunto de resultados vacío.</span><span class="sxs-lookup"><span data-stu-id="e796b-109">This example shows the creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e796b-110">Código</span><span class="sxs-lookup"><span data-stu-id="e796b-110">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="e796b-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e796b-111">Comments</span></span>  
 <span data-ttu-id="e796b-112">Este ejemplo genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="e796b-112">This example produces the following result:</span></span>  
  
```console  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="e796b-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e796b-113">Example</span></span>  
 <span data-ttu-id="e796b-114">En este ejemplo se muestra la creación de XML en un espacio de nombres y una consulta que se codifica correctamente.</span><span class="sxs-lookup"><span data-stu-id="e796b-114">This example shows the creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="e796b-115">A diferencia del ejemplo de código incorrecto anterior, el enfoque correcto al usar Visual Basic es declarar e inicializar un espacio de nombres predeterminado global.</span><span class="sxs-lookup"><span data-stu-id="e796b-115">In contrast to the incorrectly coded example above, the correct approach when using Visual Basic is to declare and initialize a global default namespace.</span></span> <span data-ttu-id="e796b-116">Esto coloca todas las propiedades XML en el espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e796b-116">This places all XML properties in the default namespace.</span></span> <span data-ttu-id="e796b-117">No se requieren otras modificaciones en el ejemplo para que funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="e796b-117">No other modifications are required to the example to make it work properly.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e796b-118">Código</span><span class="sxs-lookup"><span data-stu-id="e796b-118">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="e796b-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e796b-119">Comments</span></span>  
 <span data-ttu-id="e796b-120">Este ejemplo genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="e796b-120">This example produces the following result:</span></span>  
  
```console  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="e796b-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e796b-121">See also</span></span>

- [<span data-ttu-id="e796b-122">Información general sobre espacios de nombres (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e796b-122">Namespaces Overview (LINQ to XML) (Visual Basic)</span></span>](namespaces-overview-linq-to-xml.md)
