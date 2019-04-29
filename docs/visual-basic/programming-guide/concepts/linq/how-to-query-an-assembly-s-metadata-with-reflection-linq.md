---
title: Procedimiento Consultar los metadatos de un ensamblado con reflexión (LINQ) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 53caa336-ab83-4181-b0f6-5c87c5f9e4ee
ms.openlocfilehash: b5b74e27d4cfeb4360d9c743d16c16dc82134038
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644676"
---
# <a name="how-to-query-an-assemblys-metadata-with-reflection-linq-visual-basic"></a>Procedimiento Consultar los metadatos de un ensamblado con reflexión (LINQ) (Visual Basic)
En el ejemplo siguiente se muestra cómo se puede usar LINQ con reflexión para recuperar metadatos concretos sobre métodos que coinciden con un criterio de búsqueda especificado. En este caso, la consulta encontrará los nombres de todos los métodos del ensamblado que devuelven tipos enumerables, como matrices.  
  
## <a name="example"></a>Ejemplo  
  
```vb  
Imports System.Reflection  
Imports System.IO  
Imports System.Linq  
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
        Console.ReadKey()  
    End Sub  
  
End Module  
```  
  
 El ejemplo usa el método <xref:System.Reflection.Assembly.GetTypes%2A> para devolver una matriz de tipos en el ensamblado especificado. El [cláusula Where](../../../../visual-basic/language-reference/queries/where-clause.md) se aplica el filtro para que se devuelven solo los tipos públicos. Para cada tipo público, se genera una consulta anidada con la matriz <xref:System.Reflection.MethodInfo> que se devuelve desde la llamada <xref:System.Type.GetMethods%2A>. Estos resultados se filtran para que solo devuelvan los métodos cuyo tipo de valor devuelto sea una matriz, o un tipo que implemente <xref:System.Collections.Generic.IEnumerable%601>. Por último, estos resultados se agrupan usando el nombre de tipo como una clave.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Cree un proyecto que tenga como destino la versión 3.5 de .NET Framework, o bien una posterior, con una referencia a System.Core.dll y una instrucción `Imports` para el espacio de nombres System.Linq.  
  
## <a name="see-also"></a>Vea también

- [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
