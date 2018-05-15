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
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a><span data-ttu-id="733cc-102">Cómo: Obtener la dirección de una variable (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="733cc-102">How to: Obtain the Address of a Variable (C# Programming Guide)</span></span>
<span data-ttu-id="733cc-103">Para obtener la dirección de una expresión unaria, que se evalúa como una variable fija, use el operador de dirección `&`:</span><span class="sxs-lookup"><span data-stu-id="733cc-103">To obtain the address of a unary expression, which evaluates to a fixed variable, use the address-of operator `&`:</span></span>  
  
```csharp  
int number;  
int* p = &number; //address-of operator &  
```  
  
 <span data-ttu-id="733cc-104">El operador de dirección solo se puede aplicar a una variable.</span><span class="sxs-lookup"><span data-stu-id="733cc-104">The address-of operator can only be applied to a variable.</span></span> <span data-ttu-id="733cc-105">Si la variable es una variable móvil, puede usar la [instrucción fixed](../../../csharp/language-reference/keywords/fixed-statement.md) para fijar temporalmente la variable antes de obtener su dirección.</span><span class="sxs-lookup"><span data-stu-id="733cc-105">If the variable is a moveable variable, you can use the [fixed statement](../../../csharp/language-reference/keywords/fixed-statement.md) to temporarily fix the variable before obtaining its address.</span></span>  
  
 <span data-ttu-id="733cc-106">Es responsabilidad del usuario asegurarse de que se inicialice la variable.</span><span class="sxs-lookup"><span data-stu-id="733cc-106">It's your responsibility to ensure that the variable is initialized.</span></span> <span data-ttu-id="733cc-107">El compilador no emite un mensaje de error si no se inicializa la variable.</span><span class="sxs-lookup"><span data-stu-id="733cc-107">The compiler doesn't issue an error message if the variable is not initialized.</span></span>  
  
 <span data-ttu-id="733cc-108">No se puede obtener la dirección de una constante o un valor.</span><span class="sxs-lookup"><span data-stu-id="733cc-108">You can't get the address of a constant or a value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="733cc-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="733cc-109">Example</span></span>  
 <span data-ttu-id="733cc-110">En este ejemplo, se declara un puntero a `int`, `p`, y se le asigna la dirección de una variable de entero, `number`.</span><span class="sxs-lookup"><span data-stu-id="733cc-110">In this example, a pointer to `int`, `p`, is declared and assigned the address of an integer variable, `number`.</span></span> <span data-ttu-id="733cc-111">La variable `number` se inicializa como resultado de la asignación a `*p`.</span><span class="sxs-lookup"><span data-stu-id="733cc-111">The variable `number` is initialized as a result of the assignment to `*p`.</span></span> <span data-ttu-id="733cc-112">Si comenta esta instrucción de asignación, se quita la inicialización de la variable `number`, pero no se emite un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="733cc-112">If you comment out this assignment statement, the initialization of the variable `number` is removed, but no compile-time error is issued.</span></span>  

> [!NOTE]
> <span data-ttu-id="733cc-113">Compile este ejemplo con la opción del compilador [`-unsafe`](../../language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="733cc-113">Compile this example with the [`-unsafe`](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>
  
 [!code-csharp[address-of-a-variable](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="733cc-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="733cc-114">See Also</span></span>  
 [<span data-ttu-id="733cc-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="733cc-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="733cc-116">Expresiones de puntero</span><span class="sxs-lookup"><span data-stu-id="733cc-116">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="733cc-117">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="733cc-117">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="733cc-118">Tipos</span><span class="sxs-lookup"><span data-stu-id="733cc-118">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="733cc-119">unsafe</span><span class="sxs-lookup"><span data-stu-id="733cc-119">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="733cc-120">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="733cc-120">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="733cc-121">stackalloc</span><span class="sxs-lookup"><span data-stu-id="733cc-121">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
