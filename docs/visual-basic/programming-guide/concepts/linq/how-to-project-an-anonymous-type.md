---
title: Procedimiento para proyectar un tipo anónimo
ms.date: 07/20/2015
ms.assetid: 30b42987-0e0e-4b2b-adb1-5255ddfbcd7b
ms.openlocfilehash: c486fbd7ee8ae917cd0ccf57e2b04e472784b11d
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88810565"
---
# <a name="how-to-project-an-anonymous-type-visual-basic"></a><span data-ttu-id="aeb0d-102">Cómo: proyectar un tipo anónimo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aeb0d-102">How to: Project an Anonymous Type (Visual Basic)</span></span>
<span data-ttu-id="aeb0d-103">En algunos casos quizás desee proyectar una consulta a un nuevo tipo, aunque sepa que solo utilizará este tipo durante un breve período.</span><span class="sxs-lookup"><span data-stu-id="aeb0d-103">In some cases you might want to project a query to a new type, even though you know you will only use this type for a short while.</span></span> <span data-ttu-id="aeb0d-104">Crear un nuevo tipo solamente para usarlo en la proyección conlleva mucho trabajo adicional.</span><span class="sxs-lookup"><span data-stu-id="aeb0d-104">It is a lot of extra work to create a new type just to use in the projection.</span></span> <span data-ttu-id="aeb0d-105">En este caso un enfoque más eficiente consiste en proyectar en un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="aeb0d-105">A more efficient approach in this case is to project to an anonymous type.</span></span> <span data-ttu-id="aeb0d-106">Los tipos anónimos permiten definir una clase y, a continuación, declarar e inicializar un objeto de esa clase, sin dar un nombre a la clase.</span><span class="sxs-lookup"><span data-stu-id="aeb0d-106">Anonymous types allow you to define a class, then declare and initialize an object of that class, without giving the class a name.</span></span>  
  
 <span data-ttu-id="aeb0d-107">Los tipos anónimos son la implementación de C# del concepto matemático de *tupla*.</span><span class="sxs-lookup"><span data-stu-id="aeb0d-107">Anonymous types are the C# implementation of the mathematical concept of a *tuple*.</span></span> <span data-ttu-id="aeb0d-108">El término matemático tupla se originó de la secuencia único, doble, triple, cuádruple, quíntuple, n-tuple.</span><span class="sxs-lookup"><span data-stu-id="aeb0d-108">The mathematical term tuple originated from the sequence single, double, triple, quadruple, quintuple, n-tuple.</span></span> <span data-ttu-id="aeb0d-109">Se refiere a una secuencia finita de objetos, cada uno de un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="aeb0d-109">It refers to a finite sequence of objects, each of a specific type.</span></span> <span data-ttu-id="aeb0d-110">A veces se denomina una lista de pares nombre/valor.</span><span class="sxs-lookup"><span data-stu-id="aeb0d-110">Sometimes this is called a list of name/value pairs.</span></span> <span data-ttu-id="aeb0d-111">Por ejemplo, el contenido de una dirección en el documento XML [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md) se podría expresar de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="aeb0d-111">For example, the contents of an address in the [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md) XML document could be expressed as follows:</span></span>  
  
```
Name: Ellen Adams  
Street: 123 Maple Street  
City: Mill Valley  
State: CA  
Zip: 90952  
Country: USA  
```  
  
 <span data-ttu-id="aeb0d-112">Cuando se crea una instancia de un tipo anónimo, resulta práctico pensar en ella como si se creara una tupla de orden n.</span><span class="sxs-lookup"><span data-stu-id="aeb0d-112">When you create an instance of an anonymous type, it is convenient to think of it as creating a tuple of order n.</span></span> <span data-ttu-id="aeb0d-113">Si escribe una consulta que crea una tupla en la cláusula `Select`, la consulta devuelve un `IEnumerable` de la tupla.</span><span class="sxs-lookup"><span data-stu-id="aeb0d-113">If you write a query that creates a tuple in the `Select` clause, the query returns an `IEnumerable` of the tuple.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aeb0d-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aeb0d-114">Example</span></span>  
 <span data-ttu-id="aeb0d-115">En este ejemplo, la cláusula `Select` proyecta un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="aeb0d-115">In this example, the `Select` clause projects an anonymous type.</span></span> <span data-ttu-id="aeb0d-116">A continuación, el ejemplo utiliza `Dim` para crear el objeto `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="aeb0d-116">The example then uses `Dim` to create the `IEnumerable` object.</span></span> <span data-ttu-id="aeb0d-117">En el bucle `For Each`, la variable de iteración se convierte en una instancia del tipo anónimo creado en la expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="aeb0d-117">Within the `For Each` loop, the iteration variable becomes an instance of the anonymous type created in the query expression.</span></span>  
  
 <span data-ttu-id="aeb0d-118">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Clientes y pedidos (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="aeb0d-118">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim custOrd As XElement = XElement.Load("CustomersOrders.xml")  
Dim custList = _  
    From el In custOrd.<Customers>.<Customer> _  
    Select New With { _  
        .CustomerID = el.@<CustomerID>, _  
        .CompanyName = el.<CompanyName>.Value, _  
        .ContactName = el.<ContactName>.Value _  
    }  
For Each cust In custList  
    Console.WriteLine("{0}:{1}:{2}", cust.CustomerID, cust.CompanyName, cust.ContactName)  
Next  
```  
  
 <span data-ttu-id="aeb0d-119">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="aeb0d-119">This code produces the following output:</span></span>  
  
```console  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  
## <a name="see-also"></a><span data-ttu-id="aeb0d-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aeb0d-120">See also</span></span>

- [<span data-ttu-id="aeb0d-121">Proyecciones y transformaciones (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aeb0d-121">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](projections-and-transformations-linq-to-xml.md)
