---
title: Procedimiento para proyectar un nuevo tipo (LINQ to XML) (C#)
description: Aprenda a crear consultas en LINQ to XML en C# que devuelvan un elemento IEnumerable<T> de tipos más allá de XElement, string o int, que se describen en otros ejemplos.
ms.date: 07/20/2015
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
ms.openlocfilehash: 013ea852a64b77c04ac583b4d9b71e8006cd4976
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104643"
---
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a><span data-ttu-id="f1079-103">Procedimiento para proyectar un nuevo tipo (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="f1079-103">How to project a new type (LINQ to XML) (C#)</span></span>

<span data-ttu-id="f1079-104">Otros ejemplos de esta sección han mostrado consultados que devuelven resultados como <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> de `string` y <xref:System.Collections.Generic.IEnumerable%601> de `int`.</span><span class="sxs-lookup"><span data-stu-id="f1079-104">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="f1079-105">Se trata de tipos de resultados comunes, pero no son adecuados para cada caso.</span><span class="sxs-lookup"><span data-stu-id="f1079-105">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="f1079-106">En muchos casos querrá que sus consultas devuelvan un <xref:System.Collections.Generic.IEnumerable%601> de algún otro tipo.</span><span class="sxs-lookup"><span data-stu-id="f1079-106">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>

## <a name="example"></a><span data-ttu-id="f1079-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f1079-107">Example</span></span>

<span data-ttu-id="f1079-108">En este ejemplo se muestra como crear instancias de objetos en la cláusula `select`.</span><span class="sxs-lookup"><span data-stu-id="f1079-108">This example shows how to instantiate objects in the `select` clause.</span></span> <span data-ttu-id="f1079-109">El código primero define una nueva clase con un constructor y después modifica la instrucción `select` para que la expresión sea una nueva instancia de la nueva clase.</span><span class="sxs-lookup"><span data-stu-id="f1079-109">The code first defines a new class with a constructor, and then modifies the `select` statement so that the expression is a new instance of the new class.</span></span>

<span data-ttu-id="f1079-110">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="f1079-110">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>

```csharp
class NameQty
{
    public string name;
    public int qty;
    public NameQty(string n, int q)
    {
        name = n;
        qty = q;
    }
};

class Program {
    public static void Main()
    {
        XElement po = XElement.Load("PurchaseOrder.xml");
  
        IEnumerable<NameQty> nqList =
            from n in po.Descendants("Item")
            select new NameQty(
                    (string)n.Element("ProductName"),
                    (int)n.Element("Quantity")
                );
  
        foreach (NameQty n in nqList)
            Console.WriteLine(n.name + ":" + n.qty);
    }
}
```

<span data-ttu-id="f1079-111">En este ejemplo se usa el método <xref:System.Xml.Linq.XContainer.Element%2A> que se introdujo en el tema [Procedimiento para recuperar un único elemento secundario (LINQ to XML) (C#)](how-to-retrieve-a-single-child-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f1079-111">This example uses the <xref:System.Xml.Linq.XContainer.Element%2A> method that was introduced in the topic [How to retrieve a single child element (LINQ to XML) (C#)](how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="f1079-112">También utiliza conversiones para recuperar los valores de los elementos devueltos por el método <xref:System.Xml.Linq.XContainer.Element%2A>.</span><span class="sxs-lookup"><span data-stu-id="f1079-112">It also uses casts to retrieve the values of the elements that are returned by the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span>  

<span data-ttu-id="f1079-113">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="f1079-113">This example produces the following output:</span></span>

```output
Lawnmower:1
Baby Monitor:2
```
