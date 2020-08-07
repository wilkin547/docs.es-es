---
title: Streaming de fragmentos XML desde un objeto XmlReader (C#)
description: Aprenda a transmitir fragmentos XML dese un objeto XmlReader. Este método se utiliza para procesar archivos XML de gran tamaño.
ms.date: 07/20/2015
ms.assetid: 4a8f0e45-768a-42e2-bc5f-68bdf0e0a726
ms.openlocfilehash: e35322724712816180d48c1957719cf87079aedd
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301026"
---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-c"></a><span data-ttu-id="66856-104">Streaming de fragmentos XML desde un objeto XmlReader (C#)</span><span class="sxs-lookup"><span data-stu-id="66856-104">How to stream XML fragments from an XmlReader (C#)</span></span>

<span data-ttu-id="66856-105">Cuando deba procesar archivos XML grandes quizás no sea factible cargar la totalidad del árbol XML en memoria.</span><span class="sxs-lookup"><span data-stu-id="66856-105">When you have to process large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="66856-106">En este tema se muestra cómo transmitir por secuencias fragmentos usando <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="66856-106">This topic shows how to stream fragments using an <xref:System.Xml.XmlReader>.</span></span>  
  
 <span data-ttu-id="66856-107">Una de las formas más efectivas de usar <xref:System.Xml.XmlReader> para leer objetos <xref:System.Xml.Linq.XElement> es escribir un método de eje personalizado propio.</span><span class="sxs-lookup"><span data-stu-id="66856-107">One of the most effective ways to use an <xref:System.Xml.XmlReader> to read <xref:System.Xml.Linq.XElement> objects is to write your own custom axis method.</span></span> <span data-ttu-id="66856-108">Un método de eje suele devolver una recopilación como <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement>, tal y como se muestra en el ejemplo de este tema.</span><span class="sxs-lookup"><span data-stu-id="66856-108">An axis method typically returns a collection such as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, as shown in the example in this topic.</span></span> <span data-ttu-id="66856-109">En el método de eje personalizado, tras crear el fragmento XML llamando al método <xref:System.Xml.Linq.XNode.ReadFrom%2A>, devuelva la recopilación usando `yield return`.</span><span class="sxs-lookup"><span data-stu-id="66856-109">In the custom axis method, after you create the XML fragment by calling the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method, return the collection using `yield return`.</span></span> <span data-ttu-id="66856-110">Esto proporciona semántica de ejecución aplazada al método de eje personalizado.</span><span class="sxs-lookup"><span data-stu-id="66856-110">This provides deferred execution semantics to your custom axis method.</span></span>  
  
 <span data-ttu-id="66856-111">Cuando crea un árbol XML de un objeto <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlReader> debe estar posicionado en un elemento.</span><span class="sxs-lookup"><span data-stu-id="66856-111">When you create an XML tree from an <xref:System.Xml.XmlReader> object, the <xref:System.Xml.XmlReader> must be positioned on an element.</span></span> <span data-ttu-id="66856-112">El método <xref:System.Xml.Linq.XNode.ReadFrom%2A> no vuelve hasta que ha leído la etiqueta de cierre del elemento.</span><span class="sxs-lookup"><span data-stu-id="66856-112">The <xref:System.Xml.Linq.XNode.ReadFrom%2A> method does not return until it has read the close tag of the element.</span></span>  
  
 <span data-ttu-id="66856-113">Si desea crear un árbol parcial, puede crear una instancia de un <xref:System.Xml.XmlReader>, colocar el lector en el nodo que desea convertir a un árbol <xref:System.Xml.Linq.XElement> y después crear el objeto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="66856-113">If you want to create a partial tree, you can instantiate an <xref:System.Xml.XmlReader>, position the reader on the node that you want to convert to an <xref:System.Xml.Linq.XElement> tree, and then create the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
<span data-ttu-id="66856-114">El tema [Procedimiento para hacer streaming de fragmentos XML con acceso a la información del encabezado (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md) contiene información y un ejemplo sobre cómo hacer streaming de un documento más complejo.</span><span class="sxs-lookup"><span data-stu-id="66856-114">The topic [How to stream XML fragments with access to header information (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md) contains information and an example on how to stream a more complex document.</span></span>
  
 <span data-ttu-id="66856-115">El tema [Procedimiento para realizar una transformación de streaming de documentos XML grandes (C#)](./how-to-perform-streaming-transform-of-large-xml-documents.md) contiene un ejemplo del uso de LINQ to XML para transformar documentos XML extremadamente grandes manteniendo una superficie de memoria pequeña.</span><span class="sxs-lookup"><span data-stu-id="66856-115">The topic [How to perform streaming transform of large XML documents (C#)](./how-to-perform-streaming-transform-of-large-xml-documents.md) contains an example of using LINQ to XML to transform extremely large XML documents while maintaining a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66856-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="66856-116">Example</span></span>  
 <span data-ttu-id="66856-117">Este ejemplo crea un método de eje personalizado.</span><span class="sxs-lookup"><span data-stu-id="66856-117">This example creates a custom axis method.</span></span> <span data-ttu-id="66856-118">Puede consultarlo usando una consulta de LINQ.</span><span class="sxs-lookup"><span data-stu-id="66856-118">You can query it by using a LINQ query.</span></span> <span data-ttu-id="66856-119">El método de eje personalizado, `StreamRootChildDoc`, es un método que está específicamente diseñado para leer un documento que tiene un elemento `Child` que se repite.</span><span class="sxs-lookup"><span data-stu-id="66856-119">The custom axis method, `StreamRootChildDoc`, is a method that is designed specifically to read a document that has a repeating `Child` element.</span></span>  
  
```csharp  
static IEnumerable<XElement> StreamRootChildDoc(StringReader stringReader)  
{  
    using (XmlReader reader = XmlReader.Create(stringReader))  
    {  
        reader.MoveToContent();  
        // Parse the file and display each of the nodes.  
        while (reader.Read())  
        {  
            switch (reader.NodeType)  
            {  
                case XmlNodeType.Element:  
                    if (reader.Name == "Child") {  
                        XElement el = XElement.ReadFrom(reader) as XElement;  
                        if (el != null)  
                            yield return el;  
                    }  
                    break;  
            }  
        }  
    }  
}  
  
static void Main(string[] args)  
{  
    string markup = @"<Root>  
      <Child Key=""01"">  
        <GrandChild>aaa</GrandChild>  
      </Child>  
      <Child Key=""02"">  
        <GrandChild>bbb</GrandChild>  
      </Child>  
      <Child Key=""03"">  
        <GrandChild>ccc</GrandChild>  
      </Child>  
    </Root>";  
  
    IEnumerable<string> grandChildData =  
        from el in StreamRootChildDoc(new StringReader(markup))  
        where (int)el.Attribute("Key") > 1  
        select (string)el.Element("GrandChild");  
  
    foreach (string str in grandChildData) {  
        Console.WriteLine(str);  
    }  
}  
```  
  
 <span data-ttu-id="66856-120">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="66856-120">This example produces the following output:</span></span>  
  
```output  
bbb  
ccc  
```  
  
 <span data-ttu-id="66856-121">En este ejemplo el documento de origen es muy pequeño.</span><span class="sxs-lookup"><span data-stu-id="66856-121">In this example, the source document is very small.</span></span> <span data-ttu-id="66856-122">No obstante, aunque hubiera millones de elementos `Child`, este ejemplo seguiría teniendo una superficie de memoria pequeña.</span><span class="sxs-lookup"><span data-stu-id="66856-122">However, even if there were millions of `Child` elements, this example would still have a small memory footprint.</span></span>  
