---
title: '&amp;Operador (Visual Basic)'
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
ms.openlocfilehash: d387b2dfdbb3fefe357364f7b2a3dde155cbd489
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968351"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="26c7c-102">&amp;Operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26c7c-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="26c7c-103">Genera una concatenación de cadenas de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="26c7c-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26c7c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26c7c-104">Syntax</span></span>  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="26c7c-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="26c7c-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="26c7c-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="26c7c-106">Required.</span></span> <span data-ttu-id="26c7c-107">Cualquier `String` variable `Object` o.</span><span class="sxs-lookup"><span data-stu-id="26c7c-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="26c7c-108">Necesario.</span><span class="sxs-lookup"><span data-stu-id="26c7c-108">Required.</span></span> <span data-ttu-id="26c7c-109">Cualquier expresión con un tipo de datos que se amplíe `String`a.</span><span class="sxs-lookup"><span data-stu-id="26c7c-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="26c7c-110">Necesario.</span><span class="sxs-lookup"><span data-stu-id="26c7c-110">Required.</span></span> <span data-ttu-id="26c7c-111">Cualquier expresión con un tipo de datos que se amplíe `String`a.</span><span class="sxs-lookup"><span data-stu-id="26c7c-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26c7c-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="26c7c-112">Remarks</span></span>  
 <span data-ttu-id="26c7c-113">Si el tipo de datos `expression1` de `expression2` o no `String` es pero se amplía `String`a, se convierte en `String`.</span><span class="sxs-lookup"><span data-stu-id="26c7c-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="26c7c-114">Si uno de los tipos de datos no se amplía `String`a, el compilador genera un error.</span><span class="sxs-lookup"><span data-stu-id="26c7c-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="26c7c-115">El tipo de datos `result` de `String`es.</span><span class="sxs-lookup"><span data-stu-id="26c7c-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="26c7c-116">Si una o ambas expresiones se evalúan como [Nothing](../../../visual-basic/language-reference/nothing.md) o tienen un <xref:System.DBNull.Value?displayProperty=nameWithType>valor de, se tratan como una cadena con un valor de "".</span><span class="sxs-lookup"><span data-stu-id="26c7c-116">If one or both expressions evaluate to [Nothing](../../../visual-basic/language-reference/nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="26c7c-117">El `&` operador se puedesobrecargar, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="26c7c-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="26c7c-118">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="26c7c-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="26c7c-119">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="26c7c-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="26c7c-120">El carácter de y comercial (&) también se puede usar para identificar variables `Long`como tipo.</span><span class="sxs-lookup"><span data-stu-id="26c7c-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="26c7c-121">Para obtener más información, vea [caracteres de tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span><span class="sxs-lookup"><span data-stu-id="26c7c-121">For more information, see [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="26c7c-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26c7c-122">Example</span></span>  
 <span data-ttu-id="26c7c-123">En este ejemplo se `&` usa el operador para forzar la concatenación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="26c7c-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="26c7c-124">El resultado es un valor de cadena que representa la concatenación de los dos operandos de cadena.</span><span class="sxs-lookup"><span data-stu-id="26c7c-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="26c7c-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="26c7c-125">See also</span></span>

- [<span data-ttu-id="26c7c-126">Operador &=</span><span class="sxs-lookup"><span data-stu-id="26c7c-126">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="26c7c-127">Operadores de concatenación</span><span class="sxs-lookup"><span data-stu-id="26c7c-127">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="26c7c-128">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26c7c-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="26c7c-129">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="26c7c-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="26c7c-130">Operadores de concatenación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26c7c-130">Concatenation Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
