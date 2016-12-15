---
title: "Excepciones generadas por el compilador (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "excepciones [C#], generadas por el compilador"
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Excepciones generadas por el compilador (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Common Language Runtime \(CLR\) de .NET Framework produce automáticamente algunas excepciones cuando se produce un error en operaciones básicas.  La tabla siguiente muestra estas excepciones y sus condiciones de error.  
  
|Excepción|Descripción|  
|---------------|-----------------|  
|<xref:System.ArithmeticException>|Clase base de las excepciones producidas durante operaciones aritméticas, como <xref:System.DivideByZeroException> y <xref:System.OverflowException>.|  
|<xref:System.ArrayTypeMismatchException>|Se produce cuando una matriz no puede almacenar un elemento dado porque el tipo real del elemento es incompatible con el tipo real de la matriz.|  
|<xref:System.DivideByZeroException>|Se produce cuando tiene lugar un intento de dividir un valor integral por cero.|  
|<xref:System.IndexOutOfRangeException>|Se produce cuando tiene lugar un intento de indizar una matriz cuando el índice es menor que cero o se encuentra fuera de los límites de la matriz.|  
|<xref:System.InvalidCastException>|Se produce cuando tiene lugar un error en tiempo de ejecución en una conversión explícita de un tipo base a una interfaz o a un tipo derivado.|  
|<xref:System.NullReferenceException>|Se produce al intentar hacer referencia a un objeto cuyo valor es [null](../../../csharp/language-reference/keywords/null.md).|  
|<xref:System.OutOfMemoryException>|Se produce cuando el intento de asignar memoria mediante el operador [new](../../../csharp/language-reference/keywords/new-operator.md) da un error.  Esto indica que la memoria disponible para Common Language Runtime se ha agotado.|  
|<xref:System.OverflowException>|Se produce cuando una operación aritmética en un contexto `checked` produce un desbordamiento.|  
|<xref:System.StackOverflowException>|Se produce cuando se agota la pila de excepciones debido a la existencia de demasiadas llamadas al método pendientes; normalmente, suele indicar un nivel de recursividad muy profundo o infinito.|  
|<xref:System.TypeInitializationException>|Se produce cuando un constructor estático produce una excepción sin que haya cláusulas `catch` compatibles para capturarla.|  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Excepciones y control de excepciones](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)   
 [Control de excepciones](../../../csharp/programming-guide/exceptions/exception-handling.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try\-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)