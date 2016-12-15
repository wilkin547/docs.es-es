---
title: "C&#243;mo: Crear grupos anidados (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "agrupar grupos en consultas LINQ"
  - "agrupar consultas LINQ"
  - "grupos [LINQ en C#], anidados"
  - "consultas anidadas [C#]"
  - "consultas [LINQ en C#], grupos anidados"
  - "expresiones de consulta [LINQ en C#], grupos anidados"
ms.assetid: f48c64af-6d4e-473c-ab27-02f78b5ec2b9
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Crear grupos anidados (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En el ejemplo siguiente se muestra cómo crear grupos anidados en una expresión de consulta [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)].  Cada grupo que se crea según el curso y el nivel académico se subdivide en grupos según los nombres de las personas.  
  
## Ejemplo  
 [!code-cs[csProgGuideLINQ#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-create-a-nested-group_1.cs)]  
  
 Observe que se requieren tres bucles `foreach` anidados para procesar una iteración en los elementos internos de un grupo anidado.  
  
## Compilar el código  
 Este ejemplo contiene referencias a objetos definidos en la aplicación de ejemplo del tema [Cómo: Consultar una colección de objetos](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md).  Para compilar y ejecutar este método, péguelo en la clase `StudentClass` de esa aplicación y agregue una llamada a éste desde el método `Main`.  
  
 Cuando adapte este método a su propia aplicación, recuerde que LINQ requiere la versión 3.5 de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] y que el proyecto debe contener una referencia a System.Core.dll y una directiva using para System.Linq.  Los tipos LINQ to SQL, LINQ to XML y LINQ to DataSet requieren directivas using y referencias adicionales.  Para obtener más información, vea [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Vea también  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)