---
title: Procedimiento para combinar dos colecciones (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 5a5758d4-906b-4285-908d-5b930db192e6
ms.openlocfilehash: dc3cfd19d990fa81e00f4781cb15bf07eb9a80ea
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398056"
---
# <a name="how-to-join-two-collections-linq-to-xml-visual-basic"></a><span data-ttu-id="f27e1-102">Cómo: combinar dos colecciones (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f27e1-102">How to: Join Two Collections (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="f27e1-103">A veces, un elemento o atributo de un documento XML puede hacer referencia a otro elemento o atributo.</span><span class="sxs-lookup"><span data-stu-id="f27e1-103">An element or attribute in an XML document can sometimes refer to another element or attribute.</span></span> <span data-ttu-id="f27e1-104">Por ejemplo, el documento XML [Archivo XML de muestra: clientes y pedidos (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md) contiene una lista de clientes y una lista de pedidos.</span><span class="sxs-lookup"><span data-stu-id="f27e1-104">For example, the [Sample XML File: Customers and Orders (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md) XML document contains a list of customers and a list of orders.</span></span> <span data-ttu-id="f27e1-105">Cada elemento `Customer` contiene un atributo `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="f27e1-105">Each `Customer` element contains a `CustomerID` attribute.</span></span> <span data-ttu-id="f27e1-106">Cada elemento `Order` contiene un elemento `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="f27e1-106">Each `Order` element contains a `CustomerID` element.</span></span> <span data-ttu-id="f27e1-107">El elemento `CustomerID` de cada pedido hace referencia al atributo `CustomerID` de un cliente.</span><span class="sxs-lookup"><span data-stu-id="f27e1-107">The `CustomerID` element in each order refers to the `CustomerID` attribute in a customer.</span></span>  
  
 <span data-ttu-id="f27e1-108">En el tema [Sample XSD File: Customers and Orders](sample-xsd-file-customers-and-orders.md) (Archivo XSD de ejemplo: Clientes y pedidos) se incluye un XSD que se puede usar para validar este documento.</span><span class="sxs-lookup"><span data-stu-id="f27e1-108">The topic [Sample XSD File: Customers and Orders](sample-xsd-file-customers-and-orders.md) contains an XSD that can be used to validate this document.</span></span> <span data-ttu-id="f27e1-109">Usa las características `xs:key` y `xs:keyref` de XSD para establecer que el atributo `CustomerID` del elemento `Customer` es una clave, y para establecer una relación entre el elemento `CustomerID` de cada elemento `Order` y el atributo `CustomerID` de cada elemento `Customer`.</span><span class="sxs-lookup"><span data-stu-id="f27e1-109">It uses the `xs:key` and `xs:keyref` features of XSD to establish that the `CustomerID` attribute of the `Customer` element is a key, and to establish a relationship between the `CustomerID` element in each `Order` element and the `CustomerID` attribute in each `Customer` element.</span></span>  
  
 <span data-ttu-id="f27e1-110">Con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], puede aprovechar esta relación mediante la cláusula `Join`.</span><span class="sxs-lookup"><span data-stu-id="f27e1-110">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can take advantage of this relationship by using the `Join` clause.</span></span>  
  
 <span data-ttu-id="f27e1-111">Tenga en cuenta que como no se dispone de ningún índice, la combinación tendrá un rendimiento en tiempo de ejecución bajo.</span><span class="sxs-lookup"><span data-stu-id="f27e1-111">Note that because there is no index available, such joining will have poor runtime performance.</span></span>  
  
 <span data-ttu-id="f27e1-112">Para obtener información más detallada acerca de `Join` , vea [operaciones de combinación (Visual Basic)](join-operations.md).</span><span class="sxs-lookup"><span data-stu-id="f27e1-112">For more detailed information about `Join`, see [Join Operations (Visual Basic)](join-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f27e1-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f27e1-113">Example</span></span>  
 <span data-ttu-id="f27e1-114">El ejemplo siguiente combina los elementos `Customer` con los elementos `Order`, y genera un nuevo documento XML que incluye el elemento `CompanyName` en los pedidos.</span><span class="sxs-lookup"><span data-stu-id="f27e1-114">The following example joins the `Customer` elements to the `Order` elements, and generates a new XML document that includes the `CompanyName` element in the orders.</span></span>  
  
 <span data-ttu-id="f27e1-115">Antes de ejecutar la consulta, el ejemplo valida que el documento cumple el esquema de [Sample XSD File: Customers and Orders](sample-xsd-file-customers-and-orders.md) (Archivo XSD de ejemplo: Clientes y pedidos).</span><span class="sxs-lookup"><span data-stu-id="f27e1-115">Before executing the query, the example validates that the document complies with the schema in [Sample XSD File: Customers and Orders](sample-xsd-file-customers-and-orders.md).</span></span> <span data-ttu-id="f27e1-116">Esto garantiza que la cláusula de combinación siempre funcionará.</span><span class="sxs-lookup"><span data-stu-id="f27e1-116">This ensures that the join clause will always work.</span></span>  
  
 <span data-ttu-id="f27e1-117">Esta consulta recupera primero todos los elementos `Customer`, y luego los combina con los elementos `Order`.</span><span class="sxs-lookup"><span data-stu-id="f27e1-117">This query first retrieves all `Customer` elements, and then joins them to the `Order` elements.</span></span> <span data-ttu-id="f27e1-118">Selecciona sólo los pedidos de los clientes con un atributo `CustomerID` mayor que "K".</span><span class="sxs-lookup"><span data-stu-id="f27e1-118">It selects only the orders for customers with a `CustomerID` greater than "K".</span></span> <span data-ttu-id="f27e1-119">A continuación, proyecta un nuevo elemento `Order` que contiene la información de cliente en cada pedido.</span><span class="sxs-lookup"><span data-stu-id="f27e1-119">It then projects a new `Order` element that contains the customer information within each order.</span></span>  
  
 <span data-ttu-id="f27e1-120">En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Clientes y pedidos (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f27e1-120">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="f27e1-121">En este ejemplo se usa el siguiente esquema XSD: [Sample XSD File: Customers and Orders](sample-xsd-file-customers-and-orders.md) (Archivo XSD de ejemplo: Clientes y pedidos).</span><span class="sxs-lookup"><span data-stu-id="f27e1-121">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](sample-xsd-file-customers-and-orders.md).</span></span>  
  
 <span data-ttu-id="f27e1-122">Tenga en cuenta que si se realiza la combinación de esta forma, el rendimiento no será muy bueno.</span><span class="sxs-lookup"><span data-stu-id="f27e1-122">Note that joining in this fashion will not perform very well.</span></span> <span data-ttu-id="f27e1-123">Las combinaciones se llevan a cabo mediante una búsqueda lineal.</span><span class="sxs-lookup"><span data-stu-id="f27e1-123">Joins are performed via a linear search.</span></span> <span data-ttu-id="f27e1-124">No hay tablas o índices hash disponibles para incrementar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="f27e1-124">There are no hash tables or indexes to help with performance.</span></span>  
  
```vb  
Public Class Program  
    Public Shared errors As Boolean = False  
  
    Public Shared Function LamValidEvent(ByVal o As Object, _  
                 ByVal e As ValidationEventArgs) As Boolean  
        Console.WriteLine("{0}", e.Message)  
        errors = True  
    End Function  
  
    Shared Sub Main()  
        Dim schemas As New XmlSchemaSet()  
        schemas.Add("", "CustomersOrders.xsd")  
  
        Console.Write("Attempting to validate, ")  
        Dim custOrdDoc As XDocument = XDocument.Load("CustomersOrders.xml")  
  
        custOrdDoc.Validate(schemas, Function(o, e) LamValidEvent(0, e))  
        If errors Then  
            Console.WriteLine("custOrdDoc did not validate")  
        Else  
            Console.WriteLine("custOrdDoc validated")  
        End If  
  
        If Not errors Then  
            'Join customers and orders, and create a new XML document with  
            ' a different shape.  
            'The new document contains orders only for customers with a  
            ' CustomerID > 'K'.  
            Dim custOrd As XElement = custOrdDoc.<Root>.FirstOrDefault  
            Dim newCustOrd As XElement = _  
                <Root>  
                    <%= From c In custOrd.<Customers>.<Customer> _  
                        Join o In custOrd.<Orders>.<Order> _  
                        On c.@CustomerID Equals o.<CustomerID>.Value _  
                        Where c.@CustomerID.CompareTo("K") > 0 _  
                        Select _  
                        <Order>  
                            <CustomerID><%= c.@CustomerID %></CustomerID>  
                            <%= c.<CompanyName> %>  
                            <%= c.<ContactName> %>  
                            <%= o.<EmployeeID> %>  
                            <%= o.<OrderDate> %>  
                        </Order> _  
                    %>  
                </Root>  
            Console.WriteLine(newCustOrd)  
        End If  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="f27e1-125">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="f27e1-125">This code produces the following output:</span></span>  
  
```console
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
  
## <a name="see-also"></a><span data-ttu-id="f27e1-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f27e1-126">See also</span></span>

- [<span data-ttu-id="f27e1-127">Técnicas de consulta avanzadas (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f27e1-127">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](advanced-query-techniques-linq-to-xml.md)
