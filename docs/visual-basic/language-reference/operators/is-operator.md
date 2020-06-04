---
title: Operador Is
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 3cc0ae5f04358fbe6b2aabc50498f39ca7225164
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370809"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="c7215-102">Is (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7215-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="c7215-103">Compara dos variables de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="c7215-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7215-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c7215-104">Syntax</span></span>  
  
```vb  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="c7215-105">Partes</span><span class="sxs-lookup"><span data-stu-id="c7215-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="c7215-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="c7215-106">Required.</span></span> <span data-ttu-id="c7215-107">Cualquier `Boolean` valor.</span><span class="sxs-lookup"><span data-stu-id="c7215-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="c7215-108">Necesario.</span><span class="sxs-lookup"><span data-stu-id="c7215-108">Required.</span></span> <span data-ttu-id="c7215-109">Cualquier `Object` nombre.</span><span class="sxs-lookup"><span data-stu-id="c7215-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="c7215-110">Necesario.</span><span class="sxs-lookup"><span data-stu-id="c7215-110">Required.</span></span> <span data-ttu-id="c7215-111">Cualquier `Object` nombre.</span><span class="sxs-lookup"><span data-stu-id="c7215-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7215-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c7215-112">Remarks</span></span>  
 <span data-ttu-id="c7215-113">El `Is` operador determina si dos referencias de objeto hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="c7215-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="c7215-114">Sin embargo, no realiza comparaciones de valores.</span><span class="sxs-lookup"><span data-stu-id="c7215-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="c7215-115">Si `object1` y `object2` ambos hacen referencia a la misma instancia de objeto exacta, `result` es `True` ; si no es así, `result` es `False` .</span><span class="sxs-lookup"><span data-stu-id="c7215-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="c7215-116">`Is`también se puede usar con la `TypeOf` palabra clave para crear una `TypeOf` expresión... `Is` , que comprueba si una variable de objeto es compatible con un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="c7215-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7215-117">La `Is` palabra clave también se usa en la [selección... Instrucción Case](../statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c7215-117">The `Is` keyword is also used in the [Select...Case Statement](../statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7215-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7215-118">Example</span></span>  
 <span data-ttu-id="c7215-119">En el ejemplo siguiente se usa el `Is` operador para comparar pares de referencias de objeto.</span><span class="sxs-lookup"><span data-stu-id="c7215-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="c7215-120">Los resultados se asignan a un `Boolean` valor que representa si los dos objetos son idénticos.</span><span class="sxs-lookup"><span data-stu-id="c7215-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="c7215-121">Como se muestra en el ejemplo anterior, puede utilizar el `Is` operador para probar los objetos enlazados en tiempo de compilación y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c7215-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7215-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c7215-122">See also</span></span>

- [<span data-ttu-id="c7215-123">Typeof (operador)</span><span class="sxs-lookup"><span data-stu-id="c7215-123">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="c7215-124">Operador IsNot</span><span class="sxs-lookup"><span data-stu-id="c7215-124">IsNot Operator</span></span>](isnot-operator.md)
- [<span data-ttu-id="c7215-125">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7215-125">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="c7215-126">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7215-126">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="c7215-127">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="c7215-127">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="c7215-128">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="c7215-128">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
