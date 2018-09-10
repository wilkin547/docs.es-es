---
title: ?? Operador (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- coalesce operator [C#]
- ?? operator [C#]
- conditional-AND operator (&&) [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 03d81d4216dabce2ea75b9fdcf6ef0971cc32490
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43530111"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="41b69-103">??</span><span class="sxs-lookup"><span data-stu-id="41b69-103">??</span></span> <span data-ttu-id="41b69-104">Operador (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="41b69-104">Operator (C# Reference)</span></span>
<span data-ttu-id="41b69-105">Al operador `??` se le llama el operador de uso combinado de NULL.</span><span class="sxs-lookup"><span data-stu-id="41b69-105">The `??` operator is called the null-coalescing operator.</span></span>  <span data-ttu-id="41b69-106">Dicho operador devuelve el operando izquierdo si no es NULL; de lo contrario, devuelve el operando derecho.</span><span class="sxs-lookup"><span data-stu-id="41b69-106">It returns the left-hand operand if the operand is not null; otherwise it returns the right hand operand.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41b69-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="41b69-107">Remarks</span></span>  
 <span data-ttu-id="41b69-108">Un tipo que acepta valores NULL puede representar un valor del dominio del tipo, o el valor puede no estar definido (en cuyo caso el valor es NULL).</span><span class="sxs-lookup"><span data-stu-id="41b69-108">A nullable type can represent a value from the type’s domain, or the value can be undefined (in which case the value is null).</span></span> <span data-ttu-id="41b69-109">Se puede usar la expresividad sintáctica del operador `??` para devolver un valor apropiado (el operando derecho) cuando el operando izquierdo tenga un tipo que acepta valores NULL cuyo valor sea NULL.</span><span class="sxs-lookup"><span data-stu-id="41b69-109">You can use the `??` operator’s syntactic expressiveness to return an appropriate value (the right hand operand) when the left operand has a nullable type whose value is null.</span></span> <span data-ttu-id="41b69-110">Si se intenta asignar un tipo de valor que acepta valores NULL a otro que no sin usar el operador `??`, se generará un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="41b69-110">If you try to assign a nullable value type to a non-nullable value type without using the `??` operator, you will generate a compile-time error.</span></span> <span data-ttu-id="41b69-111">Si se usa una conversión y el tipo de valor que acepta valores NULL no está definido actualmente, se producirá una excepción `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="41b69-111">If you use a cast, and the nullable value type is currently undefined, an `InvalidOperationException` exception will be thrown.</span></span>  
  
 <span data-ttu-id="41b69-112">Para más información, vea [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="41b69-112">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="41b69-113">El resultado de un</span><span class="sxs-lookup"><span data-stu-id="41b69-113">The result of a ??</span></span> <span data-ttu-id="41b69-114">operador ?? no se considera una constante, incluso si sus dos argumentos son constantes.</span><span class="sxs-lookup"><span data-stu-id="41b69-114">operator is not considered to be a constant even if both its arguments are constants.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41b69-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="41b69-115">Example</span></span>  
 [!code-csharp[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="41b69-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="41b69-116">See Also</span></span>

- [<span data-ttu-id="41b69-117">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="41b69-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="41b69-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="41b69-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="41b69-119">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="41b69-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="41b69-120">Tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="41b69-120">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
- [<span data-ttu-id="41b69-121">¿Qué significa exactamente "elevado"?</span><span class="sxs-lookup"><span data-stu-id="41b69-121">What Exactly Does 'Lifted' mean?</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)
