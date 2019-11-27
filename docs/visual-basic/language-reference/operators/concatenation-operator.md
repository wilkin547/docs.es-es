---
title: Operador &amp;
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
ms.openlocfilehash: 4cae7e59083890e82d754bdaa58942c2224357b0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336053"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="80196-102">Operador &amp; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80196-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="80196-103">Genera una concatenación de cadenas de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="80196-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80196-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80196-104">Syntax</span></span>  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="80196-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="80196-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="80196-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="80196-106">Required.</span></span> <span data-ttu-id="80196-107">Cualquier `String` o variable de `Object`.</span><span class="sxs-lookup"><span data-stu-id="80196-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="80196-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="80196-108">Required.</span></span> <span data-ttu-id="80196-109">Cualquier expresión con un tipo de datos que se amplíe a `String`.</span><span class="sxs-lookup"><span data-stu-id="80196-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="80196-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="80196-110">Required.</span></span> <span data-ttu-id="80196-111">Cualquier expresión con un tipo de datos que se amplíe a `String`.</span><span class="sxs-lookup"><span data-stu-id="80196-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80196-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="80196-112">Remarks</span></span>  
 <span data-ttu-id="80196-113">Si el tipo de datos de `expression1` o `expression2` no es `String` pero se amplía a `String`, se convierte en `String`.</span><span class="sxs-lookup"><span data-stu-id="80196-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="80196-114">Si alguno de los tipos de datos no se amplía a `String`, el compilador genera un error.</span><span class="sxs-lookup"><span data-stu-id="80196-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="80196-115">El tipo de datos de `result` es `String`.</span><span class="sxs-lookup"><span data-stu-id="80196-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="80196-116">Si una o ambas expresiones se evalúan como [Nothing](../../../visual-basic/language-reference/nothing.md) o tienen un valor de <xref:System.DBNull.Value?displayProperty=nameWithType>, se tratan como una cadena con un valor de "".</span><span class="sxs-lookup"><span data-stu-id="80196-116">If one or both expressions evaluate to [Nothing](../../../visual-basic/language-reference/nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80196-117">El operador de `&` se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="80196-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="80196-118">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="80196-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="80196-119">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="80196-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80196-120">El carácter de y comercial (&) también se puede usar para identificar variables como tipo `Long`.</span><span class="sxs-lookup"><span data-stu-id="80196-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="80196-121">Para obtener más información, vea [caracteres de tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span><span class="sxs-lookup"><span data-stu-id="80196-121">For more information, see [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="80196-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="80196-122">Example</span></span>  
 <span data-ttu-id="80196-123">En este ejemplo se usa el operador `&` para forzar la concatenación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="80196-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="80196-124">El resultado es un valor de cadena que representa la concatenación de los dos operandos de cadena.</span><span class="sxs-lookup"><span data-stu-id="80196-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="80196-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="80196-125">See also</span></span>

- [<span data-ttu-id="80196-126">Operador &=</span><span class="sxs-lookup"><span data-stu-id="80196-126">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="80196-127">Operadores de concatenación</span><span class="sxs-lookup"><span data-stu-id="80196-127">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="80196-128">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="80196-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="80196-129">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="80196-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="80196-130">Operadores de concatenación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="80196-130">Concatenation Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
