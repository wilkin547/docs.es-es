---
title: Procedimiento para hacer streaming de fragmentos XML con acceso a la información del encabezado
ms.date: 07/20/2015
ms.assetid: effd10df-87c4-4d7a-8a9a-1434d829dca5
ms.openlocfilehash: 8d0543ff5a772768292c0e3117f41bea9367d23a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397692"
---
# <a name="how-to-stream-xml-fragments-with-access-to-header-information-visual-basic"></a>Cómo: hacer streaming de fragmentos XML con acceso a información de encabezado (Visual Basic)
A veces debe leer arbitrariamente los archivos XML grandes y escribir la aplicación para que la superficie de memoria de esta sea predecible. Si intenta rellenar un árbol XML con un archivo XML de gran tamaño, su utilización de memoria será proporcional al tamaño del archivo (es decir, excesivo). Por consiguiente, debe utilizar en su lugar una técnica de transmisión por secuencias.  
  
 Una opción consiste en escribir la aplicación usando <xref:System.Xml.XmlReader>. Pero quizás prefiera usar LINQ para consultar el árbol XML. En ese caso, puede escribir su propio método de eje personalizado. Para obtener más información, vea [Cómo: escribir un método de eje de LINQ to XML (Visual Basic)](how-to-write-a-linq-to-xml-axis-method.md).  
  
 Para escribir su propio método de eje, debe escribir un pequeño método que utiliza los nodos <xref:System.Xml.XmlReader> para leer hasta que llega a uno de los nodos en el que está interesado. A continuación el método llama a <xref:System.Xml.Linq.XNode.ReadFrom%2A>, que lee de <xref:System.Xml.XmlReader> y crea una instancia de un fragmento XML. A continuación puede escribir las consultas LINQ en su método de eje personalizado.  
  
 Las técnicas de transmisión por secuencias se aplican mejor en situaciones en las que el documento de origen solo se debe procesar una vez y se pueden procesar los elementos en el orden del documento. Ciertos operadores de consulta estándar, como <xref:System.Linq.Enumerable.OrderBy%2A>, recorren en iteración su origen, recaban todos los datos, los ordenan y finalmente producen el primer elemento de la secuencia. Tenga en cuenta que si utiliza un operador de consulta que materializa su origen antes de producir el primer elemento, no retendrá una superficie de memoria pequeña.  
  
## <a name="example"></a>Ejemplo  
 A veces el problema se pone un poco más interesante. En el siguiente documento XML, el consumidor de su método de eje personalizado también tiene que conocer el nombre del cliente al que pertenece cada elemento.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Root>  
  <Customer>  
    <Name>A. Datum Corporation</Name>  
    <Item>  
      <Key>0001</Key>  
    </Item>  
    <Item>  
      <Key>0002</Key>  
    </Item>  
    <Item>  
      <Key>0003</Key>  
    </Item>  
    <Item>  
      <Key>0004</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Fabrikam, Inc.</Name>  
    <Item>  
      <Key>0005</Key>  
    </Item>  
    <Item>  
      <Key>0006</Key>  
    </Item>  
    <Item>  
      <Key>0007</Key>  
    </Item>  
    <Item>  
      <Key>0008</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Southridge Video</Name>  
    <Item>  
      <Key>0009</Key>  
    </Item>  
    <Item>  
      <Key>0010</Key>  
    </Item>  
  </Customer>  
</Root>  
```  
  
 El enfoque que toma este ejemplo consiste en consultar también esta información de encabezado, guardar la información de encabezado y después crear un pequeño árbol XML que contiene la información de encabezado y el detalle que está enumerando. El método de eje ofrece este nuevo y pequeño árbol XML. La consulta tiene acceso a la información de encabezado así como a la información detallada.  
  
 Este enfoque ocupa una pequeña superficie de memoria. Como se ofrecen todos los fragmentos XML detallados, no se guardan referencias al fragmento anterior y está disponible para la recolección de elementos no utilizados. Tenga en cuenta que esta técnica crea muchos objetos de vida corta en el montón.  
  
 En el siguiente ejemplo se muestra cómo implementar y utilizar un método de eje personalizado que transmite por secuencias fragmentos XML del archivo especificado por la URI. Este eje personalizado ha sido escrito específicamente para que espere un documento que tiene los elementos `Customer`, `Name`, y `Item`, y que esos elementos se ordenarán como en el documento `Source.xml` anterior. Se trata de una implementación simplista. Una implementación más sólida estaría preparada para analizar un documento no válido.  
  
```vb  
Module Module1  
  
    Sub Main()  
        Dim xmlTree = <Root>  
                          <%=  
                              From el In New StreamCustomerItem("Source.xml")  
                              Let itemKey = CInt(el.<Key>.Value)  
                              Where itemKey >= 3 AndAlso itemKey <= 7  
                              Select <Item>  
                                         <Customer><%= el.Parent.<Name>.Value %></Customer>  
                                         <%= el.<Key> %>  
                                     </Item>  
                          %>  
                      </Root>  
  
        Console.WriteLine(xmlTree)  
    End Sub  
  
