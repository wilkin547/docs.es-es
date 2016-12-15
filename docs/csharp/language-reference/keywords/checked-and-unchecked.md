---
title: "Checked y Unchecked (Referencia de C#) | Microsoft Docs"
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
  - "checked (instrucción) [C#]"
  - "excepciones [C#], comprobación de desbordamiento"
  - "operadores [C#], checked y unchecked"
  - "comprobación de desbordamiento [C#]"
  - "instrucciones [C#], checked y unchecked"
  - "unchecked (instrucción) [C#]"
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Checked y Unchecked (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Las instrucciones de C\# se pueden ejecutar en un contexto comprobado o no comprobado.  En un contexto no comprobado, el desbordamiento aritmético produce una excepción.  En un contexto no comprobado, el desbordamiento aritmético se pasa por alto y el resultado se trunca.  
  
-   [checked](../../../csharp/language-reference/keywords/checked.md) Especifica un contexto comprobado.  
  
-   [unchecked](../../../csharp/language-reference/keywords/unchecked.md) Especifica un contexto no comprobado.  
  
 Si no se especifican `checked` ni `unchecked`, el contexto predeterminado depende de factores externos, como las opciones del compilador.  
  
 Las siguientes operaciones se ven afectadas por la comprobación del desbordamiento:  
  
-   Expresiones que usan los siguientes operadores predefinidos en tipos integrales:  
  
     `++`  `--` \- \(unary\)   `+` \-   `*` `/`  
  
-   Conversiones numéricas explícitas entre tipos integrales.  
  
 La opción del compilador [\/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) permite especificar un contexto comprobado o no comprobado para todas las declaraciones aritméticas que no están explícitamente en el ámbito de una palabra clave `checked` o `unchecked`.  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Palabras clave de instrucciones](../../../csharp/language-reference/keywords/statement-keywords.md)