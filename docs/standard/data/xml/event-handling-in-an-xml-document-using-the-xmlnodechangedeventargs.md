---
title: Controlar eventos en un documento XML mediante XmlNodeChangedEventArgs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 0fe844e3-5b6f-4fe7-ad15-22459501738b
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cc74b13fd4771cc4f00500ff3253795f45db2b40
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs"></a><span data-ttu-id="e537c-102">Controlar eventos en un documento XML mediante XmlNodeChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="e537c-102">Event Handling in an XML Document Using the XmlNodeChangedEventArgs</span></span>
<span data-ttu-id="e537c-103">**XmlNodeChangedEventArgs** encapsula los argumentos que se pasan a los controladores de eventos registrados en el objeto **XmlDocument** para controlar eventos.</span><span class="sxs-lookup"><span data-stu-id="e537c-103">The **XmlNodeChangedEventArgs** encapsulates the arguments passed to the event handlers registered on the **XmlDocument** object for handling events.</span></span> <span data-ttu-id="e537c-104">En la tabla siguiente se proporcionan los eventos y una descripción de cuándo se activan.</span><span class="sxs-lookup"><span data-stu-id="e537c-104">The events and a description of when they are fired is given in the following table.</span></span>  
  
|<span data-ttu-id="e537c-105">evento</span><span class="sxs-lookup"><span data-stu-id="e537c-105">Event</span></span>|<span data-ttu-id="e537c-106">Se activa</span><span class="sxs-lookup"><span data-stu-id="e537c-106">Fired</span></span>|  
|-----------|-----------|  
|<xref:System.Xml.XmlDocument.NodeInserting>|<span data-ttu-id="e537c-107">Cuando un nodo que pertenece al documento actual se va a insertar en otro nodo.</span><span class="sxs-lookup"><span data-stu-id="e537c-107">When a node belonging to the current document is about to be inserted into another node.</span></span>|  
|<xref:System.Xml.XmlDocument.NodeInserted>|<span data-ttu-id="e537c-108">Cuando un nodo que pertenece al documento actual se ha insertado en otro nodo.</span><span class="sxs-lookup"><span data-stu-id="e537c-108">When a node belonging to the current document has been inserted into another node.</span></span>|  
|<xref:System.Xml.XmlDocument.NodeRemoving>|<span data-ttu-id="e537c-109">Cuando un nodo que pertenece a este documento se va a quitar del documento.</span><span class="sxs-lookup"><span data-stu-id="e537c-109">When a node belonging to this document is about to be removed from the document.</span></span>|  
|<xref:System.Xml.XmlDocument.NodeRemoved>|<span data-ttu-id="e537c-110">Cuando un nodo que pertenece a este documento se ha quitado de su nodo primario.</span><span class="sxs-lookup"><span data-stu-id="e537c-110">When a node belonging to this document has been removed from its parent.</span></span>|  
|<xref:System.Xml.XmlDocument.NodeChanging>|<span data-ttu-id="e537c-111">Cuando se va a cambiar el valor de un nodo.</span><span class="sxs-lookup"><span data-stu-id="e537c-111">When the value of a node is about to be changed.</span></span>|  
|<xref:System.Xml.XmlDocument.NodeChanged>|<span data-ttu-id="e537c-112">Cuando se ha cambiado el valor de un nodo.</span><span class="sxs-lookup"><span data-stu-id="e537c-112">When the value of a node has been changed.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="e537c-113">Si el uso de la memoria de **XmlDataDocument** está totalmente optimizado para utilizar el almacenamiento **DataSet**, **XmlDataDocument** puede no generar ninguno de los eventos enumerados anteriormente si los cambios se realizan en la clase **DataSet** subyacente.</span><span class="sxs-lookup"><span data-stu-id="e537c-113">If the **XmlDataDocument** memory usage is fully optimized to use **DataSet** storage, the **XmlDataDocument** might not raise any of the events listed above when changes are made to the underlying **DataSet**.</span></span> <span data-ttu-id="e537c-114">Si necesita estos eventos, deberá recorrer el objeto **XmlDocument** para hacer que la memoria no esté totalmente optimizada.</span><span class="sxs-lookup"><span data-stu-id="e537c-114">If you need these events, you must traverse the whole **XmlDocument** once to make the memory usage non-fully optimized.</span></span>  
  
 <span data-ttu-id="e537c-115">En el ejemplo de código siguiente se muestra cómo definir un controlador de eventos y cómo agregarlo a un evento.</span><span class="sxs-lookup"><span data-stu-id="e537c-115">The following code example shows how to define an event handler and how to add the event handler to an event.</span></span>  
  
