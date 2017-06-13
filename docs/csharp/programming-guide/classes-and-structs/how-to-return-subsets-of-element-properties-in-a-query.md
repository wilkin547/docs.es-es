---
title: "Cómo: Devolver subconjuntos de propiedades de elementos en una consulta (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 99768c4b486dd6e8a25af22ab187c673c548ece9
ms.contentlocale: es-es
ms.lasthandoff: 06/12/2017

---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a>Cómo: Devolver subconjuntos de propiedades de elementos en una consulta (Guía de programación de C#)
Use un tipo anónimo en una expresión de consulta cuando se cumplan estas dos condiciones:  
  
-   Solo quiere algunas de las propiedades de cada elemento de origen.  
  
-   No es necesario almacenar los resultados de la consulta fuera del ámbito del método en el que se ejecuta la consulta.  
  
 Si solo quiere devolver una propiedad o campo de cada elemento de origen, puede usar simplemente el operador de punto en la cláusula `select`. Por ejemplo, para devolver solo el `ID` de cada `student`, escriba la cláusula `select` como sigue:  
  
```  
select student.ID;  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar un tipo anónimo para devolver solo un subconjunto de las propiedades de cada elemento de origen que coincida con la condición especificada.  
  
 [!code-cs[csProgGuideLINQ#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-return-subsets-of-element-properties-in-a-query_1.cs)]  
  
 Tenga en cuenta que, si no se especifica ningún nombre, el tipo anónimo usa los nombres del elemento de origen para sus propiedades. Para asignar nombres nuevos a las propiedades del tipo anónimo, escriba la instrucción `select` como sigue:  
  
```  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 Si lo intenta en el ejemplo anterior, también debe cambiar la instrucción `Console.WriteLine`:  
  
```  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   Para ejecutar este código, copie y pegue la clase en un proyecto de aplicación de consola de Visual C# creado en [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)]. De forma predeterminada, este proyecto tiene como destino la versión 3.5 de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], y tendrá una referencia a System.Core.dll y una directiva `using` para System.Linq. Si faltan uno o varios de estos requisitos del proyecto, se pueden agregar manualmente.   
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)
