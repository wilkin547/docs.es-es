---
title: "C&#243;mo: Controlar una excepci&#243;n mediante Try y Catch (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "control de excepciones [C#], bloques Try/Catch"
  - "excepciones [C#], bloques Try/Catch"
  - "try/catch (bloques) [C#]"
ms.assetid: ca8e3773-980e-4767-8633-7408540e9818
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Controlar una excepci&#243;n mediante Try y Catch (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El propósito de un bloque [try\-catch](../../../csharp/language-reference/keywords/try-catch.md) es detectar y controlar una excepción generada por código en funcionamiento.  Algunas excepciones se pueden controlar en un bloque `catch` y el problema se puede resolver sin que se vuelva a producir la excepción; sin embargo, con más frecuencia lo único que puede hacer es asegurarse de que se produzca la excepción adecuada.  
  
## Ejemplo  
 En este ejemplo, <xref:System.IndexOutOfRangeException> no es la excepción más adecuada: <xref:System.ArgumentOutOfRangeException> tiene más sentido para el método porque el argumento de `index` pasado por el llamador produce el error.  
  
 [!code-cs[csProgGuideExceptions#5](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-handle-an-exception-using-try-catch_1.cs)]  
  
## Comentarios  
 El código que produce una excepción está incluido en el bloque `try`.  Una instrucción `catch` se agrega inmediatamente después para controlar `IndexOutOfRangeException`, si se produce.  El bloque `catch` controla `IndexOutOfRangeException` y en su lugar produce la excepción `ArgumentOutOfRangeException`, más adecuada.  Para proporcionar al llamador tanta información como sea posible, considere la posibilidad de especificar la excepción original como <xref:System.Exception.InnerException%2A> de la nueva excepción.  Dado que la propiedad <xref:System.Exception.InnerException%2A> es [de sólo lectura](../../../csharp/language-reference/keywords/readonly.md), debe asignarla en el constructor de la nueva excepción.  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Excepciones y control de excepciones](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)   
 [Control de excepciones](../../../csharp/programming-guide/exceptions/exception-handling.md)