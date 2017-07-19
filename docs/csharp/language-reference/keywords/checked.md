---
title: checked (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- checked_CSharpKeyword
- checked
dev_langs:
- CSharp
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
caps.latest.revision: 24
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
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5826c8e6f99352c730824bb504a168226b9e6600
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="checked-c-reference"></a>checked (Referencia de C#)
La palabra clave `checked` se usa con el fin de habilitar explícitamente la comprobación de desbordamiento para operaciones aritméticas y conversiones de tipo integral.  
  
 De manera predeterminada, una expresión que solo contiene valores constantes provoca un error del compilador si la expresión genera un valor fuera del intervalo del tipo de destino. Si la expresión contiene uno o varios valores no constantes, el compilador no detecta el desbordamiento. En el siguiente ejemplo, la evaluación de la expresión asignada a `i2` no genera un error del compilador.  
  
 [!code-cs[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_1.cs)]  
  
 De manera predeterminada, estas expresiones no constantes no se someten a la comprobación de desbordamiento en tiempo de ejecución y no generan excepciones de desbordamiento. En el ejemplo anterior, se muestra -2 147 483 639 como la suma de dos enteros positivos.  
  
 La comprobación de desbordamiento se puede habilitar mediante opciones del compilador, la configuración del entorno o la palabra clave `checked`. En los ejemplos siguientes, se muestra cómo usar una expresión `checked` o un bloque `checked` para detectar el desbordamiento generado por la suma anterior en tiempo de ejecución. En ambos ejemplos se genera una excepción de desbordamiento.  
  
 [!code-cs[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_2.cs)]  
  
 Se puede usar la palabra clave [unchecked](../../../csharp/language-reference/keywords/unchecked.md) para evitar la comprobación de desbordamiento.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, se muestra cómo usar `checked` para habilitar la comprobación de desbordamiento en tiempo de ejecución.  
  
 [!code-cs[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_3.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Checked y Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)   
 [unchecked](../../../csharp/language-reference/keywords/unchecked.md)
