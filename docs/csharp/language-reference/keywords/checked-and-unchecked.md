---
title: Checked y Unchecked (Referencia de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
ms.openlocfilehash: 26ea8a7864d93b8d64661db2b0dc1df6634f989a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
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
