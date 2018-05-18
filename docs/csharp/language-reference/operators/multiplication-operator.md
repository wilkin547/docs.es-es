---
title: '* Operador (Referencia de C#)'
ms.date: 04/04/2018
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: 6c5d4de587b67e5ade158c163a87e8dea6bece5a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a>Operador * (Referencia de C#)
El operador de multiplicación (`*`) calcula el producto de sus operandos. Todos los tipos numéricos tienen operadores de multiplicación predefinidos.  

`*` también ejerce de operador de desreferencia, que permite leer y escribir en un puntero.
  
## <a name="remarks"></a>Comentarios  
 El operador `*` también se usa para declarar tipos de puntero y desreferenciar punteros. Este operador solo puede usarse en contextos no seguros, que son en los que se usa la palabra clave [unsafe](../../../csharp/language-reference/keywords/unsafe.md) y que requieren la opción de compilador [/ unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).  El operador de desreferencia también se conoce como el operador de direccionamiento indirecto.  
  
 Los tipos definidos por el usuario pueden sobrecargar el operador binario `*` (consulte [operator](../../../csharp/language-reference/keywords/operator.md)). Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
