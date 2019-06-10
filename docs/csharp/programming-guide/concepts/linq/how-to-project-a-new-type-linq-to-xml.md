---
title: Procedimiento para proyectar un tipo nuevo (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
ms.openlocfilehash: 70053a2457005f6751075b33e8e49851d7127446
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486583"
---
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a><span data-ttu-id="a9c46-102">Procedimiento para proyectar un tipo nuevo (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="a9c46-102">How to: Project a New Type (LINQ to XML) (C#)</span></span>
<span data-ttu-id="a9c46-103">Otros ejemplos de esta sección han mostrado consultados que devuelven resultados como <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> de `string` y <xref:System.Collections.Generic.IEnumerable%601> de `int`.</span><span class="sxs-lookup"><span data-stu-id="a9c46-103">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="a9c46-104">Se trata de tipos de resultados comunes, pero no son adecuados para cada caso.</span><span class="sxs-lookup"><span data-stu-id="a9c46-104">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="a9c46-105">En muchos casos querrá que sus consultas devuelvan un <xref:System.Collections.Generic.IEnumerable%601> de algún otro tipo.</span><span class="sxs-lookup"><span data-stu-id="a9c46-105">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9c46-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9c46-106">Example</span></span>  
 <span data-ttu-id="a9c46-107">En este ejemplo se muestra como crear instancias de objetos en la cláusula `select`.</span><span class="sxs-lookup"><span data-stu-id="a9c46-107">This example shows how to instantiate objects in the `select` clause.</span></span> <span data-ttu-id="a9c46-108">El código primero define una nueva clase con un constructor y después modifica la instrucción `select` para que la expresión sea una nueva instancia de la nueva clase.</span><span class="sxs-lookup"><span data-stu-id="a9c46-108">The code first defines a new class with a constructor, and then modifies the `select` statement so that the expression is a new instance of the new class.</span></span>  
  
 <span data-ttu-id="a9c46-109">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="a9c46-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
class NameQty {  
    public string name;  
    public int qty;  
    public NameQty(string n, int q)  
    {  
        name = n;  
        qty = q;  
    }  
};  
  
class Program {  
    public static void Main() {  
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
  
 <span data-ttu-id="a9c46-110">En este ejemplo se usa el método `M:System.Xml.Linq.XElement.Element` que se presentó en el tema [Cómo: Recuperar un único elemento secundario (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a9c46-110">This example uses the `M:System.Xml.Linq.XElement.Element` method that was introduced in the topic [How to: Retrieve a Single Child Element (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="a9c46-111">También utiliza conversiones para recuperar los valores de los elementos devueltos por el método `M:System.Xml.Linq.XElement.Element`.</span><span class="sxs-lookup"><span data-stu-id="a9c46-111">It also uses casts to retrieve the values of the elements that are returned by the `M:System.Xml.Linq.XElement.Element` method.</span></span>  
  
 <span data-ttu-id="a9c46-112">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="a9c46-112">This example produces the following output:</span></span>  
  
```  
Lawnmower:1  
Baby Monitor:2  
```  
  