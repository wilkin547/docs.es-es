---
title: Procedimiento para consultar los metadatos de un ensamblado con reflexión (LINQ)
ms.date: 07/20/2015
ms.assetid: 53caa336-ab83-4181-b0f6-5c87c5f9e4ee
ms.openlocfilehash: fda27f41d31bf8aa3931bf5923ff4011628107fe
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075335"
---
# <a name="how-to-query-an-assemblys-metadata-with-reflection-linq-visual-basic"></a>Cómo: consultar los metadatos de un ensamblado con reflexión (LINQ) (Visual Basic)

En el ejemplo siguiente se muestra cómo se puede usar LINQ con reflexión para recuperar metadatos concretos sobre métodos que coinciden con un criterio de búsqueda especificado. En este caso, la consulta encontrará los nombres de todos los métodos del ensamblado que devuelven tipos enumerables, como matrices.  
  
## <a name="example"></a>Ejemplo  
  
```vb
Imports System.Linq
Imports System.Reflection  

Module Module1  
    Sub Main()  
        Dim asmbly As Assembly =
            Assembly.Load("System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken= b77a5c561934e089")  
  
        Dim pubTypesQuery = From type In asmbly.GetTypes()
                            Where type.IsPublic
                            From method In type.GetMethods()
                            Where method.ReturnType.IsArray = True
                            Let name = method.ToString()
                            Let typeName = type.ToString()
                            Group name By typeName Into methodNames = Group  
  
        Console.WriteLine("Getting ready to iterate")  
        For Each item In pubTypesQuery  
            Console.WriteLine(item.methodNames)  
  
            For Each type In item.methodNames  
                Console.WriteLine(" " & type)  
            Next  
        Next  
        Console.WriteLine("Press any key to exit... ")  
        Console.ReadKey()  
    End Sub  
End Module  
```  
  
El ejemplo usa el método <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> para devolver una matriz de tipos en el ensamblado especificado. Se aplica el filtro de la [cláusula WHERE](../../../language-reference/queries/where-clause.md) para que solo se devuelvan los tipos públicos. Para cada tipo público, se genera una consulta anidada con la matriz <xref:System.Reflection.MethodInfo> que se devuelve desde la llamada <xref:System.Type.GetMethods%2A?displayProperty=nameWithType>. Estos resultados se filtran para que solo devuelvan los métodos cuyo tipo de valor devuelto sea una matriz, o un tipo que implemente <xref:System.Collections.Generic.IEnumerable%601>. Por último, estos resultados se agrupan usando el nombre de tipo como una clave.  
  
## <a name="see-also"></a>Vea también

- [LINQ to Objects (Visual Basic)](linq-to-objects.md)
