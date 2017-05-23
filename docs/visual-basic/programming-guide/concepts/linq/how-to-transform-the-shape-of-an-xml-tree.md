---
title: "Cómo: transformar la forma de un árbol XML (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 84b60854-48b2-452c-87f2-77d53e1d653a
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9c71f4af829a395204bc17161547aa5fdd06cbb1
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-transform-the-shape-of-an-xml-tree-visual-basic"></a>Cómo: transformar la forma de un árbol XML (Visual Basic)
El *forma* de un documento XML documento hace referencia a sus nombres de elemento, nombres de atributo y las características de su jerarquía.  
  
 A veces, deberá cambiar la forma de un elemento XML. Por ejemplo, es posible que deba enviar un documento XML a otro sistema que requiere nombres de elemento y atributo diferentes. Podría revisar el documento y eliminar y cambiar el nombre de los elementos necesarios, pero el uso de la construcción funcional proporciona un código más legible y fácil de mantener. Para obtener más información acerca de la construcción funcional, vea [construcción funcional (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).  
  
 El primer ejemplo cambia la organización del documento XML. Mueve los elementos complejos de una ubicación del árbol a otra.  
  
 El segundo ejemplo de este tema crea un documento XML con una forma diferente a la del documento de origen. Cambia el uso de mayúsculas y minúsculas de los nombres de elemento, cambia el nombre de algunos elementos y deja algunos de los elementos del árbol de origen fuera del árbol transformado.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente cambia la forma de un archivo XML con las expresiones de consulta incrustadas.  
  
 El documento XML de origen de este ejemplo contiene un elemento `Customers` en el elemento `Root` que contiene todos los clientes. También contiene un elemento `Orders` en el elemento `Root` que contiene todos los pedidos. Este ejemplo crea un nuevo árbol XML en el que los pedidos de cada cliente se incluyen en un elemento `Orders` dentro del elemento `Customer`. El documento original también contiene un elemento `CustomerID` en el elemento `Order`; este elemento se quitará del documento con la forma cambiada.  
  
 Este ejemplo utiliza el siguiente documento XML: [archivo XML de ejemplo: clientes y pedidos (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).  
  
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
. . .  
```  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo cambia el nombre de algunos elementos y convierte algunos atributos en elementos.  
  
 El código llama `ConvertAddress`, que devuelve una lista de <xref:System.Xml.Linq.XElement>objetos.</xref:System.Xml.Linq.XElement> El argumento del método es una consulta que determina el elemento complejo `Address` en el que el atributo `Type` tiene un valor `"Shipping"`.  
  
 Este ejemplo utiliza el siguiente documento XML: [archivo XML de ejemplo: pedido de compra típico (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).  
  
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
 [Proyecciones y transformaciones (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)

