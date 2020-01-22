---
title: Ejemplo de encadenamiento de consultas (C#)
ms.date: 07/20/2015
ms.assetid: abbca162-d95e-43af-b92c-e46e6aa2540e
ms.openlocfilehash: 45e3a4f341ca8eb06ff0f553e0f933956e6c6546
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205419"
---
# <a name="chaining-queries-example-c"></a>Ejemplo de encadenamiento de consultas (C#)
Este ejemplo se basa en el ejemplo anterior y muestra qué sucede cuando se encadenan dos consultas que usan ejecución aplazada y evaluación diferida.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se presenta otro método de extensión, `AppendString`, que anexa una cadena especificada a cada cadena de la recopilación de origen y después crea las nuevas cadenas.  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source >{0}<", str);  
            yield return str.ToUpper();  
        }  
    }  
  
    public static IEnumerable<string>  
      AppendString(this IEnumerable<string> source, string stringToAppend)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("AppendString: source >{0}<", str);  
            yield return str + stringToAppend;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        IEnumerable<string> q1 =  
            from s in stringArray.ConvertCollectionToUpperCase()  
            select s;  
  
        IEnumerable<string> q2 =  
            from s in q1.AppendString("!!!")  
            select s;  
  
        foreach (string str in q2)  
        {  
            Console.WriteLine("Main: str >{0}<", str);  
            Console.WriteLine();  
        }  
    }  
}  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```output  
ToUpper: source >abc<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 En este ejemplo puede ver que cada método de extensión funciona de uno en uno para cada elemento de la recopilación de origen.  
  
 Lo que debe quedar claro de este ejemplo es que aunque hemos encadenado juntas consultas que producen recopilaciones, no se han materializado recopilaciones intermedias. En su lugar, cada elemento se pasa de un método diferido al siguiente. Esto tiene como resultado una superficie de memoria mucho menor que el enfoque que primero tomaría una matriz de cadenas y después crearía una segunda matriz de cadenas que se han convertido a mayúsculas y finalmente crearía una tercera matriz de cadenas en la que cada cadena tiene puntos de exclamación anexados.  
  
 El siguiente tema de este tutorial ilustra la materialización intermedia:  
  
- [Materialización intermedia (C#)](./intermediate-materialization.md)  
  
## <a name="see-also"></a>Vea también

- [Tutorial: Encadenar cadenas juntas (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
