---
title: 'Cómo: Escribir consultas con filtrado complejo (C#)'
ms.date: 07/20/2015
ms.assetid: 4065d901-cf89-4e47-8bf9-abb65acfb003
ms.openlocfilehash: 72c34f8ef8bebb3584e00cf040cfcdc35dfc3701
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-write-queries-with-complex-filtering-c"></a>Cómo: Escribir consultas con filtrado complejo (C#)
Es posible que desee escribir consultas LINQ to XML con filtros complejos. Por ejemplo, quizás debe buscar todos los elementos que tienen un elemento secundario con un valor y un nombre específicos. En este tema se proporciona un ejemplo de escritura de una consulta con un filtrado complejo.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo buscar todos los elementos `PurchaseOrder` que tienen un elemento `Address` secundario que tiene un atributo `Type` igual a "Shipping" (envío) y un elemento `State` secundario igual a "NY". Utiliza una consulta anidada en la cláusula `Where` y el operador `Any` devuelve `true` si la colección tiene elementos en ella. Para obtener información sobre cómo usar la sintaxis de consultas basadas en métodos, vea [Query Syntax and Method Syntax in LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md) (Sintaxis de consultas y sintaxis de métodos en LINQ).  
  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
 Para obtener más información sobre el operador `Any`, vea [Quantifier Operations (C#)](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md) (Operaciones cuantificadoras (C#)).  
  
```csharp  
XElement root = XElement.Load("PurchaseOrders.xml");  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements("PurchaseOrder")  
    where   
        (from add in el.Elements("Address")  
        where  
            (string)add.Attribute("Type") == "Shipping" &&  
            (string)add.Element("State") == "NY"  
        select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute("PurchaseOrderNumber"));  
```  
  
 Este código genera el siguiente resultado:  
  
```  
99505  
```  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres. Para obtener más información, vea [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md) (Trabajar con espacios de nombres XML [C#]).  
  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra en un espacio de nombres](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).  
  
```csharp  
XElement root = XElement.Load("PurchaseOrdersInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements(aw + "PurchaseOrder")  
    where  
        (from add in el.Elements(aw + "Address")  
         where  
             (string)add.Attribute(aw + "Type") == "Shipping" &&  
             (string)add.Element(aw + "State") == "NY"  
         select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute(aw + "PurchaseOrderNumber"));  
```  
  
 Este código genera el siguiente resultado:  
  
```  
99505  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XElement.Attribute%2A>  
 <xref:System.Xml.Linq.XContainer.Elements%2A>  
 [Consultas básicas (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
 [Projection Operations (C#)](../../../../csharp/programming-guide/concepts/linq/projection-operations.md) (Operaciones de proyección [C#])  
 [Quantifier Operations (C#)](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md) (Operaciones cuantificadoras (C#))
