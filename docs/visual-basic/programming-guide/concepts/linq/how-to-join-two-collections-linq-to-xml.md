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
# <a name="how-to-join-two-collections-linq-to-xml-visual-basic"></a>Cómo: combinar dos colecciones (LINQ to XML) (Visual Basic)
A veces, un elemento o atributo de un documento XML puede hacer referencia a otro elemento o atributo. Por ejemplo, el documento XML [Archivo XML de muestra: clientes y pedidos (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md) contiene una lista de clientes y una lista de pedidos. Cada elemento `Customer` contiene un atributo `CustomerID`. Cada elemento `Order` contiene un elemento `CustomerID`. El elemento `CustomerID` de cada pedido hace referencia al atributo `CustomerID` de un cliente.  
  
 En el tema [Sample XSD File: Customers and Orders](sample-xsd-file-customers-and-orders.md) (Archivo XSD de ejemplo: Clientes y pedidos) se incluye un XSD que se puede usar para validar este documento. Usa las características `xs:key` y `xs:keyref` de XSD para establecer que el atributo `CustomerID` del elemento `Customer` es una clave, y para establecer una relación entre el elemento `CustomerID` de cada elemento `Order` y el atributo `CustomerID` de cada elemento `Customer`.  
  
 Con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], puede aprovechar esta relación mediante la cláusula `Join`.  
  
 Tenga en cuenta que como no se dispone de ningún índice, la combinación tendrá un rendimiento en tiempo de ejecución bajo.  
  
 Para obtener información más detallada acerca de `Join` , vea [operaciones de combinación (Visual Basic)](join-operations.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente combina los elementos `Customer` con los elementos `Order`, y genera un nuevo documento XML que incluye el elemento `CompanyName` en los pedidos.  
  
 Antes de ejecutar la consulta, el ejemplo valida que el documento cumple el esquema de [Sample XSD File: Customers and Orders](sample-xsd-file-customers-and-orders.md) (Archivo XSD de ejemplo: Clientes y pedidos). Esto garantiza que la cláusula de combinación siempre funcionará.  
  
 Esta consulta recupera primero todos los elementos `Customer`, y luego los combina con los elementos `Order`. Selecciona sólo los pedidos de los clientes con un atributo `CustomerID` mayor que "K". A continuación, proyecta un nuevo elemento `Order` que contiene la información de cliente en cada pedido.  
  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Clientes y pedidos (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md).  
  
 En este ejemplo se usa el siguiente esquema XSD: [Sample XSD File: Customers and Orders](sample-xsd-file-customers-and-orders.md) (Archivo XSD de ejemplo: Clientes y pedidos).  
  
 Tenga en cuenta que si se realiza la combinación de esta forma, el rendimiento no será muy bueno. Las combinaciones se llevan a cabo mediante una búsqueda lineal. No hay tablas o índices hash disponibles para incrementar el rendimiento.  
  
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
  
 Este código genera el siguiente resultado:  
  
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
  
## <a name="see-also"></a>Consulte también

- [Técnicas de consulta avanzadas (LINQ to XML) (Visual Basic)](advanced-query-techniques-linq-to-xml.md)
