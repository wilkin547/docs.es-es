---
title: 'Comparación de punteros: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: 5185bd5e1686858452efcc7c89e2c1977e094386
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969211"
---
# <a name="pointer-comparison-c-programming-guide"></a><span data-ttu-id="6b5e4-102">Comparación de punteros (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="6b5e4-102">Pointer Comparison (C# Programming Guide)</span></span>
<span data-ttu-id="6b5e4-103">Puede aplicar los siguientes operadores para comparar los punteros de cualquier tipo:</span><span class="sxs-lookup"><span data-stu-id="6b5e4-103">You can apply the following operators to compare pointers of any type:</span></span>  
  
 <span data-ttu-id="6b5e4-104">**==   !=   \<   >   \<=   >=**</span><span class="sxs-lookup"><span data-stu-id="6b5e4-104">**==   !=   \<   >   \<=   >=**</span></span>  
  
 <span data-ttu-id="6b5e4-105">Los operadores de comparación comparan las direcciones de los dos operandos, como si fueran enteros sin signo.</span><span class="sxs-lookup"><span data-stu-id="6b5e4-105">The comparison operators compare the addresses of the two operands as if they are unsigned integers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b5e4-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b5e4-106">Example</span></span>  
 [!code-csharp[csProgGuidePointers#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#16)]  
  
 [!code-csharp[csProgGuidePointers#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#17)]  
  
## <a name="sample-output"></a><span data-ttu-id="6b5e4-107">Resultados del ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b5e4-107">Sample Output</span></span>  
 `True`  
  
 `False`  
  
## <a name="see-also"></a><span data-ttu-id="6b5e4-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b5e4-108">See also</span></span>

- [<span data-ttu-id="6b5e4-109">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6b5e4-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="6b5e4-110">Expresiones de puntero</span><span class="sxs-lookup"><span data-stu-id="6b5e4-110">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="6b5e4-111">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="6b5e4-111">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="6b5e4-112">Manipular punteros</span><span class="sxs-lookup"><span data-stu-id="6b5e4-112">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)
- [<span data-ttu-id="6b5e4-113">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="6b5e4-113">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="6b5e4-114">Tipos</span><span class="sxs-lookup"><span data-stu-id="6b5e4-114">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="6b5e4-115">unsafe</span><span class="sxs-lookup"><span data-stu-id="6b5e4-115">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="6b5e4-116">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6b5e4-116">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="6b5e4-117">stackalloc</span><span class="sxs-lookup"><span data-stu-id="6b5e4-117">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
