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
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a>Procedimiento para proyectar un nuevo tipo (LINQ to XML) (C#)

Otros ejemplos de esta sección han mostrado consultados que devuelven resultados como <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> de `string` y <xref:System.Collections.Generic.IEnumerable%601> de `int`. Se trata de tipos de resultados comunes, pero no son adecuados para cada caso. En muchos casos querrá que sus consultas devuelvan un <xref:System.Collections.Generic.IEnumerable%601> de algún otro tipo.

## <a name="example"></a>Ejemplo

En este ejemplo se muestra como crear instancias de objetos en la cláusula `select`. El código primero define una nueva clase con un constructor y después modifica la instrucción `select` para que la expresión sea una nueva instancia de la nueva clase.

Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).

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
