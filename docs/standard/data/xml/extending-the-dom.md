---
title: Extender DOM
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b5489c96-4afd-439a-a25d-fc82eb4a148d
ms.openlocfilehash: 173d36f534f951cfafefd3bd69b7ab245d575747
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829510"
---
# <a name="extending-the-dom"></a><span data-ttu-id="62b16-102">Extender DOM</span><span class="sxs-lookup"><span data-stu-id="62b16-102">Extending the DOM</span></span>

<span data-ttu-id="62b16-103">Microsoft .NET Framework incluye un conjunto básico de clases que proporcionan una implementación de Document Object Model (DOM) XML.</span><span class="sxs-lookup"><span data-stu-id="62b16-103">The Microsoft .NET Framework includes a base set of classes that provides an implementation of the XML Document Object Model (DOM).</span></span> <span data-ttu-id="62b16-104"><xref:System.Xml.XmlNode> y sus clases derivadas proporcionan métodos y propiedades que permiten navegar, consultar y modificar el contenido y la estructura de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="62b16-104">The <xref:System.Xml.XmlNode>, and its derived classes, provides methods and properties that allow you to navigate, query, and modify the content and structure of an XML document.</span></span>

<span data-ttu-id="62b16-105">Cuando se carga el contenido XML en la memoria mediante DOM, los nodos creados contienen información como el nombre y el tipo de nodo, entre otros datos.</span><span class="sxs-lookup"><span data-stu-id="62b16-105">When XML content is loaded into memory using the DOM, the nodes created contain information such as node name, node type, and so on.</span></span> <span data-ttu-id="62b16-106">Puede haber ocasiones en las que necesite información de nodo específica que no proporcionan las clases base.</span><span class="sxs-lookup"><span data-stu-id="62b16-106">There may be occasions where you require specific node information that the base classes do not provide.</span></span> <span data-ttu-id="62b16-107">Por ejemplo, es posible que desee conocer el número de línea y posición del nodo.</span><span class="sxs-lookup"><span data-stu-id="62b16-107">For example, you may want to see the line number and position of the node.</span></span> <span data-ttu-id="62b16-108">En este caso, puede derivar clases nuevas de las clases DOM existentes y agregar funcionalidad adicional.</span><span class="sxs-lookup"><span data-stu-id="62b16-108">In this case, you can derive new classes from the existing DOM classes and add additional functionality.</span></span>

<span data-ttu-id="62b16-109">Al derivar clases nuevas hay que seguir dos directrices generales:</span><span class="sxs-lookup"><span data-stu-id="62b16-109">There are two general guidelines when deriving new classes:</span></span>

- <span data-ttu-id="62b16-110">Se recomienda no derivar nunca desde la clase <xref:System.Xml.XmlNode>.</span><span class="sxs-lookup"><span data-stu-id="62b16-110">It is recommended that you never derive from the <xref:System.Xml.XmlNode> class.</span></span> <span data-ttu-id="62b16-111">En su lugar, se aconseja derivar clases desde la clase que corresponda al tipo de nodo en el que esté interesado.</span><span class="sxs-lookup"><span data-stu-id="62b16-111">Instead, it is recommended that you derive classes from the class corresponding to the node type that you are interested in.</span></span> <span data-ttu-id="62b16-112">Por ejemplo, si desea devolver información adicional sobre nodos de atributo, puede derivar desde la clase <xref:System.Xml.XmlAttribute>.</span><span class="sxs-lookup"><span data-stu-id="62b16-112">For example, if you want to return additional information on attribute nodes, you can derive from the <xref:System.Xml.XmlAttribute> class.</span></span>

- <span data-ttu-id="62b16-113">Excepto en los métodos de creación de nodos, se recomienda que al invalidar una función, llame siempre a la versión base de la misma y, a continuación, agregue el procesamiento adicional.</span><span class="sxs-lookup"><span data-stu-id="62b16-113">Except for the node creation methods, it is recommended that when overriding a function, you should always call the base version of the function and then add any additional processing.</span></span>

## <a name="creating-your-own-node-instances"></a><span data-ttu-id="62b16-114">Crear sus propias instancias de nodo</span><span class="sxs-lookup"><span data-stu-id="62b16-114">Creating Your Own Node Instances</span></span>

