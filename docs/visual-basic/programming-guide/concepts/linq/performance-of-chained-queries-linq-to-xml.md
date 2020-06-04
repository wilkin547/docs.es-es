---
title: Rendimiento de consultas encadenadas (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 589f2adc-69f9-404d-b9d6-4c28dabea7f7
ms.openlocfilehash: 6b87f2744f663ebd45dceb036dcaac71b80765fc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396394"
---
# <a name="performance-of-chained-queries-linq-to-xml-visual-basic"></a><span data-ttu-id="0eb58-102">Rendimiento de consultas encadenadas (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0eb58-102">Performance of Chained Queries (LINQ to XML) (Visual Basic)</span></span>

<span data-ttu-id="0eb58-103">Una de las ventajas más importantes de LINQ (y LINQ to XML) es que las consultas encadenadas funcionan igual de bien que una sola consulta más grande y complicada.</span><span class="sxs-lookup"><span data-stu-id="0eb58-103">One of the most important benefits of LINQ (and LINQ to XML) is that chained queries can perform as well as a single larger, more complicated query.</span></span>

<span data-ttu-id="0eb58-104">Una consulta encadenada es una consulta que usa otra consulta como su origen.</span><span class="sxs-lookup"><span data-stu-id="0eb58-104">A chained query is a query that uses another query as its source.</span></span> <span data-ttu-id="0eb58-105">Por ejemplo, en el siguiente código simple, `query2` es el origen de `query1`:</span><span class="sxs-lookup"><span data-stu-id="0eb58-105">For example, in the following simple code, `query2` has `query1` as its source:</span></span>

```vb
Dim root As New XElement("Root", New XElement("Child", 1), New XElement("Child", 2), New XElement("Child", 3), New XElement("Child", 4))

Dim query1 = From x In root.Elements("Child") Where CInt(x) >= 3x

Dim query2 = From e In query1 Where CInt(e) Mod 2 = 0e

For Each i As var In query2
    Console.WriteLine("{0}", CInt(i))
Next
```

<span data-ttu-id="0eb58-106">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0eb58-106">This example produces the following output:</span></span>

```console
4
```

<span data-ttu-id="0eb58-107">Esta consulta encadenada proporciona el mismo perfil de rendimiento que si se recorriese en iteración una lista vinculada.</span><span class="sxs-lookup"><span data-stu-id="0eb58-107">This chained query provides the same performance profile as iterating through a linked list.</span></span>

- <span data-ttu-id="0eb58-108">El eje <xref:System.Xml.Linq.XContainer.Elements%2A> tiene básicamente el mismo rendimiento que si se recorriese en iteración una lista vinculada.</span><span class="sxs-lookup"><span data-stu-id="0eb58-108">The <xref:System.Xml.Linq.XContainer.Elements%2A> axis has essentially the same performance as iterating through a linked list.</span></span> <span data-ttu-id="0eb58-109"><xref:System.Xml.Linq.XContainer.Elements%2A> se implementa como iterador con ejecución aplazada.</span><span class="sxs-lookup"><span data-stu-id="0eb58-109"><xref:System.Xml.Linq.XContainer.Elements%2A> is implemented as an iterator with deferred execution.</span></span> <span data-ttu-id="0eb58-110">Es decir, realiza trabajo adicional además de recorrer en iteración la lista vinculada, como asignar el objeto iterador y mantener el seguimiento del estado de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="0eb58-110">This means that it does some work in addition to iterating through the linked list, such as allocating the iterator object and keeping track of execution state.</span></span> <span data-ttu-id="0eb58-111">Este trabajo se puede dividir en dos categorías: el trabajo que se realiza cuando se configura el iterador y el que se lleva a cabo durante cada iteración.</span><span class="sxs-lookup"><span data-stu-id="0eb58-111">This work can be divided into two categories: the work that is done at the time the iterator is set up, and the work that is done during each iteration.</span></span> <span data-ttu-id="0eb58-112">El trabajo de configuración es un trabajo mínimo y fijo, mientras que el realizado durante cada iteración es proporcional al número de elementos de la colección de origen.</span><span class="sxs-lookup"><span data-stu-id="0eb58-112">The setup work is a small, fixed amount of work and the work done during each iteration is proportional to the number of items in the source collection.</span></span>

- <span data-ttu-id="0eb58-113">En `query1`, la cláusula `Where` provoca la llamada al método <xref:System.Linq.Enumerable.Where%2A> por parte de la consulta.</span><span class="sxs-lookup"><span data-stu-id="0eb58-113">In `query1`, the `Where` clause causes the query to call the <xref:System.Linq.Enumerable.Where%2A> method.</span></span> <span data-ttu-id="0eb58-114">Este método también se implementa como iterador.</span><span class="sxs-lookup"><span data-stu-id="0eb58-114">This method is also implemented as an iterator.</span></span> <span data-ttu-id="0eb58-115">El trabajo de configuración está formado por la creación de una instancia del delegado que hará referencia a la expresión lambda, más la configuración normal de un iterador.</span><span class="sxs-lookup"><span data-stu-id="0eb58-115">The setup work consists of instantiating the delegate that will reference the lambda expression, plus the normal setup for an iterator.</span></span> <span data-ttu-id="0eb58-116">Con cada iteración, se llama al delegado para que ejecute el predicado.</span><span class="sxs-lookup"><span data-stu-id="0eb58-116">With each iteration, the delegate is called to execute the predicate.</span></span> <span data-ttu-id="0eb58-117">El trabajo de configuración y el realizado durante cada iteración es parecido al llevado a cabo mientras se recorre en iteración el eje.</span><span class="sxs-lookup"><span data-stu-id="0eb58-117">The setup work and the work done during each iteration is the similar to the work done while iterating through the axis.</span></span>

- <span data-ttu-id="0eb58-118">En `query1`, la cláusula Select provoca la llamada al método <xref:System.Linq.Enumerable.Select%2A> por parte de la consulta.</span><span class="sxs-lookup"><span data-stu-id="0eb58-118">In `query1`, the select clause causes the query to call the <xref:System.Linq.Enumerable.Select%2A> method.</span></span> <span data-ttu-id="0eb58-119">Este método tiene el mismo perfil de rendimiento que el método <xref:System.Linq.Enumerable.Where%2A>.</span><span class="sxs-lookup"><span data-stu-id="0eb58-119">This method has the same performance profile as the <xref:System.Linq.Enumerable.Where%2A> method.</span></span>

- <span data-ttu-id="0eb58-120">En `query2`, tanto la cláusula `Where` como la cláusula `Select` tienen el mismo perfil de rendimiento que en `query1`.</span><span class="sxs-lookup"><span data-stu-id="0eb58-120">In `query2`, both the `Where` clause and the `Select` clause have the same performance profile as in `query1`.</span></span>

 <span data-ttu-id="0eb58-121">Por lo tanto, la iteración por `query2` es directamente proporcional al número de elementos del origen de la primera consulta, es decir, tiempo lineal.</span><span class="sxs-lookup"><span data-stu-id="0eb58-121">The iteration through `query2` is therefore directly proportional to the number of items in the source of the first query, in other words, linear time.</span></span>

## <a name="see-also"></a><span data-ttu-id="0eb58-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0eb58-122">See also</span></span>

- [<span data-ttu-id="0eb58-123">Rendimiento (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0eb58-123">Performance (LINQ to XML) (Visual Basic)</span></span>](performance-linq-to-xml.md)
