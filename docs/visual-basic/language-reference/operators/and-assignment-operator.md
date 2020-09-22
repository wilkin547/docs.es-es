---
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
ms.openlocfilehash: 9b77c44aa77afd59e36e1d21451205d3929ef527
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874881"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="927d8-102">&amp;Operador = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="927d8-102">&amp;= Operator (Visual Basic)</span></span>

<span data-ttu-id="927d8-103">Concatena una `String` expresión a una `String` variable o propiedad y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="927d8-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="927d8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="927d8-104">Syntax</span></span>  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="927d8-105">Partes</span><span class="sxs-lookup"><span data-stu-id="927d8-105">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="927d8-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="927d8-106">Required.</span></span> <span data-ttu-id="927d8-107">Cualquier `String` variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="927d8-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="927d8-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="927d8-108">Required.</span></span> <span data-ttu-id="927d8-109">Cualquier expresión `String` .</span><span class="sxs-lookup"><span data-stu-id="927d8-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="927d8-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="927d8-110">Remarks</span></span>  

 <span data-ttu-id="927d8-111">El elemento del lado izquierdo del `&=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="927d8-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="927d8-112">La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="927d8-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span> <span data-ttu-id="927d8-113">El `&=` operador concatena la `String` expresión de su derecha a la `String` variable o propiedad de su izquierda, y asigna el resultado a la variable o propiedad de su izquierda.</span><span class="sxs-lookup"><span data-stu-id="927d8-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="927d8-114">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="927d8-114">Overloading</span></span>  

 <span data-ttu-id="927d8-115">El [ operador de&](concatenation-operator.md) se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="927d8-115">The [& Operator](concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="927d8-116">La sobrecarga del `&` operador afecta al comportamiento del `&=` operador.</span><span class="sxs-lookup"><span data-stu-id="927d8-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="927d8-117">Si el código utiliza `&=` en una clase o estructura que sobrecarga `&` , asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="927d8-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="927d8-118">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="927d8-118">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="927d8-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="927d8-119">Example</span></span>  

 <span data-ttu-id="927d8-120">En el ejemplo siguiente se usa el `&=` operador para concatenar dos `String` variables y asignar el resultado a la primera variable.</span><span class="sxs-lookup"><span data-stu-id="927d8-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="927d8-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="927d8-121">See also</span></span>

- [<span data-ttu-id="927d8-122">& (operador)</span><span class="sxs-lookup"><span data-stu-id="927d8-122">& Operator</span></span>](concatenation-operator.md)
- [<span data-ttu-id="927d8-123">Operador + =</span><span class="sxs-lookup"><span data-stu-id="927d8-123">+= Operator</span></span>](addition-assignment-operator.md)
- [<span data-ttu-id="927d8-124">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="927d8-124">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="927d8-125">Operadores de concatenación</span><span class="sxs-lookup"><span data-stu-id="927d8-125">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="927d8-126">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="927d8-126">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="927d8-127">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="927d8-127">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="927d8-128">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="927d8-128">Statements</span></span>](../../programming-guide/language-features/statements.md)
