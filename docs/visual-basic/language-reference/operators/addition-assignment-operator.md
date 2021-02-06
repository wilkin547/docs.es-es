---
description: 'Más información acerca de: operador + = (Visual Basic)'
title: += (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
ms.openlocfilehash: e5a6b8fcc75e44c00ee18fec9cd57e68b1218de7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640477"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="359d5-103">+= (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="359d5-103">+= Operator (Visual Basic)</span></span>

<span data-ttu-id="359d5-104">Agrega el valor de una expresión numérica al valor de una variable o propiedad numérica y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="359d5-104">Adds the value of a numeric expression to the value of a numeric variable or property and assigns the result to the variable or property.</span></span> <span data-ttu-id="359d5-105">También se puede utilizar para concatenar una `String` expresión a una `String` variable o propiedad y asignar el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="359d5-105">Can also be used to concatenate a `String` expression to a `String` variable or property and assign the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="359d5-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="359d5-106">Syntax</span></span>  
  
```vb  
variableorproperty += expression  
```  
  
## <a name="parts"></a><span data-ttu-id="359d5-107">Partes</span><span class="sxs-lookup"><span data-stu-id="359d5-107">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="359d5-108">Necesario.</span><span class="sxs-lookup"><span data-stu-id="359d5-108">Required.</span></span> <span data-ttu-id="359d5-109">Cualquier valor numérico o `String` variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="359d5-109">Any numeric or `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="359d5-110">Necesario.</span><span class="sxs-lookup"><span data-stu-id="359d5-110">Required.</span></span> <span data-ttu-id="359d5-111">Cualquier expresión numérica o numérica `String` .</span><span class="sxs-lookup"><span data-stu-id="359d5-111">Any numeric or `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="359d5-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="359d5-112">Remarks</span></span>  

 <span data-ttu-id="359d5-113">El elemento del lado izquierdo del `+=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="359d5-113">The element on the left side of the `+=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="359d5-114">La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="359d5-114">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="359d5-115">El `+=` operador agrega el valor situado a la derecha a la variable o propiedad de la izquierda, y asigna el resultado a la variable o propiedad de su izquierda.</span><span class="sxs-lookup"><span data-stu-id="359d5-115">The `+=` operator adds the value on its right to the variable or property on its left, and assigns the result to the variable or property on its left.</span></span> <span data-ttu-id="359d5-116">El `+=` operador también se puede usar para concatenar la `String` expresión de su derecha a la `String` variable o propiedad de su izquierda y asignar el resultado a la variable o propiedad de su izquierda.</span><span class="sxs-lookup"><span data-stu-id="359d5-116">The `+=` operator can also be used to concatenate the `String` expression on its right to the `String` variable or property on its left, and assign the result to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="359d5-117">Al utilizar el `+=` operador, es posible que no pueda determinar si se producirá la concatenación de cadenas o la suma.</span><span class="sxs-lookup"><span data-stu-id="359d5-117">When you use the `+=` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="359d5-118">Utilice el `&=` operador para la concatenación para eliminar la ambigüedad y proporcionar código autodocumentado.</span><span class="sxs-lookup"><span data-stu-id="359d5-118">Use the `&=` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
 <span data-ttu-id="359d5-119">Este operador de asignación realiza implícitamente conversiones de ampliación pero no de restricción si el entorno de compilación exige una semántica estricta.</span><span class="sxs-lookup"><span data-stu-id="359d5-119">This assignment operator implicitly performs widening but not narrowing conversions if the compilation environment enforces strict semantics.</span></span> <span data-ttu-id="359d5-120">Para obtener más información sobre estas conversiones, vea [conversiones de restricción y ampliación](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="359d5-120">For more information on these conversions, see [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="359d5-121">Para obtener más información sobre la semántica estricta y permisiva, vea [Option Strict (instrucción](../statements/option-strict-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="359d5-121">For more information on strict and permissive semantics, see [Option Strict Statement](../statements/option-strict-statement.md).</span></span>  
  
 <span data-ttu-id="359d5-122">Si se permite la semántica permisiva, el `+=` operador realiza implícitamente una serie de conversiones numéricas y de cadena idénticas a las realizadas por el `+` operador.</span><span class="sxs-lookup"><span data-stu-id="359d5-122">If permissive semantics are allowed, the `+=` operator implicitly performs a variety of string and numeric conversions identical to those performed by the `+` operator.</span></span> <span data-ttu-id="359d5-123">Para obtener más información sobre estas conversiones, vea [operador +](addition-operator.md).</span><span class="sxs-lookup"><span data-stu-id="359d5-123">For details on these conversions, see [+ Operator](addition-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="359d5-124">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="359d5-124">Overloading</span></span>  

 <span data-ttu-id="359d5-125">El `+` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="359d5-125">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="359d5-126">La sobrecarga del `+` operador afecta al comportamiento del `+=` operador.</span><span class="sxs-lookup"><span data-stu-id="359d5-126">Overloading the `+` operator affects the behavior of the `+=` operator.</span></span> <span data-ttu-id="359d5-127">Si el código utiliza `+=` en una clase o estructura que sobrecarga `+` , asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="359d5-127">If your code uses `+=` on a class or structure that overloads `+`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="359d5-128">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="359d5-128">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="359d5-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="359d5-129">Example</span></span>  

 <span data-ttu-id="359d5-130">En el ejemplo siguiente se usa el `+=` operador para combinar el valor de una variable con otra.</span><span class="sxs-lookup"><span data-stu-id="359d5-130">The following example uses the `+=` operator to combine the value of one variable with another.</span></span> <span data-ttu-id="359d5-131">La primera parte utiliza `+=` con variables numéricas para agregar un valor a otro.</span><span class="sxs-lookup"><span data-stu-id="359d5-131">The first part uses `+=` with numeric variables to add one value to another.</span></span> <span data-ttu-id="359d5-132">La segunda parte utiliza `+=` con `String` variables para concatenar un valor con otro.</span><span class="sxs-lookup"><span data-stu-id="359d5-132">The second part uses `+=` with `String` variables to concatenate one value with another.</span></span> <span data-ttu-id="359d5-133">En ambos casos, el resultado se asigna a la primera variable.</span><span class="sxs-lookup"><span data-stu-id="359d5-133">In both cases, the result is assigned to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 <span data-ttu-id="359d5-134">El valor de `num1` es ahora 13 y el valor de `str1` es ahora "103".</span><span class="sxs-lookup"><span data-stu-id="359d5-134">The value of `num1` is now 13, and the value of `str1` is now "103".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="359d5-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="359d5-135">See also</span></span>

- [<span data-ttu-id="359d5-136">+ (Operador)</span><span class="sxs-lookup"><span data-stu-id="359d5-136">+ Operator</span></span>](addition-operator.md)
- [<span data-ttu-id="359d5-137">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="359d5-137">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="359d5-138">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="359d5-138">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="359d5-139">Operadores de concatenación</span><span class="sxs-lookup"><span data-stu-id="359d5-139">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="359d5-140">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="359d5-140">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="359d5-141">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="359d5-141">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="359d5-142">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="359d5-142">Statements</span></span>](../../programming-guide/language-features/statements.md)
