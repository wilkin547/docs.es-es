---
title: "Funciones an&#243;nimas (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "funciones anónimas [C#]"
  - "métodos anónimos [C#]"
  - "expresiones lambda [C#], como funciones anónimas"
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Funciones an&#243;nimas (Gu&#237;a de programaci&#243;n de C#)
Una  función anónima es una instrucción o expresión insertada que puede utilizarse en cualquier lugar donde se espere un tipo delegado.  Puede utilizarla para inicializar un delegado con nombre o pasarla en lugar de un tipo delegado con nombre como un parámetro de método.  
  
 Existen dos tipos de funciones anónimas, que se analizan individualmente en los temas siguientes:  
  
-   [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
-   [Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  Las expresiones lambda se pueden enlazar a árboles de expresión y también a delegados.  
  
## La evolución de delegados en C\#  
 En C\# 1.0, se creaba una instancia de un delegado inicializándolo explícitamente con un método que se definía en otra parte del código.  En C\# 2.0, se introdujo el concepto de métodos anónimos como un medio de escribir bloques de instrucciones insertados sin nombre que se pueden ejecutar en una invocación de delegado.  C\# 3.0 introdujo las expresiones lambda, que son similares en concepto a los métodos anónimos, pero más expresivas y concisas.  Estas dos características se conocen colectivamente como *funciones anónimas*.  En general, las aplicaciones destinadas a la versión 3.5 y posteriores de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] deberían utilizar expresiones lambda.  
  
 El ejemplo siguiente muestra cómo ha evolucionado la creación de delegados desde C\# 1.0 a C\# 3.0:  
  
 [!code-cs[csProgGuideLINQ#65](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csRef30LangFeatures_2.cs#65)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Instrucciones, expresiones y operadores](../../../csharp/programming-guide/statements-expressions-operators/index.md)   
 [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [Delegados](../../../csharp/programming-guide/delegates/index.md)   
 [Árboles de expresión](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)