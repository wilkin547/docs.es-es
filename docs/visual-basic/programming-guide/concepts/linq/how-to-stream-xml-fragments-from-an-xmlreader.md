---
title: Procedimiento para hacer streaming de fragmentos XML desde un objeto XmlReader
ms.date: 07/20/2015
ms.assetid: f67ce598-4a12-4dcb-9a07-24deca02a111
ms.openlocfilehash: ff22625767c4e0752ca19d5a315395934b566230
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397705"
---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-visual-basic"></a><span data-ttu-id="cd2b6-102">Cómo: hacer streaming de fragmentos XML desde un objeto XmlReader (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd2b6-102">How to: Stream XML Fragments from an XmlReader (Visual Basic)</span></span>
<span data-ttu-id="cd2b6-103">Cuando deba procesar archivos XML grandes quizás no sea factible cargar la totalidad del árbol XML en memoria.</span><span class="sxs-lookup"><span data-stu-id="cd2b6-103">When you have to process large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="cd2b6-104">En este tema se muestra cómo transmitir por secuencias fragmentos usando <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="cd2b6-104">This topic shows how to stream fragments using an <xref:System.Xml.XmlReader>.</span></span>  
  
 <span data-ttu-id="cd2b6-105">Una de las formas más efectivas de usar <xref:System.Xml.XmlReader> para leer objetos <xref:System.Xml.Linq.XElement> es escribir un método de eje personalizado propio.</span><span class="sxs-lookup"><span data-stu-id="cd2b6-105">One of the most effective ways to use an <xref:System.Xml.XmlReader> to read <xref:System.Xml.Linq.XElement> objects is to write your own custom axis method.</span></span> <span data-ttu-id="cd2b6-106">Un método de eje suele devolver una recopilación como <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement>, tal y como se muestra en el ejemplo de este tema.</span><span class="sxs-lookup"><span data-stu-id="cd2b6-106">An axis method typically returns a collection such as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, as shown in the example in this topic.</span></span> <span data-ttu-id="cd2b6-107">En el método de eje personalizado, tras crear el fragmento XML llamando al método <xref:System.Xml.Linq.XNode.ReadFrom%2A>, devuelva la recopilación usando `yield return`.</span><span class="sxs-lookup"><span data-stu-id="cd2b6-107">In the custom axis method, after you create the XML fragment by calling the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method, return the collection using `yield return`.</span></span> <span data-ttu-id="cd2b6-108">Esto proporciona semántica de ejecución aplazada al método de eje personalizado.</span><span class="sxs-lookup"><span data-stu-id="cd2b6-108">This provides deferred execution semantics to your custom axis method.</span></span>  
  
 <span data-ttu-id="cd2b6-109">Cuando crea un árbol XML de un objeto <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlReader> debe estar posicionado en un elemento.</span><span class="sxs-lookup"><span data-stu-id="cd2b6-109">When you create an XML tree from an <xref:System.Xml.XmlReader> object, the <xref:System.Xml.XmlReader> must be positioned on an element.</span></span> <span data-ttu-id="cd2b6-110">El método <xref:System.Xml.Linq.XNode.ReadFrom%2A> no vuelve hasta que ha leído la etiqueta de cierre del elemento.</span><span class="sxs-lookup"><span data-stu-id="cd2b6-110">The <xref:System.Xml.Linq.XNode.ReadFrom%2A> method does not return until it has read the close tag of the element.</span></span>  
  
 <span data-ttu-id="cd2b6-111">Si desea crear un árbol parcial, puede crear una instancia de un <xref:System.Xml.XmlReader>, colocar el lector en el nodo que desea convertir a un árbol <xref:System.Xml.Linq.XElement> y después crear el objeto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="cd2b6-111">If you want to create a partial tree, you can instantiate an <xref:System.Xml.XmlReader>, position the reader on the node that you want to convert to an <xref:System.Xml.Linq.XElement> tree, and then create the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
 <span data-ttu-id="cd2b6-112">El tema [Cómo: hacer streaming de fragmentos XML con acceso a la información de encabezado (Visual Basic)](how-to-stream-xml-fragments-with-access-to-header-information.md) contiene información y un ejemplo sobre cómo transmitir un documento más complejo.</span><span class="sxs-lookup"><span data-stu-id="cd2b6-112">The topic [How to: Stream XML Fragments with Access to Header Information (Visual Basic)](how-to-stream-xml-fragments-with-access-to-header-information.md) contains information and an example on how to stream a more complex document.</span></span>  
  
 <span data-ttu-id="cd2b6-113">El tema [Cómo: realizar una transformación de transmisión por secuencias de documentos XML grandes (Visual Basic)](how-to-perform-streaming-transform-of-large-xml-documents.md) contiene un ejemplo del uso de LINQ to XML para transformar documentos XML extremadamente grandes manteniendo una superficie de memoria pequeña.</span><span class="sxs-lookup"><span data-stu-id="cd2b6-113">The topic [How to: Perform Streaming Transform of Large XML Documents (Visual Basic)](how-to-perform-streaming-transform-of-large-xml-documents.md) contains an example of using LINQ to XML to transform extremely large XML documents while maintaining a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd2b6-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cd2b6-114">Example</span></span>  
 <span data-ttu-id="cd2b6-115">Este ejemplo crea un método de eje personalizado.</span><span class="sxs-lookup"><span data-stu-id="cd2b6-115">This example creates a custom axis method.</span></span> <span data-ttu-id="cd2b6-116">Puede consultarlo usando una consulta de LINQ.</span><span class="sxs-lookup"><span data-stu-id="cd2b6-116">You can query it by using a LINQ query.</span></span> <span data-ttu-id="cd2b6-117">El método de eje personalizado, `StreamRootChildDoc`, es un método que está específicamente diseñado para leer un documento que tiene un elemento `Child` que se repite.</span><span class="sxs-lookup"><span data-stu-id="cd2b6-117">The custom axis method, `StreamRootChildDoc`, is a method that is designed specifically to read a document that has a repeating `Child` element.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim markup = "<Root>" &  
                     "  <Child Key=""01"">" &  
                     "    <GrandChild>aaa</GrandChild>" &  
                     "  </Child>" &  
                     "  <Child Key=""02"">" &  
                     "    <GrandChild>bbb</GrandChild>" &  
                     "  </Child>" &  
                     "  <Child Key=""03"">" &  
                     "    <GrandChild>ccc</GrandChild>" &  
                     "  </Child>" &  
                     "</Root>"  
  
        Dim grandChildData =  
             From el In New StreamRootChildDoc(New IO.StringReader(markup))  
             Where CInt(el.@Key) > 1  
             Select el.<GrandChild>.Value  
  
        For Each s In grandChildData  
            Console.WriteLine(s)  
        Next  
    End Sub  
