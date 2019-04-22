---
title: '&amp; Operador (Visual Basic)'
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
ms.openlocfilehash: dd85363447e9b405241d608550d9484b4760a739
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58817284"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="6b29d-102">&amp; Operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b29d-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="6b29d-103">Genera una concatenación de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="6b29d-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b29d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b29d-104">Syntax</span></span>  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="6b29d-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="6b29d-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="6b29d-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="6b29d-106">Required.</span></span> <span data-ttu-id="6b29d-107">Cualquier `String` o `Object` variable.</span><span class="sxs-lookup"><span data-stu-id="6b29d-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="6b29d-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="6b29d-108">Required.</span></span> <span data-ttu-id="6b29d-109">Cualquier expresión con un tipo de datos que se amplía a `String`.</span><span class="sxs-lookup"><span data-stu-id="6b29d-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="6b29d-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="6b29d-110">Required.</span></span> <span data-ttu-id="6b29d-111">Cualquier expresión con un tipo de datos que se amplía a `String`.</span><span class="sxs-lookup"><span data-stu-id="6b29d-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b29d-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6b29d-112">Remarks</span></span>  
 <span data-ttu-id="6b29d-113">Si el tipo de datos de `expression1` o `expression2` no `String` pero se amplía a `String`, se convierte en `String`.</span><span class="sxs-lookup"><span data-stu-id="6b29d-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="6b29d-114">Si cualquiera de los tipos de datos no se amplía a `String`, el compilador genera un error.</span><span class="sxs-lookup"><span data-stu-id="6b29d-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="6b29d-115">Tipo de datos de `result` es `String`.</span><span class="sxs-lookup"><span data-stu-id="6b29d-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="6b29d-116">Si una o ambas expresiones se evalúan como [nada](../../../visual-basic/language-reference/nothing.md) o tiene un valor de <xref:System.DBNull.Value?displayProperty=nameWithType>, se tratan como una cadena con un valor de "".</span><span class="sxs-lookup"><span data-stu-id="6b29d-116">If one or both expressions evaluate to [Nothing](../../../visual-basic/language-reference/nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b29d-117">El `&` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="6b29d-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="6b29d-118">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="6b29d-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="6b29d-119">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="6b29d-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b29d-120">El carácter de y comercial (&) también pueden utilizarse para identificar las variables como tipo `Long`.</span><span class="sxs-lookup"><span data-stu-id="6b29d-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="6b29d-121">Para obtener más información, consulte [caracteres de tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span><span class="sxs-lookup"><span data-stu-id="6b29d-121">For more information, see [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b29d-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b29d-122">Example</span></span>  
 <span data-ttu-id="6b29d-123">Este ejemplo se usa el `&` operador para forzar la concatenación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="6b29d-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="6b29d-124">El resultado es un valor de cadena que representa la concatenación de los dos operandos de cadena.</span><span class="sxs-lookup"><span data-stu-id="6b29d-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="6b29d-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b29d-125">See also</span></span>

- [<span data-ttu-id="6b29d-126">Operador &=</span><span class="sxs-lookup"><span data-stu-id="6b29d-126">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="6b29d-127">Operadores de concatenación</span><span class="sxs-lookup"><span data-stu-id="6b29d-127">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="6b29d-128">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6b29d-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="6b29d-129">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="6b29d-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="6b29d-130">Operadores de concatenación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6b29d-130">Concatenation Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