```vb  
' Attach the event handler, NodeInsertedHandler, to the NodeInserted  
' event.  
Dim doc as XmlDocument = new XmlDocument()  
Dim XmlNodeChgEHdlr as XmlNodeChangedEventHandler = new XmlNodeChangedEventHandler(addressof MyNodeChangedEvent)   
AddHandler doc.NodeInserted, XmlNodeChgEHdlr   
  
Dim n as XmlNode = doc.CreateElement( "element" )  
Console.WriteLine( "Before Event Inserting" )   
  
' This is the point where the new node is being inserted in the tree,  
' and this is the point where the NodeInserted event is raised.  
doc.AppendChild( n )  
Console.WriteLine( "After Event Inserting" )   
  
' Define the event handler that handles the NodeInserted event.  
sub NodeInsertedHandler(src as Object, args as XmlNodeChangedEventArgs)  
    Console.WriteLine("Node " + args.Node.Name + " inserted!!")  
end sub  
```  
  
```csharp  
// Attach the event handler, NodeInsertedHandler, to the NodeInserted  
// event.  
XmlDocument doc = new XmlDocument();  
doc.NodeInserted += new XmlNodeChangedEventHandler(NodeInsertedHandler);  
XmlNode n = doc.CreateElement( "element" );  
Console.WriteLine( "Before Event Inserting" );  
  
// This is the point where the new node is being inserted in the tree,  
// and this is the point where the NodeInserted event is raised.  
doc.AppendChild( n );  
Console.WriteLine( "After Event Inserting" );   
  
// Define the event handler that handles the NodeInserted event.  
void NodeInsertedHandler(Object src, XmlNodeChangedEventArgs args)  
{  
    Console.WriteLine("Node " + args.Node.Name + " inserted!!");  
}  
```  
  
 <span data-ttu-id="e537c-116">Algunas operaciones del Modelo de objetos de documento (DOM) son compuestas y pueden dar como resultado la activación de varios eventos.</span><span class="sxs-lookup"><span data-stu-id="e537c-116">Some XML Document Object Model (DOM) operations are compound operations that can result in multiple events being fired.</span></span> <span data-ttu-id="e537c-117">Por ejemplo, puede que **AppendChild** tenga que quitar el nodo que se ha anexado de su nodo primario anterior.</span><span class="sxs-lookup"><span data-stu-id="e537c-117">For example, **AppendChild** may also have to remove the node being appended from its previous parent.</span></span> <span data-ttu-id="e537c-118">En este caso, verá la activación del evento **NodeRemoved** primero, seguida por un evento **NodeInserted**.</span><span class="sxs-lookup"><span data-stu-id="e537c-118">In this case, you see a **NodeRemoved** event fired first, followed by a **NodeInserted** event.</span></span> <span data-ttu-id="e537c-119">Algunas operaciones como la configuración de **InnerXml** pueden dar como resultado varios eventos.</span><span class="sxs-lookup"><span data-stu-id="e537c-119">Operations like setting **InnerXml** could result in multiple events.</span></span>  
  
 <span data-ttu-id="e537c-120">En el ejemplo de código siguiente se muestra la creación del controlador de eventos y el control del evento **NodeInserted**.</span><span class="sxs-lookup"><span data-stu-id="e537c-120">The following code example shows the creation of the event handler and the handling of the **NodeInserted** event.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports Microsoft.VisualBasic  
  
