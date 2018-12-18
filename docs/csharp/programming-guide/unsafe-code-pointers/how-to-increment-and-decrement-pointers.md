---
title: Aumento y disminución de punteros - Guía de programación de C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
ms.openlocfilehash: f28fc4f86e4ff01f90bfd49714f38eee7040f9d1
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242302"
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a><span data-ttu-id="5c0cb-102">Cómo: Aumentar y disminuir punteros (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="5c0cb-102">How to: increment and decrement pointers (C# Programming Guide)</span></span>

<span data-ttu-id="5c0cb-103">Use los operadores de incremento y decremento (`++` y `--`) para cambiar la ubicación del puntero en `sizeof(pointer-type)` para un puntero de tipo `pointer-type*`.</span><span class="sxs-lookup"><span data-stu-id="5c0cb-103">Use the increment and the decrement operators, `++` and `--`, to change the pointer location by `sizeof(pointer-type)` for a pointer of the type `pointer-type*`.</span></span> <span data-ttu-id="5c0cb-104">Las expresiones de incremento y decremento adquieren la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c0cb-104">The increment and decrement expressions take the following form:</span></span>  
  
```csharp
++p;  
p++;  
--p;  
p--;  
```  
  
 <span data-ttu-id="5c0cb-105">Los operadores de incremento y decremento se pueden aplicar a punteros de cualquier tipo, a excepción del tipo `void*`.</span><span class="sxs-lookup"><span data-stu-id="5c0cb-105">The increment and decrement operators can be applied to pointers of any type except the type `void*`.</span></span>  
  
 <span data-ttu-id="5c0cb-106">El efecto de aplicar el operador de incremento a un puntero del tipo `pointer-type*` es agregar `sizeof(pointer-type)` a la dirección incluida en la variable del puntero.</span><span class="sxs-lookup"><span data-stu-id="5c0cb-106">The effect of applying the increment operator to a pointer of the type `pointer-type*` is to add `sizeof(pointer-type)` to the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="5c0cb-107">El efecto de aplicar el operador de decremento a un puntero del tipo `pointer-type*` es restar `sizeof(pointer-type)` de la dirección incluida en la variable del puntero.</span><span class="sxs-lookup"><span data-stu-id="5c0cb-107">The effect of applying the decrement operator to a pointer of the type `pointer-type*` is to subtract `sizeof(pointer-type)` from the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="5c0cb-108">No se genera ninguna excepción cuando la operación desborda el dominio del puntero y el resultado depende de la implementación.</span><span class="sxs-lookup"><span data-stu-id="5c0cb-108">No exceptions are generated when the operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c0cb-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5c0cb-109">Example</span></span>  
 <span data-ttu-id="5c0cb-110">En este ejemplo, se avanza a través de una matriz incrementando el puntero según el tamaño de `int`.</span><span class="sxs-lookup"><span data-stu-id="5c0cb-110">In this example, you step through an array by incrementing the pointer by the size of `int`.</span></span> <span data-ttu-id="5c0cb-111">Con cada paso que avanza, se muestra la dirección y el contenido del elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="5c0cb-111">With each step, you display the address and the content of the array element.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]  
  
<span data-ttu-id="5c0cb-112">**Value:0 @ Address:12860272**
**Value:1 @ Address:12860276**
**Value:2 @ Address:12860280**
**Value:3 @ Address:12860284**
**Value:4 @ Address:12860288**</span><span class="sxs-lookup"><span data-stu-id="5c0cb-112">**Value:0 @ Address:12860272**
**Value:1 @ Address:12860276**
**Value:2 @ Address:12860280**
**Value:3 @ Address:12860284**
**Value:4 @ Address:12860288**</span></span>

## <a name="see-also"></a><span data-ttu-id="5c0cb-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c0cb-113">See also</span></span>

- [<span data-ttu-id="5c0cb-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5c0cb-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="5c0cb-115">Expresiones de puntero</span><span class="sxs-lookup"><span data-stu-id="5c0cb-115">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="5c0cb-116">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="5c0cb-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="5c0cb-117">Manipular punteros</span><span class="sxs-lookup"><span data-stu-id="5c0cb-117">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [<span data-ttu-id="5c0cb-118">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="5c0cb-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="5c0cb-119">Tipos</span><span class="sxs-lookup"><span data-stu-id="5c0cb-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="5c0cb-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="5c0cb-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="5c0cb-121">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5c0cb-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="5c0cb-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="5c0cb-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
- [<span data-ttu-id="5c0cb-123">sizeof</span><span class="sxs-lookup"><span data-stu-id="5c0cb-123">sizeof</span></span>](../../../csharp/language-reference/keywords/sizeof.md)
