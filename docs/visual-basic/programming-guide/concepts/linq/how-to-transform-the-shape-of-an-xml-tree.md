---
title: Procedimiento para transformar la forma de un árbol XML
ms.date: 07/20/2015
ms.assetid: 84b60854-48b2-452c-87f2-77d53e1d653a
ms.openlocfilehash: 90fa23df09972eb76154dc47ce0a025e85a12ea3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397666"
---
# <a name="how-to-transform-the-shape-of-an-xml-tree-visual-basic"></a><span data-ttu-id="bc9b9-102">Cómo: transformar la forma de un árbol XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc9b9-102">How to: Transform the Shape of an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="bc9b9-103">La *forma* de un documento XML hace referencia a sus nombres de elemento, sus nombres de atributo y las características de su jerarquía.</span><span class="sxs-lookup"><span data-stu-id="bc9b9-103">The *shape* of an XML document refers to its element names, attribute names, and the characteristics of its hierarchy.</span></span>  
  
 <span data-ttu-id="bc9b9-104">A veces, deberá cambiar la forma de un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="bc9b9-104">Sometimes you will have to change the shape of an XML document.</span></span> <span data-ttu-id="bc9b9-105">Por ejemplo, es posible que deba enviar un documento XML a otro sistema que requiere nombres de elemento y atributo diferentes.</span><span class="sxs-lookup"><span data-stu-id="bc9b9-105">For example, you might have to send an existing XML document to another system that requires different element and attribute names.</span></span> <span data-ttu-id="bc9b9-106">Podría revisar el documento y eliminar y cambiar el nombre de los elementos necesarios, pero el uso de la construcción funcional proporciona un código más legible y fácil de mantener.</span><span class="sxs-lookup"><span data-stu-id="bc9b9-106">You could go through the document, deleting and renaming elements as required, but using functional construction results in more readable and maintainable code.</span></span> <span data-ttu-id="bc9b9-107">Para obtener más información sobre la construcción funcional, vea [construcción funcional (LINQ to XML) (Visual Basic)](functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="bc9b9-107">For more information about functional construction, see [Functional Construction (LINQ to XML) (Visual Basic)](functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="bc9b9-108">El primer ejemplo cambia la organización del documento XML.</span><span class="sxs-lookup"><span data-stu-id="bc9b9-108">The first example changes the organization of the XML document.</span></span> <span data-ttu-id="bc9b9-109">Mueve los elementos complejos de una ubicación del árbol a otra.</span><span class="sxs-lookup"><span data-stu-id="bc9b9-109">It moves complex elements from one location in the tree to another.</span></span>  
  
 <span data-ttu-id="bc9b9-110">El segundo ejemplo de este tema crea un documento XML con una forma diferente a la del documento de origen.</span><span class="sxs-lookup"><span data-stu-id="bc9b9-110">The second example in this topic creates an XML document with a different shape than the source document.</span></span> <span data-ttu-id="bc9b9-111">Cambia el uso de mayúsculas y minúsculas de los nombres de elemento, cambia el nombre de algunos elementos y deja algunos de los elementos del árbol de origen fuera del árbol transformado.</span><span class="sxs-lookup"><span data-stu-id="bc9b9-111">It changes the casing of the element names, renames some elements, and leaves some elements from the source tree out of the transformed tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc9b9-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc9b9-112">Example</span></span>  
 <span data-ttu-id="bc9b9-113">El código siguiente cambia la forma de un archivo XML con las expresiones de consulta incrustadas.</span><span class="sxs-lookup"><span data-stu-id="bc9b9-113">The following code changes the shape of an XML file using embedded query expressions.</span></span>  
  
 <span data-ttu-id="bc9b9-114">El documento XML de origen de este ejemplo contiene un elemento `Customers` en el elemento `Root` que contiene todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="bc9b9-114">The source XML document in this example contains a `Customers` element under the `Root` element that contains all customers.</span></span> <span data-ttu-id="bc9b9-115">También contiene un elemento `Orders` en el elemento `Root` que contiene todos los pedidos.</span><span class="sxs-lookup"><span data-stu-id="bc9b9-115">It also contains an `Orders` element under the `Root` element that contains all orders.</span></span> <span data-ttu-id="bc9b9-116">Este ejemplo crea un nuevo árbol XML en el que los pedidos de cada cliente se incluyen en un elemento `Orders` dentro del elemento `Customer`.</span><span class="sxs-lookup"><span data-stu-id="bc9b9-116">This example creates a new XML tree in which the orders for each customer are contained in an `Orders` element within the `Customer` element.</span></span> <span data-ttu-id="bc9b9-117">El documento original también contiene un elemento `CustomerID` en el elemento `Order`; este elemento se quitará del documento con la forma cambiada.</span><span class="sxs-lookup"><span data-stu-id="bc9b9-117">The original document also contains a `CustomerID` element in the `Order` element; this element will be removed from the re-shaped document.</span></span>  
  
 <span data-ttu-id="bc9b9-118">En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Clientes y pedidos (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="bc9b9-118">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim co As XElement = XElement.Load("CustomersOrders.xml")  
Dim newCustOrd = _  
    <Root>  
        <%= From cust In co.<Customers>.<Customer> _  
            Select _  
            <Customer>  
                <%= cust.Attributes() %>  
                <%= cust.Elements() %>  
                <Orders>  
                    <%= From ord In co.<Orders>.<Order> _  
                        Where ord.<CustomerID>.Value = cust.@CustomerID _  
                        Select _  
                        <Order>  
                            <%= ord.Attributes() %>  
                            <%= ord.<EmployeeID> %>  
                            <%= ord.<OrderDate> %>  
                            <%= ord.<RequiredDate> %>  
                            <%= ord.<ShipInfo> %>  
                        </Order> _  
                    %>  
                </Orders>  
            </Customer> _  
        %>  
    </Root>  
Console.WriteLine(newCustOrd)  
```  
  
 <span data-ttu-id="bc9b9-119">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="bc9b9-119">This code produces the following output:</span></span>  
  
```xml  
<Root>  
<Customer CustomerID="GREAL">  
  <CompanyName>Great Lakes Food Market</CompanyName>  
  <ContactName>Howard Snyder</ContactName>  
  <ContactTitle>Marketing Manager</ContactTitle>  
  <Phone>(503) 555-7555</Phone>  
  <FullAddress>  
    <Address>2732 Baker Blvd.</Address>  
    <City>Eugene</City>  
    <Region>OR</Region>  
    <PostalCode>97403</PostalCode>  
    <Country>USA</Country>  
  </FullAddress>  
  <Orders />  
</Customer>  
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
  <Orders />  
</Customer>  
...
</Root>
```  
  
## <a name="example"></a><span data-ttu-id="bc9b9-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc9b9-120">Example</span></span>  
 <span data-ttu-id="bc9b9-121">Este ejemplo cambia el nombre de algunos elementos y convierte algunos atributos en elementos.</span><span class="sxs-lookup"><span data-stu-id="bc9b9-121">This example renames some elements and converts some attributes to elements.</span></span>  
  
 <span data-ttu-id="bc9b9-122">El código llama a `ConvertAddress`, que devuelve una lista de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="bc9b9-122">The code calls `ConvertAddress`, which returns a list of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="bc9b9-123">El argumento del método es una consulta que determina el elemento complejo `Address` en el que el atributo `Type` tiene un valor `"Shipping"`.</span><span class="sxs-lookup"><span data-stu-id="bc9b9-123">The argument to the method is a query that determines the `Address` complex element where the `Type` attribute has a value of `"Shipping"`.</span></span>  
  
 <span data-ttu-id="bc9b9-124">En este ejemplo se usa el siguiente documento XML: [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md) (Archivo XML de ejemplo: pedido de compra común [LINQ to XML]).</span><span class="sxs-lookup"><span data-stu-id="bc9b9-124">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Function ConvertAddress(ByVal add As XElement) As IEnumerable(Of XElement)  
    Dim fragment = New List(Of XElement)  
    fragment.Add(<NAME><%= add.<Name>.Value %></NAME>)  
    fragment.Add(<STREET><%= add.<Street>.Value %></STREET>)  
    fragment.Add(<CITY><%= add.<City>.Value %></CITY>)  
    fragment.Add(<ST><%= add.<State>.Value %></ST>)  
    fragment.Add(<POSTALCODE><%= add.<Zip>.Value %></POSTALCODE>)  
    fragment.Add(<COUNTRY><%= add.<Country>.Value %></COUNTRY>)  
    Return fragment  
End Function  
  
Sub Main()  
    Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
    Dim newPo As XElement = _  
        <PO>  
            <ID><%= po.@PurchaseOrderNumber %></ID>  
            <DATE><%= CDate(po.@OrderDate) %></DATE>  
            <%= _  
                ConvertAddress( _  
                (From el In po.<Address> _  
                Where el.@Type = "Shipping" _  
                Select el) _  
                .First() _  
                ) _  
            %>  
        </PO>  
    Console.WriteLine(newPo)  
End Sub  
```  
  
 <span data-ttu-id="bc9b9-125">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="bc9b9-125">This code produces the following output:</span></span>  
  
```xml  
<PO>  
  <ID>99503</ID>  
  <DATE>1999-10-20T00:00:00</DATE>  
  <NAME>Ellen Adams</NAME>  
  <STREET>123 Maple Street</STREET>  
  <CITY>Mill Valley</CITY>  
  <ST>CA</ST>  
  <POSTALCODE>10999</POSTALCODE>  
  <COUNTRY>USA</COUNTRY>  
</PO>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bc9b9-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc9b9-126">See also</span></span>

- [<span data-ttu-id="bc9b9-127">Proyecciones y transformaciones (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc9b9-127">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](projections-and-transformations-linq-to-xml.md)
