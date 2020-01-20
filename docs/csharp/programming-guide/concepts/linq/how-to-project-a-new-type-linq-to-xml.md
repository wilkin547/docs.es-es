---
title: Procedimiento para proyectar un nuevo tipo (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
ms.openlocfilehash: 3a54677fa0fa2845dd635f89ddb7ed1c5c279e03
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345721"
---
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a><span data-ttu-id="bcfb9-102">Procedimiento para proyectar un nuevo tipo (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="bcfb9-102">How to project a new type (LINQ to XML) (C#)</span></span>

<span data-ttu-id="bcfb9-103">Otros ejemplos de esta sección han mostrado consultados que devuelven resultados como <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> de `string` y <xref:System.Collections.Generic.IEnumerable%601> de `int`.</span><span class="sxs-lookup"><span data-stu-id="bcfb9-103">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="bcfb9-104">Se trata de tipos de resultados comunes, pero no son adecuados para cada caso.</span><span class="sxs-lookup"><span data-stu-id="bcfb9-104">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="bcfb9-105">En muchos casos querrá que sus consultas devuelvan un <xref:System.Collections.Generic.IEnumerable%601> de algún otro tipo.</span><span class="sxs-lookup"><span data-stu-id="bcfb9-105">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>

## <a name="example"></a><span data-ttu-id="bcfb9-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bcfb9-106">Example</span></span>

<span data-ttu-id="bcfb9-107">En este ejemplo se muestra como crear instancias de objetos en la cláusula `select`.</span><span class="sxs-lookup"><span data-stu-id="bcfb9-107">This example shows how to instantiate objects in the `select` clause.</span></span> <span data-ttu-id="bcfb9-108">El código primero define una nueva clase con un constructor y después modifica la instrucción `select` para que la expresión sea una nueva instancia de la nueva clase.</span><span class="sxs-lookup"><span data-stu-id="bcfb9-108">The code first defines a new class with a constructor, and then modifies the `select` statement so that the expression is a new instance of the new class.</span></span>

<span data-ttu-id="bcfb9-109">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="bcfb9-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>

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

<span data-ttu-id="bcfb9-110">En este ejemplo se usa el método <xref:System.Xml.Linq.XContainer.Element%2A> que se introdujo en el tema [Procedimiento para recuperar un único elemento secundario (LINQ to XML) (C#)](how-to-retrieve-a-single-child-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="bcfb9-110">This example uses the <xref:System.Xml.Linq.XContainer.Element%2A> method that was introduced in the topic [How to retrieve a single child element (LINQ to XML) (C#)](how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="bcfb9-111">También utiliza conversiones para recuperar los valores de los elementos devueltos por el método <xref:System.Xml.Linq.XContainer.Element%2A>.</span><span class="sxs-lookup"><span data-stu-id="bcfb9-111">It also uses casts to retrieve the values of the elements that are returned by the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span>  

<span data-ttu-id="bcfb9-112">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="bcfb9-112">This example produces the following output:</span></span>

```output
Lawnmower:1
Baby Monitor:2
```
