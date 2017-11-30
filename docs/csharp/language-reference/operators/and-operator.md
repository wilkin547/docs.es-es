---
title: Operador &amp; (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eceee8e01ba46f65c6b182a40d14e62aaba5dd53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-c-reference"></a>Operador &amp; (Referencia de C#)
El operador & puede funcionar como un operador unario o binario.  
  
## <a name="remarks"></a>Comentarios  
 El operador & unario devuelve la dirección de su operando (necesita un contexto [no seguro](../../../csharp/language-reference/keywords/unsafe.md)).  
  
 Los operadores & binarios están predefinidos para los tipos enteros y `bool`. Para los tipos enteros, & calcula el AND bit a bit lógico de sus operandos. Para operandos `bool`, & calcula el AND lógico de sus operandos; es decir, el resultado es `true` si y solo si ambos operandos son `true`.  
  
 El operador `&` evalúa ambos operadores independientemente del valor del primero. Por ejemplo:  
  
 [!code-csharp[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 Los tipos definidos por el usuario pueden sobrecargar el operador binario `&` (consulte [operator](../../../csharp/language-reference/keywords/operator.md)). Las operaciones de tipos enteros suelen estar permitidas en la enumeración. Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
