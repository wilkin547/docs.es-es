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
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a><span data-ttu-id="66be9-102">Cómo: Obtener la dirección de una variable (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="66be9-102">How to: Obtain the Address of a Variable (C# Programming Guide)</span></span>
<span data-ttu-id="66be9-103">Para obtener la dirección de una expresión unaria, que se evalúa como una variable fija, use el operador de dirección:</span><span class="sxs-lookup"><span data-stu-id="66be9-103">To obtain the address of a unary expression, which evaluates to a fixed variable, use the address-of operator:</span></span>  
  
```  
int number;  
int* p = &number; //address-of operator &  
```  
  
 <span data-ttu-id="66be9-104">El operador de dirección solo se puede aplicar a una variable.</span><span class="sxs-lookup"><span data-stu-id="66be9-104">The address-of operator can only be applied to a variable.</span></span> <span data-ttu-id="66be9-105">Si la variable es una variable móvil, puede usar la [instrucción fixed](../../../csharp/language-reference/keywords/fixed-statement.md) para fijar temporalmente la variable antes de obtener su dirección.</span><span class="sxs-lookup"><span data-stu-id="66be9-105">If the variable is a moveable variable, you can use the [fixed statement](../../../csharp/language-reference/keywords/fixed-statement.md) to temporarily fix the variable before obtaining its address.</span></span>  
  
 <span data-ttu-id="66be9-106">Es responsabilidad del usuario asegurarse de que se inicialice la variable.</span><span class="sxs-lookup"><span data-stu-id="66be9-106">It is your responsibility to ensure that the variable is initialized.</span></span> <span data-ttu-id="66be9-107">El compilador no emitirá un mensaje de error si no se inicializa la variable.</span><span class="sxs-lookup"><span data-stu-id="66be9-107">The compiler will not issue an error message if the variable is not initialized.</span></span>  
  
 <span data-ttu-id="66be9-108">No se puede obtener la dirección de una constante o un valor.</span><span class="sxs-lookup"><span data-stu-id="66be9-108">You cannot get the address of a constant or a value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66be9-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="66be9-109">Example</span></span>  
 <span data-ttu-id="66be9-110">En este ejemplo, se declara un puntero a `int`, `p`, y se le asigna la dirección de una variable de entero, `number`.</span><span class="sxs-lookup"><span data-stu-id="66be9-110">In this example, a pointer to `int`, `p`, is declared and assigned the address of an integer variable, `number`.</span></span> <span data-ttu-id="66be9-111">La variable `number` se inicializa como resultado de la asignación a *p.</span><span class="sxs-lookup"><span data-stu-id="66be9-111">The variable `number` is initialized as a result of the assignment to *p.</span></span> <span data-ttu-id="66be9-112">Comentar esta instrucción de asignación quitará la inicialización de la variable `number`, pero no se emitirá un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="66be9-112">If you make this assignment statement a comment, the initialization of the variable `number` will be removed, but no compile-time error is issued.</span></span> <span data-ttu-id="66be9-113">Observe el uso del operador [Acceso a miembros](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) `->` para obtener y mostrar la dirección almacenada en el puntero.</span><span class="sxs-lookup"><span data-stu-id="66be9-113">Notice the use of the [Member Access](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) operator `->` to obtain and display the address stored in the pointer.</span></span>  
  
 <span data-ttu-id="66be9-114">[!code-cs[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="66be9-114">[!code-cs[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_1.cs)]</span></span>  
  
 <span data-ttu-id="66be9-115">[!code-cs[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="66be9-115">[!code-cs[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66be9-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="66be9-116">See Also</span></span>  
 <span data-ttu-id="66be9-117">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="66be9-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="66be9-118">[Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="66be9-118">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="66be9-119">[Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="66be9-119">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="66be9-120">[Tipos](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="66be9-120">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="66be9-121">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="66be9-121">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="66be9-122">[fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="66be9-122">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="66be9-123">stackalloc</span><span class="sxs-lookup"><span data-stu-id="66be9-123">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