End Module  
  
Public Class StreamRootChildDoc  
    Implements IEnumerable(Of XElement)  
  
    Private _stringReader As IO.StringReader  
  
    Public Sub New(ByVal stringReader As IO.StringReader)  
        _stringReader = stringReader  
    End Sub  
  
    Public Function GetEnumerator() As IEnumerator(Of XElement) Implements IEnumerable(Of XElement).GetEnumerator  
        Return New StreamChildEnumerator(_stringReader)  
    End Function  
  
    Public Function GetEnumerator1() As IEnumerator Implements IEnumerable.GetEnumerator  
        Return Me.GetEnumerator()  
    End Function  
End Class  
  
Public Class StreamChildEnumerator  
    Implements IEnumerator(Of XElement)  
  
    Private _current As XElement  
    Private _reader As Xml.XmlReader  
    Private _stringReader As IO.StringReader  
  
    Public Sub New(ByVal stringReader As IO.StringReader)  
        _stringReader = stringReader  
        _reader = Xml.XmlReader.Create(_stringReader)  
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
        While _reader.Read()  
            Select Case _reader.NodeType  
                Case Xml.XmlNodeType.Element  
                    Dim el = TryCast(XElement.ReadFrom(_reader), XElement)  
                    If el IsNot Nothing Then  
                        _current = el  
                        Return True  
                    End If  
            End Select  
        End While  
  
        Return False  
    End Function  
  
    Public Sub Reset() Implements IEnumerator.Reset  
        _reader = Xml.XmlReader.Create(_stringReader)  
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
  
 <span data-ttu-id="cd2b6-118">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="cd2b6-118">This example produces the following output:</span></span>  
  
```console  
bbb  
ccc  
```  
  
 <span data-ttu-id="cd2b6-119">En este ejemplo el documento de origen es muy pequeño.</span><span class="sxs-lookup"><span data-stu-id="cd2b6-119">In this example, the source document is very small.</span></span> <span data-ttu-id="cd2b6-120">No obstante, aunque hubiera millones de elementos `Child`, este ejemplo seguiría teniendo una superficie de memoria pequeña.</span><span class="sxs-lookup"><span data-stu-id="cd2b6-120">However, even if there were millions of `Child` elements, this example would still have a small memory footprint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd2b6-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd2b6-121">See also</span></span>

- [<span data-ttu-id="cd2b6-122">Tutorial: Implementar IEnumerable(Of T) en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cd2b6-122">Walkthrough: Implementing IEnumerable(Of T) in Visual Basic</span></span>](../../language-features/control-flow/walkthrough-implementing-ienumerable-of-t.md)
- [<span data-ttu-id="cd2b6-123">Analizar XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd2b6-123">Parsing XML (Visual Basic)</span></span>](parsing-xml.md)
