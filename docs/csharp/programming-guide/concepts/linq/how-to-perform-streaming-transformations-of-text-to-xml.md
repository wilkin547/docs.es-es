---
title: "Cómo: Efectuar transformaciones de transmisión de texto en XML (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 9b3bd941-d0ff-4f2d-ae41-7c3b81d8fae6
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3351f88bb27807714b3566992242e72a5d03ac14
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-perform-streaming-transformations-of-text-to-xml-c"></a><span data-ttu-id="146c6-102">Cómo: Efectuar transformaciones de transmisión de texto en XML (C#)</span><span class="sxs-lookup"><span data-stu-id="146c6-102">How to: Perform Streaming Transformations of Text to XML (C#)</span></span>
<span data-ttu-id="146c6-103">Un enfoque del procesamiento de un archivo de texto es escribir un método de extensión que transmita el archivo de texto por secuencias de línea en línea mediante la construcción `yield return`.</span><span class="sxs-lookup"><span data-stu-id="146c6-103">One approach to processing a text file is to write an extension method that streams the text file a line at a time using the `yield return` construct.</span></span> <span data-ttu-id="146c6-104">Después, puede escribir una consulta LINQ que procese el archivo de texto de forma aplazada y lenta.</span><span class="sxs-lookup"><span data-stu-id="146c6-104">You then can write a LINQ query that processes the text file in a lazy deferred fashion.</span></span> <span data-ttu-id="146c6-105">Si después usa <xref:System.Xml.Linq.XStreamingElement> para transmitir el resultado, puede crear una transformación del archivo de texto al XML usando una cantidad mínima de memoria, independientemente del tamaño del archivo de texto de origen.</span><span class="sxs-lookup"><span data-stu-id="146c6-105">If you then use <xref:System.Xml.Linq.XStreamingElement> to stream output, you then can create a transformation from the text file to XML that uses a minimal amount of memory, regardless of the size of the source text file.</span></span>  
  
 <span data-ttu-id="146c6-106">Existen algunas advertencias que deben tenerse en cuenta sobre las transformaciones de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="146c6-106">There are some caveats regarding streaming transformations.</span></span> <span data-ttu-id="146c6-107">Una transformación de transmisión por secuencias se aplica mejor en situaciones en las que se puede procesar todo el archivo, y si se pueden procesar las líneas en el orden en el que se producen en el documento de origen.</span><span class="sxs-lookup"><span data-stu-id="146c6-107">A streaming transformation is best applied in situations where you can process the entire file once, and if you can process the lines in the order that they occur in the source document.</span></span> <span data-ttu-id="146c6-108">Si se debe procesar más de un archivo simultáneamente so si se deben ordenar las líneas antes de poder procesarlas, se perderán muchas de las ventajas de utilizar una técnica de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="146c6-108">If you have to process the file more than once, or if you have to sort the lines before you can process them, you will lose many of the benefits of using a streaming technique.</span></span>  
  
## <a name="example"></a><span data-ttu-id="146c6-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="146c6-109">Example</span></span>  
 <span data-ttu-id="146c6-110">El siguiente archivo de texto, People.txt, es el origen de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="146c6-110">The following text file, People.txt, is the source for this example.</span></span>  
  
```  
#This is a comment  
1,Tai,Yee,Writer  
2,Nikolay,Grachev,Programmer  
3,David,Wright,Inventor  
```  
  
 <span data-ttu-id="146c6-111">El siguiente código contiene un método de extensión que transmite las líneas del archivo de texto por secuencias de forma diferida.</span><span class="sxs-lookup"><span data-stu-id="146c6-111">The following code contains an extension method that streams the lines of the text file in a deferred fashion.</span></span>  
  
```csharp  
public static class StreamReaderSequence  
{  
    public static IEnumerable<string> Lines(this StreamReader source)  
    {  
        String line;  
  
        if (source == null)  
            throw new ArgumentNullException("source");  
        while ((line = source.ReadLine()) != null)  
        {  
            yield return line;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        StreamReader sr = new StreamReader("People.txt");  
        XStreamingElement xmlTree = new XStreamingElement("Root",  
            from line in sr.Lines()  
            let items = line.Split(',')  
            where !line.StartsWith("#")  
            select new XElement("Person",  
                       new XAttribute("ID", items[0]),  
                       new XElement("First", items[1]),  
                       new XElement("Last", items[2]),  
                       new XElement("Occupation", items[3])  
                   )  
        );  
        Console.WriteLine(xmlTree);  
        sr.Close();  
    }  
}  
```  
  
 <span data-ttu-id="146c6-112">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="146c6-112">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Person ID="1">  
    <First>Tai</First>  
    <Last>Yee</Last>  
    <Occupation>Writer</Occupation>  
  </Person>  
  <Person ID="2">  
    <First>Nikolay</First>  
    <Last>Grachev</Last>  
    <Occupation>Programmer</Occupation>  
  </Person>  
  <Person ID="3">  
    <First>David</First>  
    <Last>Wright</Last>  
    <Occupation>Inventor</Occupation>  
  </Person>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="146c6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="146c6-113">See Also</span></span>  
 <span data-ttu-id="146c6-114"><xref:System.Xml.Linq.XStreamingElement></span><span class="sxs-lookup"><span data-stu-id="146c6-114"><xref:System.Xml.Linq.XStreamingElement></span></span>   
 <span data-ttu-id="146c6-115">[Advanced Query Techniques (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md) (Técnicas de consulta avanzadas (LINQ to XML) (C#))</span><span class="sxs-lookup"><span data-stu-id="146c6-115">[Advanced Query Techniques (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)</span></span>

