---
title: Comparación de punteros (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: fa980c944159c477c333762ffad569332fba9402
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086644"
---
# <a name="pointer-comparison-c-programming-guide"></a><span data-ttu-id="085d0-102">Comparación de punteros (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="085d0-102">Pointer Comparison (C# Programming Guide)</span></span>
<span data-ttu-id="085d0-103">Puede aplicar los siguientes operadores para comparar los punteros de cualquier tipo:</span><span class="sxs-lookup"><span data-stu-id="085d0-103">You can apply the following operators to compare pointers of any type:</span></span>  
  
 <span data-ttu-id="085d0-104">**==   !=   \<   >   \<=   >=**</span><span class="sxs-lookup"><span data-stu-id="085d0-104">**==   !=   \<   >   \<=   >=**</span></span>  
  
 <span data-ttu-id="085d0-105">Los operadores de comparación comparan las direcciones de los dos operandos, como si fueran enteros sin signo.</span><span class="sxs-lookup"><span data-stu-id="085d0-105">The comparison operators compare the addresses of the two operands as if they are unsigned integers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="085d0-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="085d0-106">Example</span></span>  
 [!code-csharp[csProgGuidePointers#16](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#17](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_2.cs)]  
  
## <a name="sample-output"></a><span data-ttu-id="085d0-107">Resultados del ejemplo</span><span class="sxs-lookup"><span data-stu-id="085d0-107">Sample Output</span></span>  
 `True`  
  
 `False`  
  
## <a name="see-also"></a><span data-ttu-id="085d0-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="085d0-108">See Also</span></span>

- [<span data-ttu-id="085d0-109">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="085d0-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="085d0-110">Expresiones de puntero</span><span class="sxs-lookup"><span data-stu-id="085d0-110">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="085d0-111">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="085d0-111">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="085d0-112">Manipular punteros</span><span class="sxs-lookup"><span data-stu-id="085d0-112">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [<span data-ttu-id="085d0-113">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="085d0-113">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="085d0-114">Tipos</span><span class="sxs-lookup"><span data-stu-id="085d0-114">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="085d0-115">unsafe</span><span class="sxs-lookup"><span data-stu-id="085d0-115">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="085d0-116">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="085d0-116">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="085d0-117">stackalloc</span><span class="sxs-lookup"><span data-stu-id="085d0-117">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
