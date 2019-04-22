---
title: Procedimiento Combinar dos colecciones (LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 5a5758d4-906b-4285-908d-5b930db192e6
ms.openlocfilehash: 85689fa756ab20a4dcd054b70eb3003c767936ea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58843245"
---
# <a name="how-to-join-two-collections-linq-to-xml-visual-basic"></a>Procedimiento Combinar dos colecciones (LINQ to XML) (Visual Basic)
A veces, un elemento o atributo de un documento XML puede hacer referencia a otro elemento o atributo. Por ejemplo, el documento XML [Archivo XML de ejemplo: Clientes y pedidos (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md) contiene una lista de clientes y una lista de pedidos. Cada elemento `Customer` contiene un atributo `CustomerID`. Cada elemento `Order` contiene un elemento `CustomerID`. El elemento `CustomerID` de cada pedido hace referencia al atributo `CustomerID` de un cliente.  
  
 En el tema [Archivo XSD de ejemplo: Clientes y pedidos](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md) se incluye un XSD que se puede usar para validar este documento. Usa las características `xs:key` y `xs:keyref` de XSD para establecer que el atributo `CustomerID` del elemento `Customer` es una clave, y para establecer una relación entre el elemento `CustomerID` de cada elemento `Order` y el atributo `CustomerID` de cada elemento `Customer`.  
  
 Con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], puede aprovechar esta relación mediante la cláusula `Join`.  
  
 Tenga en cuenta que como no se dispone de ningún índice, la combinación tendrá un rendimiento en tiempo de ejecución bajo.  
  
 Para obtener más información acerca de `Join`, consulte [operaciones de combinación (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/join-operations.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente combina los elementos `Customer` con los elementos `Order`, y genera un nuevo documento XML que incluye el elemento `CompanyName` en los pedidos.  
  
 Antes de ejecutar la consulta, el ejemplo valida que el documento satisface el esquema de [Archivo XSD de ejemplo: Clientes y pedidos](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md). Esto garantiza que la cláusula de combinación siempre funcionará.  
  
 Esta consulta recupera primero todos los elementos `Customer`, y luego los combina con los elementos `Order`. Selecciona sólo los pedidos de los clientes con un atributo `CustomerID` mayor que "K". A continuación, proyecta un nuevo elemento `Order` que contiene la información de cliente en cada pedido.  
  
 Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Clientes y pedidos (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).  
  
 En este ejemplo se usa el siguiente esquema XSD: [Archivo XSD de ejemplo: Clientes y pedidos](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).  
  
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
  
```  
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
  
## <a name="see-also"></a>Vea también

- [Consulta técnicas avanzadas (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
