---
title: Realizar una combinación mediante claves compuestas (LINQ en C#)
description: Obtenga información sobre como cómo realizar una combinación mediante claves compuestas en LINQ.
ms.date: 12/01/2016
ms.assetid: da70b54d-3213-45eb-8437-fbe75cbcf935
ms.openlocfilehash: 460a52da7e0c0a47b77d4c64e76641bae9da7cd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659883"
---
# <a name="join-by-using-composite-keys"></a><span data-ttu-id="37c5f-103">Realizar una unión usando claves compuestas</span><span class="sxs-lookup"><span data-stu-id="37c5f-103">Join by using composite keys</span></span>

<span data-ttu-id="37c5f-104">En este ejemplo se muestra cómo realizar operaciones de combinación en las que se quiere usar más de una clave para definir a una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="37c5f-104">This example shows how to perform join operations in which you want to use more than one key to define a match.</span></span> <span data-ttu-id="37c5f-105">Esto se logra mediante una clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="37c5f-105">This is accomplished by using a composite key.</span></span> <span data-ttu-id="37c5f-106">Una clave compuesta se crea como un tipo anónimo o un nombre con tipo con los valores que se quieren comparar.</span><span class="sxs-lookup"><span data-stu-id="37c5f-106">You create a composite key as an anonymous type or named typed with the values that you want to compare.</span></span> <span data-ttu-id="37c5f-107">Si la variable de consulta se pasará a través de límites de método, use un tipo con nombre que invalida <xref:System.Object.Equals%2A> y <xref:System.Object.GetHashCode%2A> para la clave.</span><span class="sxs-lookup"><span data-stu-id="37c5f-107">If the query variable will be passed across method boundaries, use a named type that overrides <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> for the key.</span></span> <span data-ttu-id="37c5f-108">Los nombres de las propiedades y el orden en que aparecen deben ser idénticos en cada clave.</span><span class="sxs-lookup"><span data-stu-id="37c5f-108">The names of the properties, and the order in which they occur, must be identical in each key.</span></span>

## <a name="example"></a><span data-ttu-id="37c5f-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37c5f-109">Example</span></span>

<span data-ttu-id="37c5f-110">En el ejemplo siguiente se muestra cómo usar una clave compuesta para combinar datos de tres tablas:</span><span class="sxs-lookup"><span data-stu-id="37c5f-110">The following example demonstrates how to use a composite key to join data from three tables:</span></span>

```csharp
var query = from o in db.Orders
    from p in db.Products
    join d in db.OrderDetails
        on new {o.OrderID, p.ProductID} equals new {d.OrderID, d.ProductID} into details
        from d in details
        select new {o.OrderID, p.ProductID, d.UnitPrice};
```

<span data-ttu-id="37c5f-111">La inferencia de tipos en las claves compuestas depende de los nombres de las propiedades de las claves y el orden en que aparecen.</span><span class="sxs-lookup"><span data-stu-id="37c5f-111">Type inference on composite keys depends on the names of the properties in the keys, and the order in which they occur.</span></span> <span data-ttu-id="37c5f-112">Si las propiedades de las secuencias de origen no tienen los mismos nombres, deberá asignar nombres nuevos en las claves.</span><span class="sxs-lookup"><span data-stu-id="37c5f-112">If the properties in the source sequences don't have the same names, you must assign new names in the keys.</span></span> <span data-ttu-id="37c5f-113">Por ejemplo, si la tabla `Orders` y la tabla `OrderDetails` usan nombres diferentes para las columnas, se podrían crear claves compuestas asignando nombres idénticos a los tipos anónimos:</span><span class="sxs-lookup"><span data-stu-id="37c5f-113">For example, if the `Orders` table and `OrderDetails` table each used different names for their columns, you could create composite keys by assigning identical names in the anonymous types:</span></span>

```csharp
join...on new {Name = o.CustomerName, ID = o.CustID} equals
    new {Name = d.CustName, ID = d.CustID }
```

<span data-ttu-id="37c5f-114">Las claves compuestas también se pueden usar en una cláusula `group`.</span><span class="sxs-lookup"><span data-stu-id="37c5f-114">Composite keys can be also used in a `group` clause.</span></span>

## <a name="see-also"></a><span data-ttu-id="37c5f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="37c5f-115">See also</span></span>

- [<span data-ttu-id="37c5f-116">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="37c5f-116">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="37c5f-117">join (cláusula)</span><span class="sxs-lookup"><span data-stu-id="37c5f-117">join clause</span></span>](../language-reference/keywords/join-clause.md)
- [<span data-ttu-id="37c5f-118">group (cláusula)</span><span class="sxs-lookup"><span data-stu-id="37c5f-118">group clause</span></span>](../language-reference/keywords/group-clause.md)
