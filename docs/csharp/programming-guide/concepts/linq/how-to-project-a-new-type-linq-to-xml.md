---
title: Procedimiento para proyectar un nuevo tipo (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
ms.openlocfilehash: 5205a0c56651271dea0181ed96518c0e9d7f95f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168998"
---
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a>Procedimiento para proyectar un nuevo tipo (LINQ to XML) (C#)

Otros ejemplos de esta sección han mostrado consultados que devuelven resultados como <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> de `string` y <xref:System.Collections.Generic.IEnumerable%601> de `int`. Se trata de tipos de resultados comunes, pero no son adecuados para cada caso. En muchos casos querrá que sus consultas devuelvan un <xref:System.Collections.Generic.IEnumerable%601> de algún otro tipo.

## <a name="example"></a>Ejemplo

En este ejemplo se muestra como crear instancias de objetos en la cláusula `select`. El código primero define una nueva clase con un constructor y después modifica la instrucción `select` para que la expresión sea una nueva instancia de la nueva clase.

En este ejemplo se usa el siguiente documento XML: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md) (Archivo XML de ejemplo: pedido de compra común [LINQ to XML]).

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

En este ejemplo se usa el método <xref:System.Xml.Linq.XContainer.Element%2A> que se introdujo en el tema [Procedimiento para recuperar un único elemento secundario (LINQ to XML) (C#)](how-to-retrieve-a-single-child-element-linq-to-xml.md). También utiliza conversiones para recuperar los valores de los elementos devueltos por el método <xref:System.Xml.Linq.XContainer.Element%2A>.  

Este ejemplo produce el siguiente resultado:

```output
Lawnmower:1
Baby Monitor:2
```
