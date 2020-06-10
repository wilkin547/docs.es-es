---
title: Procedimiento para consultar los metadatos de un ensamblado con reflexión (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: c4cdce49-b1c8-4420-b12a-9ff7e6671368
ms.openlocfilehash: 092cb386af0c3f2e2241c2c2ac8e50eab74cc43b
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241544"
---
# <a name="how-to-query-an-assemblys-metadata-with-reflection-linq-c"></a>Procedimiento para consultar los metadatos de un ensamblado con reflexión (LINQ) (C#)

Las API de reflexión de .NET Framework se pueden usar para examinar los metadatos de un ensamblado .NET y para crear colecciones de tipos, escribir miembros, parámetros y otros elementos que se encuentren en ese ensamblado. Dado que estas colecciones admiten la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601>, se pueden consultar mediante LINQ.  
  
En el ejemplo siguiente se muestra cómo se puede usar LINQ con reflexión para recuperar metadatos concretos sobre métodos que coinciden con un criterio de búsqueda especificado. En este caso, la consulta encontrará los nombres de todos los métodos del ensamblado que devuelven tipos enumerables, como matrices.  
  
## <a name="example"></a>Ejemplo  
  
```csharp  
using System;
using System.Linq;
using System.Reflection;  

class ReflectionHowTO  
{  
    static void Main()  
    {  
        Assembly assembly = Assembly.Load("System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken= b77a5c561934e089");  
        var pubTypesQuery = from type in assembly.GetTypes()  
                    where type.IsPublic  
                        from method in type.GetMethods()  
                        where method.ReturnType.IsArray == true
                            || ( method.ReturnType.GetInterface(  
                                typeof(System.Collections.Generic.IEnumerable<>).FullName ) != null  
                            && method.ReturnType.FullName != "System.String" )  
                        group method.ToString() by type.ToString();  

        foreach (var groupOfMethods in pubTypesQuery)  
        {  
            Console.WriteLine("Type: {0}", groupOfMethods.Key);  
            foreach (var method in groupOfMethods)  
            {  
                Console.WriteLine("  {0}", method);  
            }  
        }  

        Console.WriteLine("Press any key to exit... ");  
        Console.ReadKey();  
    }  
}
```  

El ejemplo usa el método <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> para devolver una matriz de tipos en el ensamblado especificado. Se aplica el filtro [where](../../../language-reference/keywords/where-clause.md) para que solo se devuelvan tipos públicos. Para cada tipo público, se genera una consulta anidada con la matriz <xref:System.Reflection.MethodInfo> que se devuelve desde la llamada <xref:System.Type.GetMethods%2A?displayProperty=nameWithType>. Estos resultados se filtran para que solo devuelvan los métodos cuyo tipo de valor devuelto sea una matriz, o un tipo que implemente <xref:System.Collections.Generic.IEnumerable%601>. Por último, estos resultados se agrupan usando el nombre de tipo como una clave.  
  
## <a name="see-also"></a>Vea también

- [LINQ to Objects (C#)](./linq-to-objects.md)
