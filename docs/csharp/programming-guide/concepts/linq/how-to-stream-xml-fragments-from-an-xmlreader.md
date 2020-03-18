---
title: Streaming de fragmentos XML desde un objeto XmlReader (C#)
ms.date: 07/20/2015
ms.assetid: 4a8f0e45-768a-42e2-bc5f-68bdf0e0a726
ms.openlocfilehash: f7914d33622518f983a685dd2e844a25fd3ca15f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714652"
---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-c"></a><span data-ttu-id="f4c86-102">Streaming de fragmentos XML desde un objeto XmlReader (C#)</span><span class="sxs-lookup"><span data-stu-id="f4c86-102">How to stream XML fragments from an XmlReader (C#)</span></span>

<span data-ttu-id="f4c86-103">Cuando deba procesar archivos XML grandes quizás no sea factible cargar la totalidad del árbol XML en memoria.</span><span class="sxs-lookup"><span data-stu-id="f4c86-103">When you have to process large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="f4c86-104">En este tema se muestra cómo transmitir por secuencias fragmentos usando <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="f4c86-104">This topic shows how to stream fragments using an <xref:System.Xml.XmlReader>.</span></span>  
  
 <span data-ttu-id="f4c86-105">Una de las formas más efectivas de usar <xref:System.Xml.XmlReader> para leer objetos <xref:System.Xml.Linq.XElement> es escribir un método de eje personalizado propio.</span><span class="sxs-lookup"><span data-stu-id="f4c86-105">One of the most effective ways to use an <xref:System.Xml.XmlReader> to read <xref:System.Xml.Linq.XElement> objects is to write your own custom axis method.</span></span> <span data-ttu-id="f4c86-106">Un método de eje suele devolver una recopilación como <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement>, tal y como se muestra en el ejemplo de este tema.</span><span class="sxs-lookup"><span data-stu-id="f4c86-106">An axis method typically returns a collection such as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, as shown in the example in this topic.</span></span> <span data-ttu-id="f4c86-107">En el método de eje personalizado, tras crear el fragmento XML llamando al método <xref:System.Xml.Linq.XNode.ReadFrom%2A>, devuelva la recopilación usando `yield return`.</span><span class="sxs-lookup"><span data-stu-id="f4c86-107">In the custom axis method, after you create the XML fragment by calling the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method, return the collection using `yield return`.</span></span> <span data-ttu-id="f4c86-108">Esto proporciona semántica de ejecución aplazada al método de eje personalizado.</span><span class="sxs-lookup"><span data-stu-id="f4c86-108">This provides deferred execution semantics to your custom axis method.</span></span>  
  
 <span data-ttu-id="f4c86-109">Cuando crea un árbol XML de un objeto <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlReader> debe estar posicionado en un elemento.</span><span class="sxs-lookup"><span data-stu-id="f4c86-109">When you create an XML tree from an <xref:System.Xml.XmlReader> object, the <xref:System.Xml.XmlReader> must be positioned on an element.</span></span> <span data-ttu-id="f4c86-110">El método <xref:System.Xml.Linq.XNode.ReadFrom%2A> no vuelve hasta que ha leído la etiqueta de cierre del elemento.</span><span class="sxs-lookup"><span data-stu-id="f4c86-110">The <xref:System.Xml.Linq.XNode.ReadFrom%2A> method does not return until it has read the close tag of the element.</span></span>  
  
 <span data-ttu-id="f4c86-111">Si desea crear un árbol parcial, puede crear una instancia de un <xref:System.Xml.XmlReader>, colocar el lector en el nodo que desea convertir a un árbol <xref:System.Xml.Linq.XElement> y después crear el objeto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="f4c86-111">If you want to create a partial tree, you can instantiate an <xref:System.Xml.XmlReader>, position the reader on the node that you want to convert to an <xref:System.Xml.Linq.XElement> tree, and then create the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
<span data-ttu-id="f4c86-112">El tema [Procedimiento para hacer streaming de fragmentos XML con acceso a la información del encabezado (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md) contiene información y un ejemplo sobre cómo hacer streaming de un documento más complejo.</span><span class="sxs-lookup"><span data-stu-id="f4c86-112">The topic [How to stream XML fragments with access to header information (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md) contains information and an example on how to stream a more complex document.</span></span>
  
 <span data-ttu-id="f4c86-113">El tema [Procedimiento para realizar una transformación de streaming de documentos XML grandes (C#)](./how-to-perform-streaming-transform-of-large-xml-documents.md) contiene un ejemplo del uso de LINQ to XML para transformar documentos XML extremadamente grandes manteniendo una superficie de memoria pequeña.</span><span class="sxs-lookup"><span data-stu-id="f4c86-113">The topic [How to perform streaming transform of large XML documents (C#)](./how-to-perform-streaming-transform-of-large-xml-documents.md) contains an example of using LINQ to XML to transform extremely large XML documents while maintaining a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4c86-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f4c86-114">Example</span></span>  
 <span data-ttu-id="f4c86-115">Este ejemplo crea un método de eje personalizado.</span><span class="sxs-lookup"><span data-stu-id="f4c86-115">This example creates a custom axis method.</span></span> <span data-ttu-id="f4c86-116">Puede consultarlo usando una consulta de LINQ.</span><span class="sxs-lookup"><span data-stu-id="f4c86-116">You can query it by using a LINQ query.</span></span> <span data-ttu-id="f4c86-117">El método de eje personalizado, `StreamRootChildDoc`, es un método que está específicamente diseñado para leer un documento que tiene un elemento `Child` que se repite.</span><span class="sxs-lookup"><span data-stu-id="f4c86-117">The custom axis method, `StreamRootChildDoc`, is a method that is designed specifically to read a document that has a repeating `Child` element.</span></span>  
  
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
  
 <span data-ttu-id="f4c86-118">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="f4c86-118">This example produces the following output:</span></span>  
  
```output  
bbb  
ccc  
```  
  
 <span data-ttu-id="f4c86-119">En este ejemplo el documento de origen es muy pequeño.</span><span class="sxs-lookup"><span data-stu-id="f4c86-119">In this example, the source document is very small.</span></span> <span data-ttu-id="f4c86-120">No obstante, aunque hubiera millones de elementos `Child`, este ejemplo seguiría teniendo una superficie de memoria pequeña.</span><span class="sxs-lookup"><span data-stu-id="f4c86-120">However, even if there were millions of `Child` elements, this example would still have a small memory footprint.</span></span>  
