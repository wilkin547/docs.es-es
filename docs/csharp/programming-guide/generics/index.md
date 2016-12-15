---
title: "Gen&#233;ricos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "lenguaje C#, genéricos"
  - "genéricos [C#]"
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gen&#233;ricos (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Los tipos genéricos se agregaron a la versión 2.0 del lenguaje C\# y Common Language Runtime \(CLR\).  Estos tipos agregan el concepto de parámetros de tipo a .NET Framework, lo cual permite diseñar clases y métodos que aplazan la especificación de uno o más tipos hasta que el código de cliente declara y crea una instancia de la clase o del método.  Por ejemplo, mediante la utilización de un parámetro de tipo genérico T, se puede escribir una clase única que otro código de cliente puede utilizar sin generar el costo o el riesgo de conversiones en tiempo de ejecución u operaciones de conversión boxing, como se muestra a continuación:  
  
 [!code-cs[csProgGuideGenerics#1](../../../csharp/programming-guide/generics/codesnippet/CSharp/index_1.cs)]  
  
## Información general acerca de los genéricos  
  
-   Utilice los tipos genéricos para maximizar la reutilización, seguridad de tipos y rendimiento del código.  
  
-   El uso más común de genéricos es crear clases de colección.  
  
-   La biblioteca de clases de .NET Framework contiene varias nuevas clases de colección genéricas en el espacio de nombres <xref:System.Collections.Generic>.  Éstas se deberían utilizar siempre que sea posible en lugar de clases como <xref:System.Collections.ArrayList> en el espacio de nombres <xref:System.Collections>.  
  
-   Puede crear sus propias interfaces, clases, métodos, eventos y delegados genéricos.  
  
-   Las clases genéricas se pueden restringir para permitir el acceso a métodos en tipos de datos determinados.  
  
-   Se puede obtener información sobre los tipos que se utilizan en un tipo de datos genérico en tiempo de ejecución y mediante reflexión.  
  
## Secciones relacionadas  
 Para obtener más información:  
  
-   [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
  
-   [Ventajas de los genéricos](../../../csharp/programming-guide/generics/benefits-of-generics.md)  
  
-   [Parámetros de tipos genéricos](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
-   [Restricciones de tipos de parámetros](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
-   [Clases genéricas](../../../csharp/programming-guide/generics/generic-classes.md)  
  
-   [Interfaces genéricas](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
-   [Métodos genéricos](../../../csharp/programming-guide/generics/generic-methods.md)  
  
-   [Delegados genéricos](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
-   [Palabra clave predeterminada](../../../csharp/programming-guide/generics/default-keyword-in-generic-code.md)  
  
-   [Diferencias entre plantillas de C\+\+ y tipos genéricos de C\#](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
-   [Genéricos y reflexión](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
-   [Genéricos en el motor en tiempo de ejecución](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
-   [Tipos genéricos en la biblioteca de clases de .NET Framework](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md)  
  
## Especificación del lenguaje C\#  
 Para obtener más información, vea [Especificación del lenguaje C\#](../../../csharp/language-reference/language-specification.md).  
  
## Vea también  
 <xref:System.Collections.Generic>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Tipos](../../../csharp/programming-guide/types/index.md)   
 [\<typeparam\>](../../../csharp/programming-guide/xmldoc/typeparam.md)   
 [\<typeparamref\>](../../../csharp/programming-guide/xmldoc/typeparamref.md)