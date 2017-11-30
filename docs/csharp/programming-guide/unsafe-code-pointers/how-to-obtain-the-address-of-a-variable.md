---
title: "Cómo: Obtener la dirección de una variable (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d0969f7e62864c682660f08cd4198aa4032e0e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a><span data-ttu-id="88cb7-102">Cómo: Obtener la dirección de una variable (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="88cb7-102">How to: Obtain the Address of a Variable (C# Programming Guide)</span></span>
<span data-ttu-id="88cb7-103">Para obtener la dirección de una expresión unaria, que se evalúa como una variable fija, use el operador de dirección:</span><span class="sxs-lookup"><span data-stu-id="88cb7-103">To obtain the address of a unary expression, which evaluates to a fixed variable, use the address-of operator:</span></span>  
  
```  
int number;  
int* p = &number; //address-of operator &  
```  
  
 <span data-ttu-id="88cb7-104">El operador de dirección solo se puede aplicar a una variable.</span><span class="sxs-lookup"><span data-stu-id="88cb7-104">The address-of operator can only be applied to a variable.</span></span> <span data-ttu-id="88cb7-105">Si la variable es una variable móvil, puede usar la [instrucción fixed](../../../csharp/language-reference/keywords/fixed-statement.md) para fijar temporalmente la variable antes de obtener su dirección.</span><span class="sxs-lookup"><span data-stu-id="88cb7-105">If the variable is a moveable variable, you can use the [fixed statement](../../../csharp/language-reference/keywords/fixed-statement.md) to temporarily fix the variable before obtaining its address.</span></span>  
  
 <span data-ttu-id="88cb7-106">Es responsabilidad del usuario asegurarse de que se inicialice la variable.</span><span class="sxs-lookup"><span data-stu-id="88cb7-106">It is your responsibility to ensure that the variable is initialized.</span></span> <span data-ttu-id="88cb7-107">El compilador no emitirá un mensaje de error si no se inicializa la variable.</span><span class="sxs-lookup"><span data-stu-id="88cb7-107">The compiler will not issue an error message if the variable is not initialized.</span></span>  
  
 <span data-ttu-id="88cb7-108">No se puede obtener la dirección de una constante o un valor.</span><span class="sxs-lookup"><span data-stu-id="88cb7-108">You cannot get the address of a constant or a value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88cb7-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="88cb7-109">Example</span></span>  
 <span data-ttu-id="88cb7-110">En este ejemplo, se declara un puntero a `int`, `p`, y se le asigna la dirección de una variable de entero, `number`.</span><span class="sxs-lookup"><span data-stu-id="88cb7-110">In this example, a pointer to `int`, `p`, is declared and assigned the address of an integer variable, `number`.</span></span> <span data-ttu-id="88cb7-111">La variable `number` se inicializa como resultado de la asignación a *p.</span><span class="sxs-lookup"><span data-stu-id="88cb7-111">The variable `number` is initialized as a result of the assignment to *p.</span></span> <span data-ttu-id="88cb7-112">Comentar esta instrucción de asignación quitará la inicialización de la variable `number`, pero no se emitirá un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="88cb7-112">If you make this assignment statement a comment, the initialization of the variable `number` will be removed, but no compile-time error is issued.</span></span> <span data-ttu-id="88cb7-113">Observe el uso del operador [Acceso a miembros](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) `->` para obtener y mostrar la dirección almacenada en el puntero.</span><span class="sxs-lookup"><span data-stu-id="88cb7-113">Notice the use of the [Member Access](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) operator `->` to obtain and display the address stored in the pointer.</span></span>  
  
 [!code-csharp[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="88cb7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="88cb7-114">See Also</span></span>  
 [<span data-ttu-id="88cb7-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="88cb7-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="88cb7-116">Expresiones de puntero</span><span class="sxs-lookup"><span data-stu-id="88cb7-116">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="88cb7-117">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="88cb7-117">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="88cb7-118">Tipos</span><span class="sxs-lookup"><span data-stu-id="88cb7-118">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="88cb7-119">unsafe</span><span class="sxs-lookup"><span data-stu-id="88cb7-119">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="88cb7-120">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="88cb7-120">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="88cb7-121">stackalloc</span><span class="sxs-lookup"><span data-stu-id="88cb7-121">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