<span data-ttu-id="62b16-115">La clase <xref:System.Xml.XmlDocument> contiene métodos de creación de nodos.</span><span class="sxs-lookup"><span data-stu-id="62b16-115">The <xref:System.Xml.XmlDocument> class contains node creation methods.</span></span> <span data-ttu-id="62b16-116">Cuando se carga un archivo XML, se llama a estos métodos para crear los nodos.</span><span class="sxs-lookup"><span data-stu-id="62b16-116">When an XML file is loaded, these methods are called to create the nodes.</span></span> <span data-ttu-id="62b16-117">Se pueden invalidar los métodos de forma que sus instancias de nodo se creen al cargar un documento.</span><span class="sxs-lookup"><span data-stu-id="62b16-117">You can override these methods so that your node instances are created when a document is loaded.</span></span> <span data-ttu-id="62b16-118">Por ejemplo, si ha extendido la clase <xref:System.Xml.XmlElement>, heredará la clase <xref:System.Xml.XmlDocument> e invalidará el método <xref:System.Xml.XmlDocument.CreateElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="62b16-118">For example, if you have extended the <xref:System.Xml.XmlElement> class, you would inherit the <xref:System.Xml.XmlDocument> class and override the <xref:System.Xml.XmlDocument.CreateElement%2A> method.</span></span>

<span data-ttu-id="62b16-119">En el ejemplo siguiente se muestra cómo invalidar el método <xref:System.Xml.XmlDocument.CreateElement%2A>para devolver su implementación de la clase <xref:System.Xml.XmlElement>.</span><span class="sxs-lookup"><span data-stu-id="62b16-119">The following example shows how to override the <xref:System.Xml.XmlDocument.CreateElement%2A> method to return your implementation of the <xref:System.Xml.XmlElement> class.</span></span>

```vb
Class LineInfoDocument
    Inherits XmlDocument
        Public Overrides Function CreateElement(prefix As String, localname As String, nsURI As String) As XmlElement
        Dim elem As New LineInfoElement(prefix, localname, nsURI, Me)
        Return elem
    End Function 'CreateElement
End Class 'LineInfoDocument
```

```csharp
class LineInfoDocument : XmlDocument
{
    public override XmlElement CreateElement(string prefix, string localname, string nsURI)
    {
        LineInfoElement elem = new LineInfoElement(prefix, localname, nsURI, this);
        return elem;
    }
}
```

## <a name="extending-a-class"></a><span data-ttu-id="62b16-120">Extender una clase</span><span class="sxs-lookup"><span data-stu-id="62b16-120">Extending a Class</span></span>

<span data-ttu-id="62b16-121">Para extender una clase, derive su clase de una de las clases DOM existentes.</span><span class="sxs-lookup"><span data-stu-id="62b16-121">To extend a class, derive your class from one of the existing DOM classes.</span></span> <span data-ttu-id="62b16-122">Se puede invalidar cualquiera de los métodos virtuales o propiedades de la clase base, o bien agregar los suyos propios.</span><span class="sxs-lookup"><span data-stu-id="62b16-122">You can then override any of the virtual methods or properties in the base class, or add your own.</span></span>

<span data-ttu-id="62b16-123">En el ejemplo siguiente se crea una clase nueva, que implementa la clase <xref:System.Xml.XmlElement> y la interfaz <xref:System.Xml.IXmlLineInfo>.</span><span class="sxs-lookup"><span data-stu-id="62b16-123">In the following example, a new class is created, which implements the <xref:System.Xml.XmlElement> class and the <xref:System.Xml.IXmlLineInfo> interface.</span></span> <span data-ttu-id="62b16-124">Se definen métodos y propiedades adicionales que permiten a los usuarios recopilar información de línea.</span><span class="sxs-lookup"><span data-stu-id="62b16-124">Additional methods and properties are defined which allows users to gather line information.</span></span>

```vb
Class LineInfoElement
   Inherits XmlElement
   Implements IXmlLineInfo
   Private lineNumber As Integer = 0
   Private linePosition As Integer = 0

   Friend Sub New(prefix As String, localname As String, nsURI As String, doc As XmlDocument)
      MyBase.New(prefix, localname, nsURI, doc)
      CType(doc, LineInfoDocument).IncrementElementCount()
   End Sub

   Public Sub SetLineInfo(linenum As Integer, linepos As Integer)
      lineNumber = linenum
      linePosition = linepos
   End Sub

   Public ReadOnly Property LineNumber() As Integer
      Get
         Return lineNumber
      End Get
   End Property

   Public ReadOnly Property LinePosition() As Integer
      Get
         Return linePosition
      End Get
   End Property

   Public Function HasLineInfo() As Boolean
      Return True
   End Function
End Class ' End LineInfoElement class.
```

