---
title: Procedimiento para transformar la forma de un árbol XML
ms.date: 07/20/2015
ms.assetid: 84b60854-48b2-452c-87f2-77d53e1d653a
ms.openlocfilehash: 24cf02d84b498fc4b41238b1adaf7316cb139a10
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82796111"
---
# <a name="how-to-transform-the-shape-of-an-xml-tree-visual-basic"></a>Cómo: transformar la forma de un árbol XML (Visual Basic)
La *forma* de un documento XML hace referencia a sus nombres de elemento, sus nombres de atributo y las características de su jerarquía.  
  
 A veces, deberá cambiar la forma de un elemento XML. Por ejemplo, es posible que deba enviar un documento XML a otro sistema que requiere nombres de elemento y atributo diferentes. Podría revisar el documento y eliminar y cambiar el nombre de los elementos necesarios, pero el uso de la construcción funcional proporciona un código más legible y fácil de mantener. Para obtener más información sobre la construcción funcional, vea [construcción funcional (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).  
  
 El primer ejemplo cambia la organización del documento XML. Mueve los elementos complejos de una ubicación del árbol a otra.  
  
 El segundo ejemplo de este tema crea un documento XML con una forma diferente a la del documento de origen. Cambia el uso de mayúsculas y minúsculas de los nombres de elemento, cambia el nombre de algunos elementos y deja algunos de los elementos del árbol de origen fuera del árbol transformado.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente cambia la forma de un archivo XML con las expresiones de consulta incrustadas.  
  
 El documento XML de origen de este ejemplo contiene un elemento `Customers` en el elemento `Root` que contiene todos los clientes. También contiene un elemento `Orders` en el elemento `Root` que contiene todos los pedidos. Este ejemplo crea un nuevo árbol XML en el que los pedidos de cada cliente se incluyen en un elemento `Orders` dentro del elemento `Customer`. El documento original también contiene un elemento `CustomerID` en el elemento `Order`; este elemento se quitará del documento con la forma cambiada.  
  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Clientes y pedidos (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).  
  
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
  
 Este código genera el siguiente resultado:  
  
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
  
## <a name="example"></a>Ejemplo  
 Este ejemplo cambia el nombre de algunos elementos y convierte algunos atributos en elementos.  
  
 El código llama a `ConvertAddress`, que devuelve una lista de objetos <xref:System.Xml.Linq.XElement>. El argumento del método es una consulta que determina el elemento complejo `Address` en el que el atributo `Type` tiene un valor `"Shipping"`.  
  
 En este ejemplo se usa el siguiente documento XML: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md) (Archivo XML de ejemplo: pedido de compra común [LINQ to XML]).  
  
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
  
 Este código genera el siguiente resultado:  
  
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
  
## <a name="see-also"></a>Vea también

- [Proyecciones y transformaciones (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
