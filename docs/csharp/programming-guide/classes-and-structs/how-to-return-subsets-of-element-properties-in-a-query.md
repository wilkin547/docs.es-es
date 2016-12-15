---
title: "C&#243;mo: Devolver subconjuntos de propiedades de elementos en una consulta (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "tipos anónimos [C#], para subconjuntos de propiedades de elemento"
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Devolver subconjuntos de propiedades de elementos en una consulta (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Utilice un tipo anónimo en una expresión de consulta cuando se cumplan las dos condiciones siguientes:  
  
-   Sólo desea devolver algunas propiedades de cada elemento de origen.  
  
-   No tiene que almacenar los resultados de la consulta fuera del ámbito del método en el que se ejecuta la consulta.  
  
 Si sólo desea devolver una propiedad o campo de cada elemento de origen, puede utilizar simplemente el operador de punto en la cláusula `select`.  Por ejemplo, para devolver solamente el elemento `ID` de cada `student`, escriba la cláusula `select` de la siguiente forma:  
  
```  
select student.ID;  
```  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar un tipo anónimo para devolver solamente un subconjunto de las propiedades de cada elemento de origen que coincida con la condición especificada.  
  
 [!code-cs[csProgGuideLINQ#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-return-subsets-of-element-properties-in-a-query_1.cs)]  
  
 Tenga en cuenta que el tipo anónimo utiliza los nombres del elemento de origen para sus propiedades si no se especifican nombres.  Para asignar nombres nuevos a las propiedades del tipo anónimo, escriba la instrucción `select` de la siguiente forma:  
  
```  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 Si intenta realizar esta operación en el ejemplo anterior, también debe cambiar la instrucción `Console.WriteLine`:  
  
```  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## Compilar el código  
  
-   Para ejecutar este código, copie y pegue la clase en un proyecto de aplicación de consola de Visual C\# creado en [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)].  De manera predeterminada, el proyecto tiene como destino la versión 3.5 de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] y contendrá una referencia a System.Core.dll y una directiva `using` para System.Linq.  Si el proyecto no cumple uno o varios de estos requisitos, puede agregar lo que falte manualmente.  Para obtener más información, vea [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)