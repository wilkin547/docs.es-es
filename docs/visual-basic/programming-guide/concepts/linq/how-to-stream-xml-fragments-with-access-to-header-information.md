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
# <a name="how-to-stream-xml-fragments-with-access-to-header-information-visual-basic"></a><span data-ttu-id="9b0c3-102">Cómo: hacer streaming de fragmentos XML con acceso a información de encabezado (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b0c3-102">How to: Stream XML Fragments with Access to Header Information (Visual Basic)</span></span>
<span data-ttu-id="9b0c3-103">A veces debe leer arbitrariamente los archivos XML grandes y escribir la aplicación para que la superficie de memoria de esta sea predecible.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-103">Sometimes you have to read arbitrarily large XML files, and write your application so that the memory footprint of the application is predictable.</span></span> <span data-ttu-id="9b0c3-104">Si intenta rellenar un árbol XML con un archivo XML de gran tamaño, su utilización de memoria será proporcional al tamaño del archivo (es decir, excesivo).</span><span class="sxs-lookup"><span data-stu-id="9b0c3-104">If you attempt to populate an XML tree with a large XML file, your memory usage will be proportional to the size of the file—that is, excessive.</span></span> <span data-ttu-id="9b0c3-105">Por consiguiente, debe utilizar en su lugar una técnica de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-105">Therefore, you should use a streaming technique instead.</span></span>  
  
 <span data-ttu-id="9b0c3-106">Una opción consiste en escribir la aplicación usando <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-106">One option is to write your application using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="9b0c3-107">Pero quizás prefiera usar LINQ para consultar el árbol XML.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-107">However, you might want to use LINQ to query the XML tree.</span></span> <span data-ttu-id="9b0c3-108">En ese caso, puede escribir su propio método de eje personalizado.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-108">If this is the case, you can write your own custom axis method.</span></span> <span data-ttu-id="9b0c3-109">Para obtener más información, vea [Cómo: escribir un método de eje de LINQ to XML (Visual Basic)](how-to-write-a-linq-to-xml-axis-method.md).</span><span class="sxs-lookup"><span data-stu-id="9b0c3-109">For more information, see [How to: Write a LINQ to XML Axis Method (Visual Basic)](how-to-write-a-linq-to-xml-axis-method.md).</span></span>  
  
 <span data-ttu-id="9b0c3-110">Para escribir su propio método de eje, debe escribir un pequeño método que utiliza los nodos <xref:System.Xml.XmlReader> para leer hasta que llega a uno de los nodos en el que está interesado.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-110">To write your own axis method, you write a small method that uses the <xref:System.Xml.XmlReader> to read nodes until it reaches one of the nodes in which you are interested.</span></span> <span data-ttu-id="9b0c3-111">A continuación el método llama a <xref:System.Xml.Linq.XNode.ReadFrom%2A>, que lee de <xref:System.Xml.XmlReader> y crea una instancia de un fragmento XML.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-111">The method then calls <xref:System.Xml.Linq.XNode.ReadFrom%2A>, which reads from the <xref:System.Xml.XmlReader> and instantiates an XML fragment.</span></span> <span data-ttu-id="9b0c3-112">A continuación puede escribir las consultas LINQ en su método de eje personalizado.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-112">You can then write LINQ queries on your custom axis method.</span></span>  
  
 <span data-ttu-id="9b0c3-113">Las técnicas de transmisión por secuencias se aplican mejor en situaciones en las que el documento de origen solo se debe procesar una vez y se pueden procesar los elementos en el orden del documento.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-113">Streaming techniques are best applied in situations where you need to process the source document only once, and you can process the elements in document order.</span></span> <span data-ttu-id="9b0c3-114">Ciertos operadores de consulta estándar, como <xref:System.Linq.Enumerable.OrderBy%2A>, recorren en iteración su origen, recaban todos los datos, los ordenan y finalmente producen el primer elemento de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-114">Certain standard query operators, such as <xref:System.Linq.Enumerable.OrderBy%2A>, iterate their source, collect all of the data, sort it, and then finally yield the first item in the sequence.</span></span> <span data-ttu-id="9b0c3-115">Tenga en cuenta que si utiliza un operador de consulta que materializa su origen antes de producir el primer elemento, no retendrá una superficie de memoria pequeña.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-115">Note that if you use a query operator that materializes its source before yielding the first item, you will not retain a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b0c3-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9b0c3-116">Example</span></span>  
 <span data-ttu-id="9b0c3-117">A veces el problema se pone un poco más interesante.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-117">Sometimes the problem gets just a little more interesting.</span></span> <span data-ttu-id="9b0c3-118">En el siguiente documento XML, el consumidor de su método de eje personalizado también tiene que conocer el nombre del cliente al que pertenece cada elemento.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-118">In the following XML document, the consumer of your custom axis method also has to know the name of the customer that each item belongs to.</span></span>  
  
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
  
 <span data-ttu-id="9b0c3-119">El enfoque que toma este ejemplo consiste en consultar también esta información de encabezado, guardar la información de encabezado y después crear un pequeño árbol XML que contiene la información de encabezado y el detalle que está enumerando.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-119">The approach that this example takes is to also watch for this header information, save the header information, and then build a small XML tree that contains both the header information and the detail that you are enumerating.</span></span> <span data-ttu-id="9b0c3-120">El método de eje ofrece este nuevo y pequeño árbol XML.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-120">The axis method then yields this new, small XML tree.</span></span> <span data-ttu-id="9b0c3-121">La consulta tiene acceso a la información de encabezado así como a la información detallada.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-121">The query then has access to the header information as well as the detail information.</span></span>  
  
 <span data-ttu-id="9b0c3-122">Este enfoque ocupa una pequeña superficie de memoria.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-122">This approach has a small memory footprint.</span></span> <span data-ttu-id="9b0c3-123">Como se ofrecen todos los fragmentos XML detallados, no se guardan referencias al fragmento anterior y está disponible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-123">As each detail XML fragment is yielded, no references are kept to the previous fragment, and it is available for garbage collection.</span></span> <span data-ttu-id="9b0c3-124">Tenga en cuenta que esta técnica crea muchos objetos de vida corta en el montón.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-124">Note that this technique creates many short lived objects on the heap.</span></span>  
  
 <span data-ttu-id="9b0c3-125">En el siguiente ejemplo se muestra cómo implementar y utilizar un método de eje personalizado que transmite por secuencias fragmentos XML del archivo especificado por la URI.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-125">The following example shows how to implement and use a custom axis method that streams XML fragments from the file specified by the URI.</span></span> <span data-ttu-id="9b0c3-126">Este eje personalizado ha sido escrito específicamente para que espere un documento que tiene los elementos `Customer`, `Name`, y `Item`, y que esos elementos se ordenarán como en el documento `Source.xml` anterior.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-126">This custom axis is specifically written such that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the above `Source.xml` document.</span></span> <span data-ttu-id="9b0c3-127">Se trata de una implementación simplista.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-127">It is a simplistic implementation.</span></span> <span data-ttu-id="9b0c3-128">Una implementación más sólida estaría preparada para analizar un documento no válido.</span><span class="sxs-lookup"><span data-stu-id="9b0c3-128">A more robust implementation would be prepared to parse an invalid document.</span></span>  
  
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
  
 <span data-ttu-id="9b0c3-129">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="9b0c3-129">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9b0c3-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9b0c3-130">See also</span></span>

- [<span data-ttu-id="9b0c3-131">Programación de LINQ to XML avanzada (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b0c3-131">Advanced LINQ to XML Programming (Visual Basic)</span></span>](advanced-linq-to-xml-programming.md)
