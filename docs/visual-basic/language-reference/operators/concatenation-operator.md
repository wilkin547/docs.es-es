---
title: '&amp; (Operador) (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: 28d8cdb22974d77edf055ab9b2c6c767872e6783
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604307"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="43103-102">&amp; (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="43103-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="43103-103">Genera una concatenación de cadena de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="43103-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43103-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43103-104">Syntax</span></span>  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="43103-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="43103-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="43103-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="43103-106">Required.</span></span> <span data-ttu-id="43103-107">Cualquier `String` o `Object` variable.</span><span class="sxs-lookup"><span data-stu-id="43103-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="43103-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="43103-108">Required.</span></span> <span data-ttu-id="43103-109">Cualquier expresión con un tipo de datos que se amplíe a `String`.</span><span class="sxs-lookup"><span data-stu-id="43103-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="43103-110">Requerido.</span><span class="sxs-lookup"><span data-stu-id="43103-110">Required.</span></span> <span data-ttu-id="43103-111">Cualquier expresión con un tipo de datos que se amplíe a `String`.</span><span class="sxs-lookup"><span data-stu-id="43103-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43103-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="43103-112">Remarks</span></span>  
 <span data-ttu-id="43103-113">Si el tipo de datos de `expression1` o `expression2` no `String` , pero se amplía a `String`, se convierte en `String`.</span><span class="sxs-lookup"><span data-stu-id="43103-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="43103-114">Si cualquiera de los tipos de datos no se amplía a `String`, el compilador genera un error.</span><span class="sxs-lookup"><span data-stu-id="43103-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="43103-115">Tipo de datos de `result` es `String`.</span><span class="sxs-lookup"><span data-stu-id="43103-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="43103-116">Si una o ambas expresiones se evalúan como [nada](../../../visual-basic/language-reference/nothing.md) o tener un valor de <xref:System.DBNull.Value?displayProperty=nameWithType>, se tratan como una cadena con un valor de "".</span><span class="sxs-lookup"><span data-stu-id="43103-116">If one or both expressions evaluate to [Nothing](../../../visual-basic/language-reference/nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43103-117">El `&` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="43103-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="43103-118">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="43103-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="43103-119">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="43103-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43103-120">El carácter "y" comercial (&) también pueden utilizarse para identificar las variables como tipo `Long`.</span><span class="sxs-lookup"><span data-stu-id="43103-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="43103-121">Para obtener más información, consulte [caracteres de tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span><span class="sxs-lookup"><span data-stu-id="43103-121">For more information, see [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="43103-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="43103-122">Example</span></span>  
 <span data-ttu-id="43103-123">Este ejemplo se utiliza la `&` operador para forzar la concatenación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="43103-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="43103-124">El resultado es un valor de cadena que representa la concatenación de los dos operandos de cadena.</span><span class="sxs-lookup"><span data-stu-id="43103-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="43103-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="43103-125">See Also</span></span>  
 [<span data-ttu-id="43103-126">Operador &=</span><span class="sxs-lookup"><span data-stu-id="43103-126">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="43103-127">Operadores de concatenación</span><span class="sxs-lookup"><span data-stu-id="43103-127">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [<span data-ttu-id="43103-128">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="43103-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="43103-129">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="43103-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="43103-130">Operadores de concatenación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="43103-130">Concatenation Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
