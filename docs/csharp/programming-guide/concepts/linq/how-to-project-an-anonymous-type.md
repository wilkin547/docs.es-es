---
title: Procedimiento para proyectar un tipo anónimo (C#)
ms.date: 07/20/2015
ms.assetid: 5cb9be13-5ac4-4373-a034-b3520a5b2dec
ms.openlocfilehash: 7797c8bfb12943af1ce7f975b170bf002aa7d6fc
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345733"
---
# <a name="how-to-project-an-anonymous-type-c"></a>Procedimiento para proyectar un tipo anónimo (C#)
En algunos casos quizás desee proyectar una consulta a un nuevo tipo, aunque sepa que solo utilizará este tipo durante un breve período. Crear un nuevo tipo solamente para usarlo en la proyección conlleva mucho trabajo adicional. En este caso un enfoque más eficiente consiste en proyectar en un tipo anónimo. Los tipos anónimos permiten definir una clase y, a continuación, declarar e inicializar un objeto de esa clase, sin dar un nombre a la clase.  
  
 Los tipos anónimos son la implementación de C# del concepto matemático de *tupla*. El término matemático tupla se originó de la secuencia único, doble, triple, cuádruple, quíntuple, n-tuple. Se refiere a una secuencia finita de objetos, cada uno de un tipo específico. A veces se denomina una lista de pares nombre/valor. Por ejemplo, el contenido de una dirección en el documento XML [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md) se puede expresar de esta forma:  
  
```text  
Name: Ellen Adams  
Street: 123 Maple Street  
City: Mill Valley  
State: CA  
Zip: 90952  
Country: USA  
```  
  
 Cuando se crea una instancia de un tipo anónimo, resulta práctico pensar en ella como si se creara una tupla de orden n. Si escribe una consulta que crea una tupla en la cláusula `select`, la consulta devuelve un `IEnumerable` de la tupla.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, la cláusula `select` proyecta un tipo anónimo. A continuación, el ejemplo utiliza `var` para crear el objeto `IEnumerable`. En el bucle `foreach`, la variable de iteración se convierte en una instancia del tipo anónimo creado en la expresión de consulta.  
  
 Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Clientes y pedidos (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).  
  
```csharp  
XElement custOrd = XElement.Load("CustomersOrders.xml");  
var custList =  
    from el in custOrd.Element("Customers").Elements("Customer")  
    select new {  
        CustomerID = (string)el.Attribute("CustomerID"),  
        CompanyName = (string)el.Element("CompanyName"),  
        ContactName = (string)el.Element("ContactName")  
    };  
foreach (var cust in custList)  
    Console.WriteLine("{0}:{1}:{2}", cust.CustomerID, cust.CompanyName, cust.ContactName);  
```  
  
 Este código genera el siguiente resultado:  
  
```output  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  