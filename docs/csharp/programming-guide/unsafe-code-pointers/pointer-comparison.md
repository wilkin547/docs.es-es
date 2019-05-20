---
title: 'Comparación de punteros: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: 25bc1c7b701c36d2daf1918986eb6a8e56980990
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635136"
---
# <a name="pointer-comparison-c-programming-guide"></a><span data-ttu-id="a8574-102">Comparación de punteros (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="a8574-102">Pointer Comparison (C# Programming Guide)</span></span>
<span data-ttu-id="a8574-103">Puede aplicar los siguientes operadores para comparar los punteros de cualquier tipo:</span><span class="sxs-lookup"><span data-stu-id="a8574-103">You can apply the following operators to compare pointers of any type:</span></span>  
  
 <span data-ttu-id="a8574-104">**==   !=   \<   >   \<=   >=**</span><span class="sxs-lookup"><span data-stu-id="a8574-104">**==   !=   \<   >   \<=   >=**</span></span>  
  
 <span data-ttu-id="a8574-105">Los operadores de comparación comparan las direcciones de los dos operandos, como si fueran enteros sin signo.</span><span class="sxs-lookup"><span data-stu-id="a8574-105">The comparison operators compare the addresses of the two operands as if they are unsigned integers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8574-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8574-106">Example</span></span>  
 [!code-csharp[csProgGuidePointers#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#16)]  
  
 [!code-csharp[csProgGuidePointers#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#17)]  
  
## <a name="sample-output"></a><span data-ttu-id="a8574-107">Resultados del ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8574-107">Sample Output</span></span>  
 `True`  
  
 `False`  
  
## <a name="see-also"></a><span data-ttu-id="a8574-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8574-108">See also</span></span>

- [<span data-ttu-id="a8574-109">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a8574-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a8574-110">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="a8574-110">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="a8574-111">Manipular punteros</span><span class="sxs-lookup"><span data-stu-id="a8574-111">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
- [<span data-ttu-id="a8574-112">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="a8574-112">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="a8574-113">Tipos</span><span class="sxs-lookup"><span data-stu-id="a8574-113">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="a8574-114">unsafe</span><span class="sxs-lookup"><span data-stu-id="a8574-114">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="a8574-115">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a8574-115">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="a8574-116">stackalloc</span><span class="sxs-lookup"><span data-stu-id="a8574-116">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
