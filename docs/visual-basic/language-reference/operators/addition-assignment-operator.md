---
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
ms.openlocfilehash: a3a37798a3ddb480ac5322c4b2d3e9396e739aa6
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873488"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="1fd51-102">+= (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1fd51-102">+= Operator (Visual Basic)</span></span>

<span data-ttu-id="1fd51-103">Agrega el valor de una expresión numérica al valor de una variable o propiedad numérica y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="1fd51-103">Adds the value of a numeric expression to the value of a numeric variable or property and assigns the result to the variable or property.</span></span> <span data-ttu-id="1fd51-104">También se puede utilizar para concatenar una `String` expresión a una `String` variable o propiedad y asignar el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="1fd51-104">Can also be used to concatenate a `String` expression to a `String` variable or property and assign the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fd51-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1fd51-105">Syntax</span></span>  
  
```vb  
variableorproperty += expression  
```  
  
## <a name="parts"></a><span data-ttu-id="1fd51-106">Partes</span><span class="sxs-lookup"><span data-stu-id="1fd51-106">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="1fd51-107">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1fd51-107">Required.</span></span> <span data-ttu-id="1fd51-108">Cualquier valor numérico o `String` variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="1fd51-108">Any numeric or `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="1fd51-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1fd51-109">Required.</span></span> <span data-ttu-id="1fd51-110">Cualquier expresión numérica o numérica `String` .</span><span class="sxs-lookup"><span data-stu-id="1fd51-110">Any numeric or `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fd51-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1fd51-111">Remarks</span></span>  

 <span data-ttu-id="1fd51-112">El elemento del lado izquierdo del `+=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="1fd51-112">The element on the left side of the `+=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="1fd51-113">La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="1fd51-113">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="1fd51-114">El `+=` operador agrega el valor situado a la derecha a la variable o propiedad de la izquierda, y asigna el resultado a la variable o propiedad de su izquierda.</span><span class="sxs-lookup"><span data-stu-id="1fd51-114">The `+=` operator adds the value on its right to the variable or property on its left, and assigns the result to the variable or property on its left.</span></span> <span data-ttu-id="1fd51-115">El `+=` operador también se puede usar para concatenar la `String` expresión de su derecha a la `String` variable o propiedad de su izquierda y asignar el resultado a la variable o propiedad de su izquierda.</span><span class="sxs-lookup"><span data-stu-id="1fd51-115">The `+=` operator can also be used to concatenate the `String` expression on its right to the `String` variable or property on its left, and assign the result to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1fd51-116">Al utilizar el `+=` operador, es posible que no pueda determinar si se producirá la concatenación de cadenas o la suma.</span><span class="sxs-lookup"><span data-stu-id="1fd51-116">When you use the `+=` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="1fd51-117">Utilice el `&=` operador para la concatenación para eliminar la ambigüedad y proporcionar código autodocumentado.</span><span class="sxs-lookup"><span data-stu-id="1fd51-117">Use the `&=` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
 <span data-ttu-id="1fd51-118">Este operador de asignación realiza implícitamente conversiones de ampliación pero no de restricción si el entorno de compilación exige una semántica estricta.</span><span class="sxs-lookup"><span data-stu-id="1fd51-118">This assignment operator implicitly performs widening but not narrowing conversions if the compilation environment enforces strict semantics.</span></span> <span data-ttu-id="1fd51-119">Para obtener más información sobre estas conversiones, vea [conversiones de restricción y ampliación](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="1fd51-119">For more information on these conversions, see [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="1fd51-120">Para obtener más información sobre la semántica estricta y permisiva, vea [Option Strict (instrucción](../statements/option-strict-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="1fd51-120">For more information on strict and permissive semantics, see [Option Strict Statement](../statements/option-strict-statement.md).</span></span>  
  
 <span data-ttu-id="1fd51-121">Si se permite la semántica permisiva, el `+=` operador realiza implícitamente una serie de conversiones numéricas y de cadena idénticas a las realizadas por el `+` operador.</span><span class="sxs-lookup"><span data-stu-id="1fd51-121">If permissive semantics are allowed, the `+=` operator implicitly performs a variety of string and numeric conversions identical to those performed by the `+` operator.</span></span> <span data-ttu-id="1fd51-122">Para obtener más información sobre estas conversiones, vea [operador +](addition-operator.md).</span><span class="sxs-lookup"><span data-stu-id="1fd51-122">For details on these conversions, see [+ Operator](addition-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="1fd51-123">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="1fd51-123">Overloading</span></span>  

 <span data-ttu-id="1fd51-124">El `+` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="1fd51-124">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="1fd51-125">La sobrecarga del `+` operador afecta al comportamiento del `+=` operador.</span><span class="sxs-lookup"><span data-stu-id="1fd51-125">Overloading the `+` operator affects the behavior of the `+=` operator.</span></span> <span data-ttu-id="1fd51-126">Si el código utiliza `+=` en una clase o estructura que sobrecarga `+` , asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="1fd51-126">If your code uses `+=` on a class or structure that overloads `+`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="1fd51-127">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1fd51-127">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fd51-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1fd51-128">Example</span></span>  

 <span data-ttu-id="1fd51-129">En el ejemplo siguiente se usa el `+=` operador para combinar el valor de una variable con otra.</span><span class="sxs-lookup"><span data-stu-id="1fd51-129">The following example uses the `+=` operator to combine the value of one variable with another.</span></span> <span data-ttu-id="1fd51-130">La primera parte utiliza `+=` con variables numéricas para agregar un valor a otro.</span><span class="sxs-lookup"><span data-stu-id="1fd51-130">The first part uses `+=` with numeric variables to add one value to another.</span></span> <span data-ttu-id="1fd51-131">La segunda parte utiliza `+=` con `String` variables para concatenar un valor con otro.</span><span class="sxs-lookup"><span data-stu-id="1fd51-131">The second part uses `+=` with `String` variables to concatenate one value with another.</span></span> <span data-ttu-id="1fd51-132">En ambos casos, el resultado se asigna a la primera variable.</span><span class="sxs-lookup"><span data-stu-id="1fd51-132">In both cases, the result is assigned to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 <span data-ttu-id="1fd51-133">El valor de `num1` es ahora 13 y el valor de `str1` es ahora "103".</span><span class="sxs-lookup"><span data-stu-id="1fd51-133">The value of `num1` is now 13, and the value of `str1` is now "103".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fd51-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1fd51-134">See also</span></span>

- [<span data-ttu-id="1fd51-135">+ (Operador)</span><span class="sxs-lookup"><span data-stu-id="1fd51-135">+ Operator</span></span>](addition-operator.md)
- [<span data-ttu-id="1fd51-136">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="1fd51-136">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="1fd51-137">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="1fd51-137">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="1fd51-138">Operadores de concatenación</span><span class="sxs-lookup"><span data-stu-id="1fd51-138">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="1fd51-139">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1fd51-139">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="1fd51-140">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="1fd51-140">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="1fd51-141">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="1fd51-141">Statements</span></span>](../../programming-guide/language-features/statements.md)
