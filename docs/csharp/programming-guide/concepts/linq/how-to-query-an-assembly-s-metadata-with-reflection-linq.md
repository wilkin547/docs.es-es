---
title: Procedimiento para consultar los metadatos de un ensamblado con reflexión (LINQ) (C#)
description: Obtenga información sobre cómo usar LINQ con las API de reflexión de .NET en C# para recuperar metadatos específicos sobre los métodos que coinciden con un criterio de búsqueda.
ms.date: 07/20/2015
ms.assetid: c4cdce49-b1c8-4420-b12a-9ff7e6671368
ms.openlocfilehash: dc5352e9cb90e9ad2808fb027823174d07d69da6
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104596"
---
# <a name="how-to-query-an-assemblys-metadata-with-reflection-linq-c"></a><span data-ttu-id="604bc-103">Procedimiento para consultar los metadatos de un ensamblado con reflexión (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="604bc-103">How to query an assembly's metadata with Reflection (LINQ) (C#)</span></span>

<span data-ttu-id="604bc-104">Las API de reflexión de .NET Framework se pueden usar para examinar los metadatos de un ensamblado .NET y para crear colecciones de tipos, escribir miembros, parámetros y otros elementos que se encuentren en ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="604bc-104">The .NET reflection APIs can be used to examine the metadata in a .NET assembly and create collections of types, type members, parameters, and so on that are in that assembly.</span></span> <span data-ttu-id="604bc-105">Dado que estas colecciones admiten la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601>, se pueden consultar mediante LINQ.</span><span class="sxs-lookup"><span data-stu-id="604bc-105">Because these collections support the generic <xref:System.Collections.Generic.IEnumerable%601> interface, they can be queried by using LINQ.</span></span>  
  
<span data-ttu-id="604bc-106">En el ejemplo siguiente se muestra cómo se puede usar LINQ con reflexión para recuperar metadatos concretos sobre métodos que coinciden con un criterio de búsqueda especificado.</span><span class="sxs-lookup"><span data-stu-id="604bc-106">The following example shows how LINQ can be used with reflection to retrieve specific metadata about methods that match a specified search criterion.</span></span> <span data-ttu-id="604bc-107">En este caso, la consulta encontrará los nombres de todos los métodos del ensamblado que devuelven tipos enumerables, como matrices.</span><span class="sxs-lookup"><span data-stu-id="604bc-107">In this case, the query will find the names of all the methods in the assembly that return enumerable types such as arrays.</span></span>  
  
## <a name="example"></a><span data-ttu-id="604bc-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="604bc-108">Example</span></span>  
  
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

<span data-ttu-id="604bc-109">El ejemplo usa el método <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> para devolver una matriz de tipos en el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="604bc-109">The example uses the <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> method to return an array of types in the specified assembly.</span></span> <span data-ttu-id="604bc-110">Se aplica el filtro [where](../../../language-reference/keywords/where-clause.md) para que solo se devuelvan tipos públicos.</span><span class="sxs-lookup"><span data-stu-id="604bc-110">The [where](../../../language-reference/keywords/where-clause.md) filter is applied so that only public types are returned.</span></span> <span data-ttu-id="604bc-111">Para cada tipo público, se genera una consulta anidada con la matriz <xref:System.Reflection.MethodInfo> que se devuelve desde la llamada <xref:System.Type.GetMethods%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="604bc-111">For each public type, a subquery is generated by using the <xref:System.Reflection.MethodInfo> array that is returned from the <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> call.</span></span> <span data-ttu-id="604bc-112">Estos resultados se filtran para que solo devuelvan los métodos cuyo tipo de valor devuelto sea una matriz, o un tipo que implemente <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="604bc-112">These results are filtered to return only those methods whose return type is an array or else a type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="604bc-113">Por último, estos resultados se agrupan usando el nombre de tipo como una clave.</span><span class="sxs-lookup"><span data-stu-id="604bc-113">Finally, these results are grouped by using the type name as a key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="604bc-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="604bc-114">See also</span></span>

- [<span data-ttu-id="604bc-115">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="604bc-115">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
