---
title: Materialización intermedia (C#)
ms.date: 07/20/2015
ms.assetid: 7922d38f-5044-41cf-8e17-7173d6553a5e
ms.openlocfilehash: af1eb7df7da02d8e72fc102cda4ee5f329dc7974
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "70253164"
---
# <a name="intermediate-materialization-c"></a>Materialización intermedia (C#)
Si no tiene cuidado, en algunas situaciones puede alterar drásticamente el perfil de memoria y rendimiento de su aplicación causando una materialización prematura de las recopilaciones de sus consultas. Algunos operadores de consulta estándar provocan la materialización de su recopilación de origen antes de producir un elemento único. Por ejemplo, <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> primero recorre en iteración toda la recopilación de origen, después ordena todos los elementos y finalmente produce el primer elemento. Esto significa que resulta caro obtener el primer elemento de una recopilación ordenada; cada elemento posterior no es caro. Esto tiene sentido: sería imposible que el operador de consulta hiciera lo contrario.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo altera el ejemplo anterior. El método `AppendString` llama a <xref:System.Linq.Enumerable.ToList%2A> antes de recorrer en iteración el origen. Esto provoca la materialización.  
  
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
        // the following statement materializes the source collection in a List<T>  
        // before iterating through it  
        foreach (string str in source.ToList())  
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
ToUpper: source >def<  
ToUpper: source >ghi<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 En este ejemplo puede ver que la llamada a <xref:System.Linq.Enumerable.ToList%2A> hace que `AppendString` enumere todo su origen antes de producir el primer elemento. Si el origen fuera una matriz grande, alteraría significativamente el perfil de memoria de la aplicación.  
  
 Los operadores de consulta estándar también se pueden encadenar juntos. Esto se ilustra en el tema final de este tutorial.  
  
- [Chaining Standard Query Operators Together (C#)](./chaining-standard-query-operators-together.md) (Encadenar juntos operadores de consulta estándar [C#])  
  
## <a name="see-also"></a>Vea también

- [Tutorial: encadenar cadenas juntas (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
