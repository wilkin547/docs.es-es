---
title: "Cómo: Efectuar transformaciones de transmisión de texto en XML (C#) | Microsoft Docs"
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: bba371063439dfe5698ab6c3342500eec9fdc015
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-perform-streaming-transformations-of-text-to-xml-c"></a>Cómo: Efectuar transformaciones de transmisión de texto en XML (C#)
Un enfoque del procesamiento de un archivo de texto es escribir un método de extensión que transmita el archivo de texto por secuencias de línea en línea mediante la construcción `yield return`. Después, puede escribir una consulta LINQ que procese el archivo de texto de forma aplazada y lenta. Si después usa <xref:System.Xml.Linq.XStreamingElement> para transmitir la salida, puede crear una transformación del archivo de texto al XML que usa una cantidad mínima de memoria, independientemente del tamaño del archivo de texto de origen.  
  
 Existen algunas advertencias que deben tenerse en cuenta sobre las transformaciones de transmisión por secuencias. Una transformación de transmisión por secuencias se aplica mejor en situaciones en las que se puede procesar todo el archivo, y si se pueden procesar las líneas en el orden en el que se producen en el documento de origen. Si se debe procesar más de un archivo simultáneamente so si se deben ordenar las líneas antes de poder procesarlas, se perderán muchas de las ventajas de utilizar una técnica de transmisión por secuencias.  
  
## <a name="example"></a>Ejemplo  
 El siguiente archivo de texto, People.txt, es el origen de este ejemplo.  
  
```  
#This is a comment  
1,Tai,Yee,Writer  
2,Nikolay,Grachev,Programmer  
3,David,Wright,Inventor  
```  
  
 El siguiente código contiene un método de extensión que transmite las líneas del archivo de texto por secuencias de forma diferida.  
  
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
  
 Este ejemplo produce el siguiente resultado:  
  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XStreamingElement>   
 [Advanced Query Techniques (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md) (Técnicas de consulta avanzadas (LINQ to XML) (C#))
