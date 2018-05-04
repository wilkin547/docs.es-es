---
title: 'Cómo: Obtener la dirección de una variable (Guía de programación de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 63a49490effb8b7d365492e8518b7558ec03a705
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a>Cómo: Obtener la dirección de una variable (Guía de programación de C#)
Para obtener la dirección de una expresión unaria, que se evalúa como una variable fija, use el operador de dirección `&`:  
  
```csharp  
int number;  
int* p = &number; //address-of operator &  
```  
  
 El operador de dirección solo se puede aplicar a una variable. Si la variable es una variable móvil, puede usar la [instrucción fixed](../../../csharp/language-reference/keywords/fixed-statement.md) para fijar temporalmente la variable antes de obtener su dirección.  
  
 Es responsabilidad del usuario asegurarse de que se inicialice la variable. El compilador no emite un mensaje de error si no se inicializa la variable.  
  
 No se puede obtener la dirección de una constante o un valor.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, se declara un puntero a `int`, `p`, y se le asigna la dirección de una variable de entero, `number`. La variable `number` se inicializa como resultado de la asignación a `*p`. Si comenta esta instrucción de asignación, se quita la inicialización de la variable `number`, pero no se emite un error de compilación.  

> [!NOTE]
> Compile este ejemplo con la opción del compilador [`-unsafe`](../../language-reference/compiler-options/unsafe-compiler-option.md).
  
 [!code-csharp[address-of-a-variable](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#8)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [Tipos](../../../csharp/language-reference/keywords/types.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
