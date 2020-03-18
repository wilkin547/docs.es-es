---
title: Procedimiento para efectuar transformaciones en streaming de texto en XML (C#)
ms.date: 07/20/2015
ms.assetid: 9b3bd941-d0ff-4f2d-ae41-7c3b81d8fae6
ms.openlocfilehash: 496535b7f868095a62be2b72b1eea2b082e00a44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75345795"
---
# <a name="how-to-perform-streaming-transformations-of-text-to-xml-c"></a>Procedimiento para efectuar transformaciones en streaming de texto en XML (C#)

Un enfoque del procesamiento de un archivo de texto es escribir un método de extensión que transmita el archivo de texto por secuencias de línea en línea mediante la construcción `yield return`. Después, puede escribir una consulta LINQ que procese el archivo de texto de forma aplazada y lenta. Si después usa <xref:System.Xml.Linq.XStreamingElement> para transmitir el resultado, puede crear una transformación del archivo de texto al XML usando una cantidad mínima de memoria, independientemente del tamaño del archivo de texto de origen.

 Existen algunas advertencias que deben tenerse en cuenta sobre las transformaciones de transmisión por secuencias. Una transformación de transmisión por secuencias se aplica mejor en situaciones en las que se puede procesar todo el archivo, y si se pueden procesar las líneas en el orden en el que se producen en el documento de origen. Si se debe procesar más de un archivo simultáneamente so si se deben ordenar las líneas antes de poder procesarlas, se perderán muchas de las ventajas de utilizar una técnica de transmisión por secuencias.

## <a name="example"></a>Ejemplo

 El siguiente archivo de texto, People.txt, es el origen de este ejemplo.

```text
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
        if (source == null)
            throw new ArgumentNullException(nameof(source));

        string line;
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
        var sr = new StreamReader("People.txt");
        var xmlTree = new XStreamingElement("Root",
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

- <xref:System.Xml.Linq.XStreamingElement>
