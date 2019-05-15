---
title: 'Procedimiento Devolver subconjuntos de propiedades de elementos en una consulta: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
ms.openlocfilehash: da4ecb11c51f42c2297b6d40ed9a963590b3f441
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64599988"
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a>Procedimiento Devolver subconjuntos de propiedades de elementos en una consulta (Guía de programación de C#)
Use un tipo anónimo en una expresión de consulta cuando se cumplan estas dos condiciones:  
  
- Solo quiere algunas de las propiedades de cada elemento de origen.  
  
- No es necesario almacenar los resultados de la consulta fuera del ámbito del método en el que se ejecuta la consulta.  
  
 Si solo quiere devolver una propiedad o campo de cada elemento de origen, puede usar simplemente el operador de punto en la cláusula `select`. Por ejemplo, para devolver solo el `ID` de cada `student`, escriba la cláusula `select` como sigue:  
  
```  
select student.ID;  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar un tipo anónimo para devolver solo un subconjunto de las propiedades de cada elemento de origen que coincida con la condición especificada.  
  
 [!code-csharp[csProgGuideLINQ#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#31)]  
  
 Tenga en cuenta que, si no se especifica ningún nombre, el tipo anónimo usa los nombres del elemento de origen para sus propiedades. Para asignar nombres nuevos a las propiedades del tipo anónimo, escriba la instrucción `select` como sigue:  
  
```  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 Si lo intenta en el ejemplo anterior, también debe cambiar la instrucción `Console.WriteLine`:  
  
```csharp  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
- Para ejecutar este código, copie y pegue la clase en un proyecto de aplicación de la consola de Visual C# creado en Visual Studio. De forma predeterminada, este proyecto tiene como destino la versión 3.5 de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], y tendrá una referencia a System.Core.dll y una directiva `using` para System.Linq. Si faltan alguno de estos requisitos del proyecto, se puede agregar manualmente.   
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)