```csharp
class LineInfoElement : XmlElement, IXmlLineInfo {
   int lineNumber = 0;
   int linePosition = 0;
   internal LineInfoElement( string prefix, string localname, string nsURI, XmlDocument doc ) : base( prefix, localname, nsURI, doc ) {
       ( (LineInfoDocument)doc ).IncrementElementCount();
  }
  public void SetLineInfo( int linenum, int linepos ) {
      lineNumber = linenum;
      linePosition = linepos;
  }
  public int LineNumber {
     get {
       return lineNumber;
     }
  }
  public int LinePosition {
      get {
        return linePosition;
      }
  }
  public bool HasLineInfo() {
    return true;
  }
} // End LineInfoElement class.
```

### <a name="example"></a><span data-ttu-id="62b16-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="62b16-125">Example</span></span>

<span data-ttu-id="62b16-126">En el ejemplo siguiente se cuenta el número de elementos de un documento XML:</span><span class="sxs-lookup"><span data-stu-id="62b16-126">The following example counts the number of elements in an XML document:</span></span>

```vb
Imports System.Xml
Imports System.IO

Class LineInfoDocument
   Inherits XmlDocument

   Private elementCount As Integer

   Friend Sub New()
      elementCount = 0
   End Sub

   Public Overrides Function CreateElement(prefix As String, localname As String, nsURI As String) As XmlElement
      Dim elem As New LineInfoElement(prefix, localname, nsURI, Me)
      Return elem
   End Function

   Public Sub IncrementElementCount()
      elementCount += 1
   End Sub

   Public Function GetCount() As Integer
      Return elementCount
   End Function
End Class 'End LineInfoDocument class.

Class LineInfoElement
   Inherits XmlElement

   Friend Sub New(prefix As String, localname As String, nsURI As String, doc As XmlDocument)
      MyBase.New(prefix, localname, nsURI, doc)
      CType(doc, LineInfoDocument).IncrementElementCount()
   End Sub 'New
End Class 'LineInfoElement
 _ 'End LineInfoElement class.

Public Class Test

   Private filename As [String] = "book.xml"

   Public Shared Sub Main()

      Dim doc As New LineInfoDocument()
      doc.Load(filename)
      Console.WriteLine("Number of elements in {0}: {1}", filename, doc.GetCount())
   End Sub
End Class
```

```csharp
using System;
using System.Xml;
using System.IO;

class LineInfoDocument : XmlDocument {

  int elementCount;
  internal LineInfoDocument():base() {
    elementCount = 0;
  }

  public override XmlElement CreateElement( string prefix, string localname, string nsURI) {
    LineInfoElement elem = new LineInfoElement(prefix, localname, nsURI, this );
    return elem;
  }

  public void IncrementElementCount() {
     elementCount++;
  }

  public int GetCount() {
     return elementCount;
  }
} // End LineInfoDocument class.

class LineInfoElement:XmlElement {

    internal LineInfoElement( string prefix, string localname, string nsURI, XmlDocument doc ):base( prefix,localname,nsURI, doc ){
      ((LineInfoDocument)doc).IncrementElementCount();
    }
} // End LineInfoElement class.

public class Test {

  const String filename = "book.xml";
  public static void Main() {

     LineInfoDocument doc =new LineInfoDocument();
     doc.Load(filename);
     Console.WriteLine("Number of elements in {0}: {1}", filename, doc.GetCount());

  }
}
```

#### <a name="input"></a><span data-ttu-id="62b16-127">Entrada</span><span class="sxs-lookup"><span data-stu-id="62b16-127">Input</span></span>

<span data-ttu-id="62b16-128">book.xml</span><span class="sxs-lookup"><span data-stu-id="62b16-128">book.xml</span></span>

```xml
<!--sample XML fragment-->
<book genre='novel' ISBN='1-861001-57-5' misc='sale-item'>
  <title>The Handmaid's Tale</title>
  <price>14.95</price>
</book>
```

#### <a name="output"></a><span data-ttu-id="62b16-129">Salida</span><span class="sxs-lookup"><span data-stu-id="62b16-129">Output</span></span>