End Module  
  
Public Class StreamCustomerItem  
    Implements IEnumerable(Of XElement)  
  
    Private _uri As String  
  
    Public Sub New(ByVal uri As String)  
        _uri = uri  
    End Sub  
  
    Public Function GetEnumerator() As IEnumerator(Of XElement) Implements IEnumerable(Of XElement).GetEnumerator  
        Return New StreamCustomerItemEnumerator(_uri)  
    End Function  
  
    Public Function GetEnumerator1() As IEnumerator Implements IEnumerable.GetEnumerator  
        Return Me.GetEnumerator()  
    End Function  
End Class  
  
Public Class StreamCustomerItemEnumerator  
    Implements IEnumerator(Of XElement)  
  
    Private _current As XElement  
    Private _customerName As String  
    Private _reader As Xml.XmlReader  
    Private _uri As String  
  
    Public Sub New(ByVal uri As String)  
        _uri = uri  
        _reader = Xml.XmlReader.Create(_uri)  
        _reader.MoveToContent()  
    End Sub  
  
    Public ReadOnly Property Current As XElement Implements IEnumerator(Of XElement).Current  
        Get  
            Return _current  
        End Get  
    End Property  
  
    Public ReadOnly Property Current1 As Object Implements IEnumerator.Current  
        Get  
            Return Me.Current  
        End Get  
    End Property  
  
    Public Function MoveNext() As Boolean Implements IEnumerator.MoveNext  
        Dim item As XElement  
        Dim name As XElement  
  
        ' Parse the file, save header information when encountered, and return the  
        ' current Item XElement.  
  
        ' loop through Customer elements  
        While _reader.Read()  
            If _reader.NodeType = Xml.XmlNodeType.Element Then  
                Select Case _reader.Name  
                    Case "Customer"  
                        ' move to Name element  
                        While _reader.Read()  
  
                            If _reader.NodeType = Xml.XmlNodeType.Element AndAlso  
                                _reader.Name = "Name" Then  
  
                                name = TryCast(XElement.ReadFrom(_reader), XElement)  
                                _customerName = If(name IsNot Nothing, name.Value, "")  
                                Exit While  
                            End If  
  
                        End While  
                    Case "Item"  
                        item = TryCast(XElement.ReadFrom(_reader), XElement)  
                        Dim tempRoot = <Root>  
                                           <Name><%= _customerName %></Name>  
                                           <%= item %>  
                                       </Root>  
                        _current = item  
                        Return True  
                End Select  
            End If  
        End While  
  
        Return False  
    End Function  
  
    Public Sub Reset() Implements IEnumerator.Reset  
        _reader = Xml.XmlReader.Create(_uri)  
        _reader.MoveToContent()  
    End Sub  
  
#Region "IDisposable Support"  
    Private disposedValue As Boolean ' To detect redundant calls  
  
    ' IDisposable  
    Protected Overridable Sub Dispose(ByVal disposing As Boolean)  
        If Not Me.disposedValue Then  
            If disposing Then  
                _reader.Close()  
            End If  
        End If  
        Me.disposedValue = True  
    End Sub  
  
    Public Sub Dispose() Implements IDisposable.Dispose  
        Dispose(True)  
        GC.SuppressFinalize(Me)  
    End Sub  
#End Region  
  
End Class  
```  
  
 Este código genera el siguiente resultado:  
  
```xml  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0003</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0004</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0005</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0006</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0007</Key>  
  </Item>  
</Root>  
```  
  
## <a name="see-also"></a>Consulte también

- [Programación de LINQ to XML avanzada (Visual Basic)](advanced-linq-to-xml-programming.md)
