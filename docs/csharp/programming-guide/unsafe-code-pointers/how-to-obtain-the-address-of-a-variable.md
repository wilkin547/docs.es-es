---
title: "Cómo: Obtener la dirección de una variable (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
caps.latest.revision: 19
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
ms.openlocfilehash: 169f68cc80b7a27427a9987942e66e0ba9ed1a02
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a>Cómo: Obtener la dirección de una variable (Guía de programación de C#)
Para obtener la dirección de una expresión unaria, que se evalúa como una variable fija, use el operador de dirección:  
  
```  
int number;  
int* p = &number; //address-of operator &  
```  
  
 El operador de dirección solo se puede aplicar a una variable. Si la variable es una variable móvil, puede usar la [instrucción fixed](../../../csharp/language-reference/keywords/fixed-statement.md) para fijar temporalmente la variable antes de obtener su dirección.  
  
 Es responsabilidad del usuario asegurarse de que se inicialice la variable. El compilador no emitirá un mensaje de error si no se inicializa la variable.  
  
 No se puede obtener la dirección de una constante o un valor.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, se declara un puntero a `int`, `p`, y se le asigna la dirección de una variable de entero, `number`. La variable `number` se inicializa como resultado de la asignación a *p. Comentar esta instrucción de asignación quitará la inicialización de la variable `number`, pero no se emitirá un error de compilación. Observe el uso del operador [Acceso a miembros](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) `->` para obtener y mostrar la dirección almacenada en el puntero.  
  
 [!code-cs[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_1.cs)]  
  
 [!code-cs[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_2.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Tipos](../../../csharp/language-reference/keywords/types.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)

