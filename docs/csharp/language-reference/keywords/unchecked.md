---
title: unchecked (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
dev_langs:
- CSharp
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
caps.latest.revision: 23
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5878a2412e6c85da85b1a3b8c2a8255b51e67137
ms.contentlocale: es-es
ms.lasthandoff: 09/25/2017

---
# <a name="unchecked-c-reference"></a>unchecked (Referencia de C#)
La palabra clave `unchecked` se usa para suprimir la comprobación de desbordamiento en las operaciones y conversiones aritméticas de tipos enteros.  
  
 En un contexto unchecked, si una expresión genera un valor que está fuera del intervalo del tipo de destino, no se marca el desbordamiento. Por ejemplo, dado que el cálculo del siguiente ejemplo se realiza en un bloque o una expresión `unchecked`, el hecho de que el resultado sea demasiado grande para un entero se omite y se asigna a `int1` el valor -2 147 483 639.  
  
 [!code-cs[csrefKeywordsChecked#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_1.cs)]  
  
 Si se quita el entorno `unchecked`, se produce un error de compilación. El desbordamiento se puede detectar en tiempo de compilación porque todos los términos de la expresión son constantes.  
  
 Las expresiones que contienen términos no constantes son unchecked de forma predeterminada en tiempo de compilación y tiempo de ejecución. Vea [checked](../../../csharp/language-reference/keywords/checked.md) para obtener información sobre cómo habilitar un entorno checked.  
  
 Puesto que la comprobación de desbordamiento lleva tiempo, el uso del código unchecked en situaciones donde no hay riesgo de desbordamiento puede mejorar el rendimiento. Pero si el desbordamiento es una posibilidad, se debe usar un entorno checked.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo usar la palabra clave `unchecked`.  
  
 [!code-cs[csrefKeywordsChecked#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_2.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Checked y Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)   
 [checked](../../../csharp/language-reference/keywords/checked.md)

