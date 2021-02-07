---
description: 'Más información acerca de: operador is (Visual Basic)'
title: Operador is
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 0912ebd9bc9c33149568c6cea0197ef24c305ff2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665690"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="5f1fa-103">Operador is (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f1fa-103">Is operator (Visual Basic)</span></span>

<span data-ttu-id="5f1fa-104">Compara dos variables de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-104">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="5f1fa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f1fa-105">Syntax</span></span>

```vb
result = object1 Is object2
```

## <a name="parts"></a><span data-ttu-id="5f1fa-106">Partes</span><span class="sxs-lookup"><span data-stu-id="5f1fa-106">Parts</span></span>

 `result`  
 <span data-ttu-id="5f1fa-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-107">Required.</span></span> <span data-ttu-id="5f1fa-108">Cualquier `Boolean` valor.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-108">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="5f1fa-109">Necesario.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-109">Required.</span></span> <span data-ttu-id="5f1fa-110">Cualquier `Object` nombre.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-110">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="5f1fa-111">Necesario.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-111">Required.</span></span> <span data-ttu-id="5f1fa-112">Cualquier `Object` nombre.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-112">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f1fa-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5f1fa-113">Remarks</span></span>

<span data-ttu-id="5f1fa-114">El `Is` operador determina si dos referencias de objeto hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-114">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="5f1fa-115">Sin embargo, no realiza comparaciones de valores.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-115">However, it does not perform value comparisons.</span></span> <span data-ttu-id="5f1fa-116">Si `object1` y `object2` ambos hacen referencia a la misma instancia de objeto exacta, `result` es `True` ; si no es así, `result` es `False` .</span><span class="sxs-lookup"><span data-stu-id="5f1fa-116">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>

> [!NOTE]
> <span data-ttu-id="5f1fa-117">La `Is` palabra clave también se usa en la [selección... Instrucción Case](../statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5f1fa-117">The `Is` keyword is also used in the [Select...Case Statement](../statements/select-case-statement.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="5f1fa-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5f1fa-118">Example</span></span>

<span data-ttu-id="5f1fa-119">En el ejemplo siguiente se usa el `Is` operador para comparar pares de referencias de objeto.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="5f1fa-120">Los resultados se asignan a un `Boolean` valor que representa si los dos objetos son idénticos.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>

[!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]

<span data-ttu-id="5f1fa-121">Como se muestra en el ejemplo anterior, puede utilizar el `Is` operador para probar los objetos enlazados en tiempo de compilación y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>

## <a name="use-typeof-operator-with-is-operator"></a><span data-ttu-id="5f1fa-122">Usar el operador typeof con is</span><span class="sxs-lookup"><span data-stu-id="5f1fa-122">Use TypeOf operator with Is operator</span></span>

<span data-ttu-id="5f1fa-123">`Is` el operador también se puede usar con la `TypeOf` palabra clave para crear una `TypeOf` expresión... `Is` , que comprueba si una variable de objeto es compatible con un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-123">`Is` operator can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span> <span data-ttu-id="5f1fa-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5f1fa-124">For example:</span></span>

```vb
If TypeOf sender Is Button Then
```

## <a name="see-also"></a><span data-ttu-id="5f1fa-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f1fa-125">See also</span></span>

- [<span data-ttu-id="5f1fa-126">Operador TypeOf</span><span class="sxs-lookup"><span data-stu-id="5f1fa-126">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="5f1fa-127">Operador IsNot</span><span class="sxs-lookup"><span data-stu-id="5f1fa-127">IsNot Operator</span></span>](isnot-operator.md)
- [<span data-ttu-id="5f1fa-128">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5f1fa-128">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="5f1fa-129">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5f1fa-129">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="5f1fa-130">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="5f1fa-130">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="5f1fa-131">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="5f1fa-131">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
