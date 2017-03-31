---
title: "Materialización intermedia (C#) | Microsoft Docs"
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
ms.assetid: 7922d38f-5044-41cf-8e17-7173d6553a5e
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4807224faef5968828e16a4e1f11614e7ac6cf73
ms.lasthandoff: 03/13/2017


---
# <a name="intermediate-materialization-c"></a>Materialización intermedia (C#)
Si no tiene cuidado, en algunas situaciones puede alterar drásticamente el perfil de memoria y rendimiento de su aplicación causando una materialización prematura de las recopilaciones de sus consultas. Algunos operadores de consulta estándar provocan la materialización de su colección de origen antes de producir un elemento único. Por ejemplo, <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName> primero recorre en iteración toda la colección de origen, después ordena todos los elementos y finalmente produce el primer elemento. Esto significa que resulta caro obtener el primer elemento de una recopilación ordenada; cada elemento posterior no es caro. Esto tiene sentido: sería imposible que el operador de consulta hiciera lo contrario.  
  
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
  
```  
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
  
 En este ejemplo se puede ver que la llamada a <xref:System.Linq.Enumerable.ToList%2A> hace que `AppendString` enumere todo su origen antes de producir el primer elemento. Si el origen fuera una matriz grande, alteraría significativamente el perfil de memoria de la aplicación.  
  
 Los operadores de consulta estándar también se pueden encadenar juntos. Esto se ilustra en el tema final de este tutorial.  
  
-   [Chaining Standard Query Operators Together (C#)](../../../../csharp/programming-guide/concepts/linq/chaining-standard-query-operators-together.md) (Encadenar juntos operadores de consulta estándar [C#])  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Encadenar consultas juntas (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)
