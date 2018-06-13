---
title: Realizar una unión usando claves compuestas
description: Cómo realizar una unión usando claves compuestas.
ms.date: 12/1/2016
ms.assetid: da70b54d-3213-45eb-8437-fbe75cbcf935
ms.openlocfilehash: e40f4d147886c07913c761bb5df83ee34d23eaba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33271219"
---
# <a name="join-by-using-composite-keys"></a><span data-ttu-id="261a5-103">Realizar una unión usando claves compuestas</span><span class="sxs-lookup"><span data-stu-id="261a5-103">Join by using composite keys</span></span>

<span data-ttu-id="261a5-104">En este ejemplo se muestra cómo realizar operaciones de combinación en las que se quiere usar más de una clave para definir a una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="261a5-104">This example shows how to perform join operations in which you want to use more than one key to define a match.</span></span> <span data-ttu-id="261a5-105">Esto se logra mediante una clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="261a5-105">This is accomplished by using a composite key.</span></span> <span data-ttu-id="261a5-106">Una clave compuesta se crea como un tipo anónimo o un nombre con tipo con los valores que se quieren comparar.</span><span class="sxs-lookup"><span data-stu-id="261a5-106">You create a composite key as an anonymous type or named typed with the values that you want to compare.</span></span> <span data-ttu-id="261a5-107">Si la variable de consulta se pasará a través de límites de método, use un tipo con nombre que invalida <xref:System.Object.Equals%2A> y <xref:System.Object.GetHashCode%2A> para la clave.</span><span class="sxs-lookup"><span data-stu-id="261a5-107">If the query variable will be passed across method boundaries, use a named type that overrides <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> for the key.</span></span> <span data-ttu-id="261a5-108">Los nombres de las propiedades y el orden en que aparecen deben ser idénticos en cada clave.</span><span class="sxs-lookup"><span data-stu-id="261a5-108">The names of the properties, and the order in which they occur, must be identical in each key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="261a5-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="261a5-109">Example</span></span>  
 <span data-ttu-id="261a5-110">En el ejemplo siguiente se muestra cómo usar una clave compuesta para combinar datos de tres tablas:</span><span class="sxs-lookup"><span data-stu-id="261a5-110">The following example demonstrates how to use a composite key to join data from three tables:</span></span>  
  
```csharp  
var query = from o in db.Orders  
    from p in db.Products  
    join d in db.OrderDetails   
        on new {o.OrderID, p.ProductID} equals new {d.OrderID,        d.ProductID} into details  
        from d in details  
        select new {o.OrderID, p.ProductID, d.UnitPrice};  
```  
  
 <span data-ttu-id="261a5-111">La inferencia de tipos en las claves compuestas depende de los nombres de las propiedades de las claves y el orden en que aparecen.</span><span class="sxs-lookup"><span data-stu-id="261a5-111">Type inference on composite keys depends on the names of the properties in the keys, and the order in which they occur.</span></span> <span data-ttu-id="261a5-112">Si las propiedades de las secuencias de origen no tienen los mismos nombres, deberá asignar nuevos nombres en las claves.</span><span class="sxs-lookup"><span data-stu-id="261a5-112">If the properties in the source sequences do not have the same names, you must assign new names in the keys.</span></span> <span data-ttu-id="261a5-113">Por ejemplo, si la tabla `Orders` y la tabla `OrderDetails` usan nombres diferentes para las columnas, se podrían crear claves compuestas asignando nombres idénticos a los tipos anónimos:</span><span class="sxs-lookup"><span data-stu-id="261a5-113">For example, if the `Orders` table and `OrderDetails` table each used different names for their columns, you could create composite keys by assigning identical names in the anonymous types:</span></span>  
  
```csharp  
join...on new {Name = o.CustomerName, ID = o.CustID} equals   
    new {Name = d.CustName, ID = d.CustID }  
```  
  
 <span data-ttu-id="261a5-114">Las claves compuestas también se pueden usar en una cláusula `group`.</span><span class="sxs-lookup"><span data-stu-id="261a5-114">Composite keys can be also used in a `group` clause.</span></span>  

## <a name="see-also"></a><span data-ttu-id="261a5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="261a5-115">See also</span></span>  
 [<span data-ttu-id="261a5-116">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="261a5-116">LINQ query expressions</span></span>](index.md)  
 [<span data-ttu-id="261a5-117">join (cláusula)</span><span class="sxs-lookup"><span data-stu-id="261a5-117">join clause</span></span>](../language-reference/keywords/join-clause.md)  
 [<span data-ttu-id="261a5-118">group (cláusula)</span><span class="sxs-lookup"><span data-stu-id="261a5-118">group clause</span></span>](../language-reference/keywords/group-clause.md)