Public Class Sample  
  
    Private Const filename As String = "books.xml"  
  
    Shared Sub Main()  
        Dim mySample As Sample = New Sample()  
        mySample.Run(filename)  
    End Sub  
  
    Public Sub Run(ByVal args As String)  
        ' Create and load the XML document.  
        Console.WriteLine("Loading file 0 ...", args)  
        Dim doc As XmlDocument = New XmlDocument()  
        doc.Load(args)  
  
        ' Create the event handlers.  
        Dim XmlNodeChgEHdlr As XmlNodeChangedEventHandler = New XmlNodeChangedEventHandler(AddressOf MyNodeChangedEvent)  
        Dim XmlNodeInsrtEHdlr As XmlNodeChangedEventHandler = New XmlNodeChangedEventHandler(AddressOf MyNodeInsertedEvent)  
        AddHandler doc.NodeChanged, XmlNodeChgEHdlr  
        AddHandler doc.NodeInserted, XmlNodeInsrtEHdlr  
  
        ' Change the book price.  
        doc.DocumentElement.LastChild.InnerText = "5.95"  
  
        ' Add a new element.  
        Dim newElem As XmlElement = doc.CreateElement("style")  
        newElem.InnerText = "hardcover"  
        doc.DocumentElement.AppendChild(newElem)  
  
        Console.WriteLine(Chr(13) + Chr(10) + "Display the modified XML...")  
        Console.WriteLine(doc.OuterXml)  
    End Sub  
  
    ' Handle the NodeChanged event.  
    Public Sub MyNodeChangedEvent(ByVal src As Object, ByVal args As XmlNodeChangedEventArgs)  
        Console.Write("Node Changed Event: <0> changed", args.Node.Name)  
        If Not (args.Node.Value Is Nothing) Then  
            Console.WriteLine(" with value  0", args.Node.Value)  
        Else  
            Console.WriteLine("")  
        End If  
    End Sub  
  
    ' Handle the NodeInserted event.  
    Public Sub MyNodeInsertedEvent(ByVal src As Object, ByVal args As XmlNodeChangedEventArgs)  
        Console.Write("Node Inserted Event: <0> inserted", args.Node.Name)  
        If Not (args.Node.Value Is Nothing) Then  
            Console.WriteLine(" with value 0", args.Node.Value)  
        Else  
            Console.WriteLine("")  
        End If  
    End Sub  
  
End Class        ' End class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
  private const String filename = "books.xml";  
  
  public static void Main()  
  {  
     Sample mySample = new Sample();  
     mySample.Run(filename);  
  }  
  
  public void Run(String args)  
  {  
  
     // Create and load the XML document.  
     Console.WriteLine ("Loading file {0} ...", args);  
     XmlDocument doc = new XmlDocument();  
     doc.Load (args);  
  
     // Create the event handlers.  
     doc.NodeChanged += new XmlNodeChangedEventHandler(this.MyNodeChangedEvent);  
     doc.NodeInserted += new XmlNodeChangedEventHandler(this.MyNodeInsertedEvent);  
  
     // Change the book price.  
     doc.DocumentElement.LastChild.InnerText = "5.95";  
  
     // Add a new element.  
     XmlElement newElem = doc.CreateElement("style");  
     newElem.InnerText = "hardcover";  
     doc.DocumentElement.AppendChild(newElem);  
  
     Console.WriteLine("\r\nDisplay the modified XML...");  
     Console.WriteLine(doc.OuterXml);             
  
  }  
  
  // Handle the NodeChanged event.  
  public void MyNodeChangedEvent(Object src, XmlNodeChangedEventArgs args)  
  {  
     Console.Write("Node Changed Event: <{0}> changed", args.Node.Name);  
     if (args.Node.Value != null)  
     {  
        Console.WriteLine(" with value  {0}", args.Node.Value);  
     }  
     else  
       Console.WriteLine("");  
  }  
  
  // Handle the NodeInserted event.  
  public void MyNodeInsertedEvent(Object src, XmlNodeChangedEventArgs args)  
  {  
     Console.Write("Node Inserted Event: <{0}> inserted", args.Node.Name);  
     if (args.Node.Value != null)  
     {  
        Console.WriteLine(" with value {0}", args.Node.Value);  
     }  
     else  
        Console.WriteLine("");  
  }  
  
} // End class   
```  
  
 <span data-ttu-id="e537c-121">Para obtener más información, consulte <xref:System.Xml.XmlNodeChangedEventArgs> y <xref:System.Xml.XmlNodeChangedEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="e537c-121">For more information, see <xref:System.Xml.XmlNodeChangedEventArgs> and <xref:System.Xml.XmlNodeChangedEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e537c-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e537c-122">See Also</span></span>  
 [<span data-ttu-id="e537c-123">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="e537c-123">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
