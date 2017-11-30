---
title: Operador [] (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 03664f5604bb7d7dce9e8ae2ff0ec045c6a203b1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>Operador [] (Referencia de C#)
Los corchetes (`[]`) se usan para matrices, indexadores y atributos. También se pueden usar con punteros.  
  
## <a name="remarks"></a>Comentarios  
 El tipo de matriz es un tipo seguido de `[]`:  
  
 [!code-csharp[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]  
  
 Para acceder a un elemento de una matriz, el índice del elemento deseado se encierra entre corchetes:  
  
 [!code-csharp[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]  
  
 Se produce una excepción si el índice de una matriz está fuera del intervalo.  
  
 No se puede sobrecargar el operador de indexación de la matriz. En cambio, los tipos pueden definir indexadores y propiedades que aceptan uno o varios parámetros. Los parámetros del indexador van entre corchetes, al igual que los índices de matriz, pero se pueden declarar para que sean de cualquier tipo, a diferencia de los índices de matriz, que deben ser números enteros.  
  
 Por ejemplo, .NET Framework define un tipo `Hashtable` que asocia claves y valores de tipo arbitrario:  
  
 [!code-csharp[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]  
  
 Los corchetes también se usan para especificar [atributos](../../../csharp/programming-guide/concepts/attributes/index.md):  
  
 [!code-csharp[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]  
  
 Puede usar corchetes para indexar fuera de un puntero:  
  
 [!code-csharp[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]  
  
 No se realiza ninguna comprobación de límites.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)  
 [Matrices](../../../csharp/programming-guide/arrays/index.md)  
 [Indizadores](../../../csharp/programming-guide/indexers/index.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md)
