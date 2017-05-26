---
title: Operador [] (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '[]_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
caps.latest.revision: 20
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
ms.openlocfilehash: 4eaecd5cd70c396a62856087a7b37f38e02d2383
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="-operator-c-reference"></a>Operador [] (Referencia de C#)
Los corchetes (`[]`) se usan para matrices, indexadores y atributos. También se pueden usar con punteros.  
  
## <a name="remarks"></a>Comentarios  
 El tipo de matriz es un tipo seguido de `[]`:  
  
 [!code-cs[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]  
  
 Para acceder a un elemento de una matriz, el índice del elemento deseado se encierra entre corchetes:  
  
 [!code-cs[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]  
  
 Se produce una excepción si el índice de una matriz está fuera del intervalo.  
  
 No se puede sobrecargar el operador de indexación de la matriz. En cambio, los tipos pueden definir indexadores y propiedades que aceptan uno o varios parámetros. Los parámetros del indexador van entre corchetes, al igual que los índices de matriz, pero se pueden declarar para que sean de cualquier tipo, a diferencia de los índices de matriz, que deben ser números enteros.  
  
 Por ejemplo, .NET Framework define un tipo `Hashtable` que asocia claves y valores de tipo arbitrario:  
  
 [!code-cs[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]  
  
 Los corchetes también se usan para especificar [atributos](../../../csharp/programming-guide/concepts/attributes/index.md):  
  
 [!code-cs[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]  
  
 Puede usar corchetes para indexar fuera de un puntero:  
  
 [!code-cs[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]  
  
 No se realiza ninguna comprobación de límites.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)   
 [Arrays](../../../csharp/programming-guide/arrays/index.md)  (Matrices)  
 [Indexers](../../../csharp/programming-guide/indexers/index.md)  (Indexadores)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md)

