---
description: 'Más información acerca de: &amp; = (operador) (Visual Basic)'
title: '&amp;= (Operador)'
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: ffc4de352ee29f4c7d18a257dd3699b37c668db7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774322"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="d4f8d-103">&amp;Operador = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4f8d-103">&amp;= Operator (Visual Basic)</span></span>

<span data-ttu-id="d4f8d-104">Concatena una `String` expresión a una `String` variable o propiedad y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="d4f8d-104">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4f8d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4f8d-105">Syntax</span></span>  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="d4f8d-106">Partes</span><span class="sxs-lookup"><span data-stu-id="d4f8d-106">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="d4f8d-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="d4f8d-107">Required.</span></span> <span data-ttu-id="d4f8d-108">Cualquier `String` variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="d4f8d-108">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="d4f8d-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d4f8d-109">Required.</span></span> <span data-ttu-id="d4f8d-110">Cualquier expresión `String` .</span><span class="sxs-lookup"><span data-stu-id="d4f8d-110">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4f8d-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d4f8d-111">Remarks</span></span>  

 <span data-ttu-id="d4f8d-112">El elemento del lado izquierdo del `&=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="d4f8d-112">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="d4f8d-113">La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="d4f8d-113">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span> <span data-ttu-id="d4f8d-114">El `&=` operador concatena la `String` expresión de su derecha a la `String` variable o propiedad de su izquierda, y asigna el resultado a la variable o propiedad de su izquierda.</span><span class="sxs-lookup"><span data-stu-id="d4f8d-114">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="d4f8d-115">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="d4f8d-115">Overloading</span></span>  

 <span data-ttu-id="d4f8d-116">El [ operador de&](concatenation-operator.md) se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="d4f8d-116">The [& Operator](concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="d4f8d-117">La sobrecarga del `&` operador afecta al comportamiento del `&=` operador.</span><span class="sxs-lookup"><span data-stu-id="d4f8d-117">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="d4f8d-118">Si el código utiliza `&=` en una clase o estructura que sobrecarga `&` , asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="d4f8d-118">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="d4f8d-119">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d4f8d-119">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4f8d-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d4f8d-120">Example</span></span>  

 <span data-ttu-id="d4f8d-121">En el ejemplo siguiente se usa el `&=` operador para concatenar dos `String` variables y asignar el resultado a la primera variable.</span><span class="sxs-lookup"><span data-stu-id="d4f8d-121">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="d4f8d-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4f8d-122">See also</span></span>

- [<span data-ttu-id="d4f8d-123">& (operador)</span><span class="sxs-lookup"><span data-stu-id="d4f8d-123">& Operator</span></span>](concatenation-operator.md)
- [<span data-ttu-id="d4f8d-124">Operador + =</span><span class="sxs-lookup"><span data-stu-id="d4f8d-124">+= Operator</span></span>](addition-assignment-operator.md)
- [<span data-ttu-id="d4f8d-125">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="d4f8d-125">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="d4f8d-126">Operadores de concatenación</span><span class="sxs-lookup"><span data-stu-id="d4f8d-126">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="d4f8d-127">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4f8d-127">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="d4f8d-128">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="d4f8d-128">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="d4f8d-129">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="d4f8d-129">Statements</span></span>](../../programming-guide/language-features/statements.md)
