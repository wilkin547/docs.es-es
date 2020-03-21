---
title: 'Cómo: Realizar una transformación de streaming de documentos XML grandes'
ms.date: 07/20/2015
ms.assetid: 3d954cc9-4b3c-4b47-8132-ff7541cff53b
ms.openlocfilehash: f5e6063f0a850c03a605d75b0cbdc0bf9e03b325
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2020
ms.locfileid: "78267020"
---
# <a name="how-to-perform-streaming-transform-of-large-xml-documents-visual-basic"></a><span data-ttu-id="6adbb-102">Cómo: Realizar la transformación de streaming de documentos XML grandes (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6adbb-102">How to: Perform Streaming Transform of Large XML Documents (Visual Basic)</span></span>
<span data-ttu-id="6adbb-103">A veces tiene que transformar los archivos XML grandes y escribir la aplicación para que sea predecible la superficie en memoria de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6adbb-103">Sometimes you have to transform large XML files, and write your application so that the memory footprint of the application is predictable.</span></span> <span data-ttu-id="6adbb-104">Si intenta rellenar un árbol XML con un archivo XML de gran tamaño, su utilización de memoria será proporcional al tamaño del archivo (es decir, excesivo).</span><span class="sxs-lookup"><span data-stu-id="6adbb-104">If you try to populate an XML tree with a very large XML file, your memory usage will be proportional to the size of the file (that is, excessive).</span></span> <span data-ttu-id="6adbb-105">Por consiguiente, debe utilizar en su lugar una técnica de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="6adbb-105">Therefore, you should use a streaming technique instead.</span></span>  
  
 <span data-ttu-id="6adbb-106">Las técnicas de transmisión por secuencias se aplican mejor en situaciones en las que el documento de origen solo se debe procesar una vez y se pueden procesar los elementos en el orden del documento.</span><span class="sxs-lookup"><span data-stu-id="6adbb-106">Streaming techniques are best applied in situations where you need to process the source document only once, and you can process the elements in document order.</span></span> <span data-ttu-id="6adbb-107">Ciertos operadores de consulta estándar, como <xref:System.Linq.Enumerable.OrderBy%2A>, recorren en iteración su origen, recaban todos los datos, los ordenan y finalmente producen el primer elemento de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="6adbb-107">Certain standard query operators, such as <xref:System.Linq.Enumerable.OrderBy%2A>, iterate their source, collect all of the data, sort it, and then finally yield the first item in the sequence.</span></span> <span data-ttu-id="6adbb-108">Tenga en cuenta que si utiliza un operador de consulta que materializa su origen antes de producir el primer elemento, no retendrá una superficie de memoria pequeña para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6adbb-108">Note that if you use a query operator that materializes its source before yielding the first item, you will not retain a small memory footprint for your application.</span></span>  
  
 <span data-ttu-id="6adbb-109">Incluso si utiliza la técnica descrita en [Cómo: transmitir fragmentos XML con acceso a](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md)información de encabezado (Visual Basic), si intenta ensamblar un árbol XML que contiene el documento transformado, el uso de memoria será demasiado grande.</span><span class="sxs-lookup"><span data-stu-id="6adbb-109">Even if you use the technique described in [How to: Stream XML Fragments with Access to Header Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md), if you try to assemble an XML tree that contains the transformed document, memory usage will be too great.</span></span>  
  
 <span data-ttu-id="6adbb-110">Hay dos grandes enfoques.</span><span class="sxs-lookup"><span data-stu-id="6adbb-110">There are two main approaches.</span></span> <span data-ttu-id="6adbb-111">Un enfoque consiste en utilizar las características de procesamiento aplazada de <xref:System.Xml.Linq.XStreamingElement>.</span><span class="sxs-lookup"><span data-stu-id="6adbb-111">One approach is to use the deferred processing characteristics of <xref:System.Xml.Linq.XStreamingElement>.</span></span> <span data-ttu-id="6adbb-112">El otro enfoque consiste en crear un <xref:System.Xml.XmlWriter> y utilizar las capacidades de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] para escribir elementos en un <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="6adbb-112">Another approach is to create an <xref:System.Xml.XmlWriter>, and use the capabilities of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to write elements to an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="6adbb-113">En este tema se muestran ambos enfoques.</span><span class="sxs-lookup"><span data-stu-id="6adbb-113">This topic demonstrates both approaches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6adbb-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6adbb-114">Example</span></span>  
 <span data-ttu-id="6adbb-115">En el ejemplo siguiente se basa en el ejemplo [de Cómo: transmitir fragmentos XML con acceso a](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md)información de encabezado (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="6adbb-115">The following example builds on the example in [How to: Stream XML Fragments with Access to Header Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md).</span></span>  
  
 <span data-ttu-id="6adbb-116">Este ejemplo utiliza las funciones de ejecución aplazada de <xref:System.Xml.Linq.XStreamingElement> para transmitir por secuencias el resultado.</span><span class="sxs-lookup"><span data-stu-id="6adbb-116">This example uses the deferred execution capabilities of <xref:System.Xml.Linq.XStreamingElement> to stream the output.</span></span> <span data-ttu-id="6adbb-117">Este ejemplo puede transformar un documento muy grande a la vez que mantiene una pequeña superficie de memoria.</span><span class="sxs-lookup"><span data-stu-id="6adbb-117">This example can transform a very large document while maintaining a small memory footprint.</span></span>  
  
 <span data-ttu-id="6adbb-118">Observe que se escribe el eje personalizado (`StreamCustomerItem`) específicamente para que espere un documento que tiene los elementos `Customer`, `Name` e `Item`, y que esos elementos se organizarán como en el documento Source.xml siguiente.</span><span class="sxs-lookup"><span data-stu-id="6adbb-118">Note that the custom axis (`StreamCustomerItem`) is specifically written so that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the following Source.xml document.</span></span> <span data-ttu-id="6adbb-119">No obstante, una implementación más sólida estaría preparada para analizar un documento no válido.</span><span class="sxs-lookup"><span data-stu-id="6adbb-119">A more robust implementation, however, would be prepared to parse an invalid document.</span></span>  
  
 <span data-ttu-id="6adbb-120">A continuación, se muestra el documento de origen, Source.xml:</span><span class="sxs-lookup"><span data-stu-id="6adbb-120">The following is the source document, Source.xml:</span></span>  
  
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
  
```vb  
Module Module1  
    Sub Main()  
        Dim root = New XStreamingElement("Root",  
            From el In New StreamCustomerItem("Source.xml")  
            Select <Item>  
                       <Customer><%= el.Parent.<Name>.Value %></Customer>  
                       <%= el.<Key> %>  
                   </Item>  
            )  
        root.Save("Test.xml")  
        Console.WriteLine(My.Computer.FileSystem.ReadAllText("Test.xml"))  
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
  
 <span data-ttu-id="6adbb-121">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="6adbb-121">This code produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0001</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0002</Key>  
  </Item>  
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
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0008</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0009</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0010</Key>  
  </Item>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="6adbb-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6adbb-122">Example</span></span>  
 <span data-ttu-id="6adbb-123">En el ejemplo siguiente también se basa en el ejemplo de [Cómo: transmitir fragmentos XML con acceso a](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md)información de encabezado (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="6adbb-123">The following example also builds on the example in [How to: Stream XML Fragments with Access to Header Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md).</span></span>  
  
 <span data-ttu-id="6adbb-124">Este ejemplo utiliza la capacidad de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] para escribir elementos en un <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="6adbb-124">This example uses the capability of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to write elements to an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="6adbb-125">Este ejemplo puede transformar un documento muy grande a la vez que mantiene una pequeña superficie de memoria.</span><span class="sxs-lookup"><span data-stu-id="6adbb-125">This example can transform a very large document while maintaining a small memory footprint.</span></span>  
  
 <span data-ttu-id="6adbb-126">Observe que se escribe el eje personalizado (`StreamCustomerItem`) específicamente para que espere un documento que tiene los elementos `Customer`, `Name` e `Item`, y que esos elementos se organizarán como en el documento Source.xml siguiente.</span><span class="sxs-lookup"><span data-stu-id="6adbb-126">Note that the custom axis (`StreamCustomerItem`) is specifically written so that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the following Source.xml document.</span></span> <span data-ttu-id="6adbb-127">Una implementación más sólida, sin embargo, validaría el documento de origen con XSD o se prepararía para analizar un documento no válido.</span><span class="sxs-lookup"><span data-stu-id="6adbb-127">A more robust implementation, however, would either validate the source document with an XSD, or would be prepared to parse an invalid document.</span></span>  
  
 <span data-ttu-id="6adbb-128">Este ejemplo utiliza el mismo documento de origen, Source.xml, que el ejemplo anterior de este tema.</span><span class="sxs-lookup"><span data-stu-id="6adbb-128">This example uses the same source document, Source.xml, as the previous example in this topic.</span></span> <span data-ttu-id="6adbb-129">También produce exactamente el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="6adbb-129">It also produces exactly the same output.</span></span>  
  
 <span data-ttu-id="6adbb-130">Se prefiere usar la clase <xref:System.Xml.Linq.XStreamingElement> para la transmisión por secuencias de la salida XML a sobrescribir una clase <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="6adbb-130">Using <xref:System.Xml.Linq.XStreamingElement> for streaming the output XML is preferred over writing to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim srcTree =  
            From el In New StreamCustomerItem("Source.xml")  
            Select <Item>  
                       <Customer><%= el.Parent.<Name>.Value %></Customer>  
                       <%= el.<Key> %>  
                   </Item>  
  
        Dim xws = New Xml.XmlWriterSettings()  
        xws.OmitXmlDeclaration = True  
        xws.Indent = True  
        Using xw = Xml.XmlWriter.Create("Output.xml", xws)  
            xw.WriteStartElement("Root")  
            For Each el In srcTree  
                el.WriteTo(xw)  
            Next  
            xw.WriteEndElement()  
        End Using  
  
        Dim s = My.Computer.FileSystem.ReadAllText("Output.xml")  
        Console.WriteLine(s)  
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
  
 <span data-ttu-id="6adbb-131">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="6adbb-131">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0001</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0002</Key>  
  </Item>  
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
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0008</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0009</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0010</Key>  
  </Item>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6adbb-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6adbb-132">See also</span></span>

- [<span data-ttu-id="6adbb-133">Programación avanzada de LINQ to XMLLINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6adbb-133">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
