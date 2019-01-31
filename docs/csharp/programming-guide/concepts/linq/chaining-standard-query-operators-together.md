---
title: Encadenar operadores de consulta estándar juntos (C#)
ms.date: 07/20/2015
ms.assetid: 66f2b0a9-2c23-4735-988e-bbc9dfb55c7b
ms.openlocfilehash: 71b364d76860b5daa21ea176947d9cfe9d49b308
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582888"
---
# <a name="chaining-standard-query-operators-together-c"></a>Encadenar operadores de consulta estándar juntos (C#)
Este es el tema final de [Tutorial: Encadenar cadenas juntas (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md).  
  
 Los operadores de consulta estándar también se pueden encadenar juntos. Por ejemplo, puede interponer el operador <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> y también funciona de forma diferida. No materializa resultados intermedios.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, se llama al método <xref:System.Linq.Enumerable.Where%2A> antes de llamar a `ConvertCollectionToUpperCase`. El método <xref:System.Linq.Enumerable.Where%2A> funciona casi exactamente de la misma manera que los métodos diferidos utilizados en los ejemplos anteriores de este tutorial, `ConvertCollectionToUpperCase` y `AppendString`.  
  
 Una diferencia es que en este caso, el método <xref:System.Linq.Enumerable.Where%2A> recorre en iteración su recopilación de origen, determina que el primer elemento no pasa el predicado y después obtiene el siguiente elemento, que lo pasa. A continuación produce el segundo elemento.  
  
 Pero la idea básica es la misma: las colecciones intermedias no se materializan a menos que deban hacerlo.  
  
 Cuando se utilizan expresiones de consulta, se convierten en llamadas a operadores de consulta estándar y se aplican los mismos principios.  
  
 Todos los ejemplos de esta sección que consultan documentos XML abierto de Office utilizan el mismo principio. La ejecución aplazada y la evaluación diferida son algunos de los conceptos fundamentales que debe comprender para utilizar LINQ (y LINQ to XML) de forma efectiva.  
  
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
            where s.CompareTo("D") >= 0  
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
  
```  
ToUpper: source >abc<  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
## <a name="see-also"></a>Vea también

- [Tutorial: Encadenar cadenas juntas (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)
