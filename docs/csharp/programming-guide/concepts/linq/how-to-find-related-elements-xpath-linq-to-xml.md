---
title: Procedimiento para buscar elementos relacionados (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 41b386ee-562d-4841-bd6b-e44a7eb69f26
ms.openlocfilehash: a4260012899527662638a037fa4616a7a0d6f875
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486743"
---
# <a name="how-to-find-related-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="e58ea-102">Procedimiento para buscar elementos relacionados (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="e58ea-102">How to: Find Related Elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="e58ea-103">Este tema muestra cómo obtener un elemento seleccionando en un atributo al que hace referencia el valor de otro elemento.</span><span class="sxs-lookup"><span data-stu-id="e58ea-103">This topic shows how to get an element selecting on an attribute that is referred to by the value of another element.</span></span>  
  
 <span data-ttu-id="e58ea-104">La expresión XPath es:</span><span class="sxs-lookup"><span data-stu-id="e58ea-104">The XPath expression is:</span></span>  
  
 `.//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]`  
  
## <a name="example"></a><span data-ttu-id="e58ea-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e58ea-105">Example</span></span>  
 <span data-ttu-id="e58ea-106">Este ejemplo encuentra el duodécimo (12) elemento `Order`, y después encuentra el cliente de dicho pedido.</span><span class="sxs-lookup"><span data-stu-id="e58ea-106">This example finds the 12th `Order` element, and then finds the customer for that order.</span></span>  
  
 <span data-ttu-id="e58ea-107">Tenga en cuenta que la indización en una lista de .NET se basa en "cero".</span><span class="sxs-lookup"><span data-stu-id="e58ea-107">Note that indexing into a list in .NET is 'zero' based.</span></span> <span data-ttu-id="e58ea-108">Sin embargo, la indización en una colección de nodos de un predicado XPath se basa en "uno".</span><span class="sxs-lookup"><span data-stu-id="e58ea-108">Indexing into a collection of nodes in an XPath predicate is 'one' based.</span></span> <span data-ttu-id="e58ea-109">Este ejemplo refleja esta diferencia.</span><span class="sxs-lookup"><span data-stu-id="e58ea-109">This example reflects this difference.</span></span>  
  
 <span data-ttu-id="e58ea-110">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Clientes y pedidos (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="e58ea-110">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
XDocument co = XDocument.Load("CustomersOrders.xml");  
  
// LINQ to XML query  
XElement customer1 =  
    (from el in co.Descendants("Customer")  
     where (string)el.Attribute("CustomerID") ==  
          (string)(co  
              .Element("Root")  
              .Element("Orders")  
              .Elements("Order")  
              .ToList()[11]  
              .Element("CustomerID"))  
    select el)  
    .First();  
  
// An alternate way to write the query that avoids creation  
// of a System.Collections.Generic.List:  
XElement customer2 =  
    (from el in co.Descendants("Customer")  
     where (string)el.Attribute("CustomerID") ==  
          (string)(co  
              .Element("Root")  
              .Element("Orders")  
              .Elements("Order")  
              .Skip(11).First()  
              .Element("CustomerID"))  
    select el)  
    .First();  
  
// XPath expression  
XElement customer3 = co.XPathSelectElement(  
  ".//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]");  
  
if (customer1 == customer2 && customer1 == customer3)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(customer1);  
```  
  
 <span data-ttu-id="e58ea-111">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="e58ea-111">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Customer CustomerID="HUNGC">  
  <CompanyName>Hungry Coyote Import Store</CompanyName>  
  <ContactName>Yoshi Latimer</ContactName>  
  <ContactTitle>Sales Representative</ContactTitle>  
  <Phone>(503) 555-6874</Phone>  
  <Fax>(503) 555-2376</Fax>  
  <FullAddress>  
    <Address>City Center Plaza 516 Main St.</Address>  
    <City>Elgin</City>  
    <Region>OR</Region>  
    <PostalCode>97827</PostalCode>  
    <Country>USA</Country>  
  </FullAddress>  
</Customer>  
```  
 