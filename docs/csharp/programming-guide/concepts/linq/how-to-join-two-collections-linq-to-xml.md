---
title: Procedimiento para combinar dos colecciones (LINQ to XML) (C#)
description: En este ejemplo de C# se combinan los elementos de LINQ to XML a otros elementos y se genera un nuevo documento XML.
ms.date: 07/20/2015
ms.assetid: 7b817ede-911a-4cff-9dd3-639c3fc228c9
ms.openlocfilehash: 10792ed4907e778b41821c9b32574bd8fc0ab35f
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104988"
---
# <a name="how-to-join-two-collections-linq-to-xml-c"></a><span data-ttu-id="b71ba-103">Procedimiento para combinar dos colecciones (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="b71ba-103">How to join two collections (LINQ to XML) (C#)</span></span>

<span data-ttu-id="b71ba-104">A veces, un elemento o atributo de un documento XML puede hacer referencia a otro elemento o atributo.</span><span class="sxs-lookup"><span data-stu-id="b71ba-104">An element or attribute in an XML document can sometimes refer to another element or attribute.</span></span> <span data-ttu-id="b71ba-105">Por ejemplo, el documento XML [Archivo XML de muestra: clientes y pedidos (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md) contiene una lista de clientes y una lista de pedidos.</span><span class="sxs-lookup"><span data-stu-id="b71ba-105">For example, the [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md) XML document contains a list of customers and a list of orders.</span></span> <span data-ttu-id="b71ba-106">Cada elemento `Customer` contiene un atributo `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="b71ba-106">Each `Customer` element contains a `CustomerID` attribute.</span></span> <span data-ttu-id="b71ba-107">Cada elemento `Order` contiene un elemento `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="b71ba-107">Each `Order` element contains a `CustomerID` element.</span></span> <span data-ttu-id="b71ba-108">El elemento `CustomerID` de cada pedido hace referencia al atributo `CustomerID` de un cliente.</span><span class="sxs-lookup"><span data-stu-id="b71ba-108">The `CustomerID` element in each order refers to the `CustomerID` attribute in a customer.</span></span>

<span data-ttu-id="b71ba-109">En el tema [Archivo XSD de ejemplo: Clientes y pedidos](./sample-xsd-file-customers-and-orders1.md) se incluye un XSD que se puede usar para validar este documento.</span><span class="sxs-lookup"><span data-stu-id="b71ba-109">The topic [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md) contains an XSD that can be used to validate this document.</span></span> <span data-ttu-id="b71ba-110">Usa las características `xs:key` y `xs:keyref` de XSD para establecer que el atributo `CustomerID` del elemento `Customer` es una clave, y para establecer una relación entre el elemento `CustomerID` de cada elemento `Order` y el atributo `CustomerID` de cada elemento `Customer`.</span><span class="sxs-lookup"><span data-stu-id="b71ba-110">It uses the `xs:key` and `xs:keyref` features of XSD to establish that the `CustomerID` attribute of the `Customer` element is a key, and to establish a relationship between the `CustomerID` element in each `Order` element and the `CustomerID` attribute in each `Customer` element.</span></span>

<span data-ttu-id="b71ba-111">Con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], puede aprovechar esta relación mediante la cláusula `join`.</span><span class="sxs-lookup"><span data-stu-id="b71ba-111">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can take advantage of this relationship by using the `join` clause.</span></span>

<span data-ttu-id="b71ba-112">Como no se dispone de ningún índice, la combinación tendrá un rendimiento en tiempo de ejecución bajo.</span><span class="sxs-lookup"><span data-stu-id="b71ba-112">Because there is no index available, such joining will have poor run-time performance.</span></span>

<span data-ttu-id="b71ba-113">Para obtener más información sobre `join`, consulte [Operaciones de combinación (C#)](./join-operations.md).</span><span class="sxs-lookup"><span data-stu-id="b71ba-113">For more detailed information about `join`, see [Join Operations (C#)](./join-operations.md).</span></span>

## <a name="example"></a><span data-ttu-id="b71ba-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b71ba-114">Example</span></span>

<span data-ttu-id="b71ba-115">El ejemplo siguiente combina los elementos `Customer` con los elementos `Order`, y genera un nuevo documento XML que incluye el elemento `CompanyName` en los pedidos.</span><span class="sxs-lookup"><span data-stu-id="b71ba-115">The following example joins the `Customer` elements to the `Order` elements, and generates a new XML document that includes the `CompanyName` element in the orders.</span></span>

<span data-ttu-id="b71ba-116">Antes de ejecutar la consulta, el ejemplo valida que el documento satisface el esquema de [Archivo XSD de ejemplo: Clientes y pedidos](./sample-xsd-file-customers-and-orders1.md).</span><span class="sxs-lookup"><span data-stu-id="b71ba-116">Before executing the query, the example validates that the document complies with the schema in [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md).</span></span> <span data-ttu-id="b71ba-117">Esto garantiza que la cláusula de combinación siempre funcionará.</span><span class="sxs-lookup"><span data-stu-id="b71ba-117">This ensures that the join clause will always work.</span></span>

<span data-ttu-id="b71ba-118">Esta consulta recupera primero todos los elementos `Customer`, y luego los combina con los elementos `Order`.</span><span class="sxs-lookup"><span data-stu-id="b71ba-118">This query first retrieves all `Customer` elements, and then joins them to the `Order` elements.</span></span> <span data-ttu-id="b71ba-119">Selecciona sólo los pedidos de los clientes con un atributo `CustomerID` mayor que "K".</span><span class="sxs-lookup"><span data-stu-id="b71ba-119">It selects only the orders for customers with a `CustomerID` greater than "K".</span></span> <span data-ttu-id="b71ba-120">A continuación, proyecta un nuevo elemento `Order` que contiene la información de cliente en cada pedido.</span><span class="sxs-lookup"><span data-stu-id="b71ba-120">It then projects a new `Order` element that contains the customer information within each order.</span></span>

<span data-ttu-id="b71ba-121">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Clientes y pedidos (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="b71ba-121">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>

<span data-ttu-id="b71ba-122">En este ejemplo se usa el siguiente esquema XSD: [Archivo XSD de ejemplo: Clientes y pedidos](./sample-xsd-file-customers-and-orders1.md).</span><span class="sxs-lookup"><span data-stu-id="b71ba-122">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md).</span></span>

<span data-ttu-id="b71ba-123">La combinación de este modo no funcionará bien.</span><span class="sxs-lookup"><span data-stu-id="b71ba-123">Joining in this fashion will not perform well.</span></span> <span data-ttu-id="b71ba-124">Las combinaciones se llevan a cabo mediante una búsqueda lineal.</span><span class="sxs-lookup"><span data-stu-id="b71ba-124">Joins are performed via a linear search.</span></span> <span data-ttu-id="b71ba-125">No hay tablas o índices hash disponibles para incrementar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b71ba-125">There are no hash tables or indexes to help with performance.</span></span>

```csharp
XmlSchemaSet schemas = new XmlSchemaSet();
schemas.Add("", "CustomersOrders.xsd");

Console.Write("Attempting to validate, ");
XDocument custOrdDoc = XDocument.Load("CustomersOrders.xml");

bool errors = false;
custOrdDoc.Validate(schemas, (o, e) =>
                     {
                         Console.WriteLine("{0}", e.Message);
                         errors = true;
                     });
Console.WriteLine("custOrdDoc {0}", errors ? "did not validate" : "validated");

if (!errors)
{
    // Join customers and orders, and create a new XML document with
    // a different shape.

    // The new document contains orders only for customers with a
    // CustomerID > 'K'
    XElement custOrd = custOrdDoc.Element("Root");
    XElement newCustOrd = new XElement("Root",
        from c in custOrd.Element("Customers").Elements("Customer")
        join o in custOrd.Element("Orders").Elements("Order")
                   on (string)c.Attribute("CustomerID") equals
                      (string)o.Element("CustomerID")
        where ((string)c.Attribute("CustomerID")).CompareTo("K") > 0
        select new XElement("Order",
            new XElement("CustomerID", (string)c.Attribute("CustomerID")),
            new XElement("CompanyName", (string)c.Element("CompanyName")),
            new XElement("ContactName", (string)c.Element("ContactName")),
            new XElement("EmployeeID", (string)o.Element("EmployeeID")),
            new XElement("OrderDate", (DateTime)o.Element("OrderDate"))
        )
    );
    Console.WriteLine(newCustOrd);
}
```

<span data-ttu-id="b71ba-126">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b71ba-126">This code produces the following output:</span></span>

```output
Attempting to validate, custOrdDoc validated
<Root>
  <Order>
    <CustomerID>LAZYK</CustomerID>
    <CompanyName>Lazy K Kountry Store</CompanyName>
    <ContactName>John Steel</ContactName>
    <EmployeeID>1</EmployeeID>
    <OrderDate>1997-03-21T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LAZYK</CustomerID>
    <CompanyName>Lazy K Kountry Store</CompanyName>
    <ContactName>John Steel</ContactName>
    <EmployeeID>8</EmployeeID>
    <OrderDate>1997-05-22T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LETSS</CustomerID>
    <CompanyName>Let's Stop N Shop</CompanyName>
    <ContactName>Jaime Yorres</ContactName>
    <EmployeeID>1</EmployeeID>
    <OrderDate>1997-06-25T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LETSS</CustomerID>
    <CompanyName>Let's Stop N Shop</CompanyName>
    <ContactName>Jaime Yorres</ContactName>
    <EmployeeID>8</EmployeeID>
    <OrderDate>1997-10-27T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LETSS</CustomerID>
    <CompanyName>Let's Stop N Shop</CompanyName>
    <ContactName>Jaime Yorres</ContactName>
    <EmployeeID>6</EmployeeID>
    <OrderDate>1997-11-10T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LETSS</CustomerID>
    <CompanyName>Let's Stop N Shop</CompanyName>
    <ContactName>Jaime Yorres</ContactName>
    <EmployeeID>4</EmployeeID>
    <OrderDate>1998-02-12T00:00:00</OrderDate>
  </Order>
</Root>
```
