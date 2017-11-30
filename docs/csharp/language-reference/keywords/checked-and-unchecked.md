---
title: Checked y Unchecked (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4b7b18b39dbfa7ed0818d9ea6e9e62ef79a9f5b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="checked-and-unchecked-c-reference"></a>Checked y Unchecked (Referencia de C#)
Las instrucciones de C# se pueden ejecutar en un contexto comprobado o no comprobado. En un contexto no comprobado, el desbordamiento aritmético produce una excepción. En un contexto no comprobado, el desbordamiento aritmético se pasa por alto y el resultado se trunca.  
  
-   [checked](../../../csharp/language-reference/keywords/checked.md) Especifica un contexto comprobado.  
  
-   [unchecked](../../../csharp/language-reference/keywords/unchecked.md) Especifica un contexto no comprobado.  
  
 Si no se especifican `checked` ni `unchecked`, el contexto predeterminado depende de factores externos, como las opciones del compilador.  
  
 Las siguientes operaciones se ven afectadas por la comprobación del desbordamiento:  
  
-   Expresiones que usan los siguientes operadores predefinidos en tipos integrales:  
  
     `++` `--` - (unario)   `+` -   `*` `/`  
  
-   Conversiones numéricas explícitas entre tipos integrales.  
  
 La opción del compilador [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) permite especificar un contexto comprobado o no comprobado para todas las declaraciones aritméticas que no están explícitamente en el ámbito de una palabra clave `checked` o `unchecked`.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [Palabras clave de instrucciones](../../../csharp/language-reference/keywords/statement-keywords.md)