```console
Number of elements in book.xml: 3
```

## <a name="node-event-handler"></a><span data-ttu-id="62b16-130">Controlador de eventos de nodo</span><span class="sxs-lookup"><span data-stu-id="62b16-130">Node Event Handler</span></span>

<span data-ttu-id="62b16-131">La implementación .NET Framework de DOM incluye también un sistema de eventos que permite recibir y controlar eventos cuando se cambian nodos en un documento XML.</span><span class="sxs-lookup"><span data-stu-id="62b16-131">The .NET Framework implementation of the DOM also includes an event system that enables you to receive and handle events when nodes in an XML document change.</span></span> <span data-ttu-id="62b16-132">Mediante las clases <xref:System.Xml.XmlNodeChangedEventHandler> y <xref:System.Xml.XmlNodeChangedEventArgs>, puede capturar los eventos `NodeChanged`, `NodeChanging`, `NodeInserted`, `NodeInserting`, `NodeRemoved`, y `NodeRemoving`.</span><span class="sxs-lookup"><span data-stu-id="62b16-132">Using the <xref:System.Xml.XmlNodeChangedEventHandler> and <xref:System.Xml.XmlNodeChangedEventArgs> classes, you can capture `NodeChanged`, `NodeChanging`, `NodeInserted`, `NodeInserting`, `NodeRemoved`, and `NodeRemoving` events.</span></span>

<span data-ttu-id="62b16-133">El proceso de control de eventos funciona exactamente igual en las clases derivadas que en las clases DOM originales.</span><span class="sxs-lookup"><span data-stu-id="62b16-133">The event-handling process works exactly the same in derived classes as it would in the original DOM classes.</span></span>

<span data-ttu-id="62b16-134">Para obtener más información sobre el control de eventos de nodo, vea [Eventos](../../events/index.md) y <xref:System.Xml.XmlNodeChangedEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="62b16-134">For more information regarding node event handling, see [Events](../../events/index.md) and <xref:System.Xml.XmlNodeChangedEventHandler>.</span></span>

## <a name="default-attributes-and-the-createelement-method"></a><span data-ttu-id="62b16-135">Atributos predeterminados y el método CreateElement</span><span class="sxs-lookup"><span data-stu-id="62b16-135">Default Attributes and the CreateElement Method</span></span>

<span data-ttu-id="62b16-136">Si va a invalidar el método <xref:System.Xml.XmlDocument.CreateElement%2A> en una clase derivada, los atributos predeterminados no se agregan al crear elementos nuevos mientras se edita el documento.</span><span class="sxs-lookup"><span data-stu-id="62b16-136">If you are overriding the <xref:System.Xml.XmlDocument.CreateElement%2A> method in a derived class, default attributes are not added when you are creating new elements while editing the document.</span></span> <span data-ttu-id="62b16-137">Esto solo constituye un problema durante la edición.</span><span class="sxs-lookup"><span data-stu-id="62b16-137">This is only an issue while editing.</span></span> <span data-ttu-id="62b16-138">Puesto que el método <xref:System.Xml.XmlDocument.CreateElement%2A> es responsable de la adición de atributos predeterminados a un <xref:System.Xml.XmlDocument>, debe programar esta funcionalidad en dicho método <xref:System.Xml.XmlDocument.CreateElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="62b16-138">Because the <xref:System.Xml.XmlDocument.CreateElement%2A> method is responsible for adding default attributes to an <xref:System.Xml.XmlDocument>, you must code this functionality in the <xref:System.Xml.XmlDocument.CreateElement%2A> method.</span></span> <span data-ttu-id="62b16-139">Si va a cargar un <xref:System.Xml.XmlDocument> que incluye atributos predeterminados, se controlarán correctamente.</span><span class="sxs-lookup"><span data-stu-id="62b16-139">If you are loading an <xref:System.Xml.XmlDocument> that includes default attributes, they will be handled correctly.</span></span> <span data-ttu-id="62b16-140">Para obtener más información sobre los atributos predeterminados, vea [Crear nuevos atributos para elementos en DOM](creating-new-attributes-for-elements-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="62b16-140">For more information on default attributes, see [Creating New Attributes for Elements in the DOM](creating-new-attributes-for-elements-in-the-dom.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="62b16-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="62b16-141">See also</span></span>

- [<span data-ttu-id="62b16-142">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="62b16-142">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
