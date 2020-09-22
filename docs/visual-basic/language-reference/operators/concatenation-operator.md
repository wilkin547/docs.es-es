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
ms.openlocfilehash: 20c2e2088691e68221872cc1dfc5486413515a4d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867154"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="91120-102">&amp; Operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91120-102">&amp; Operator (Visual Basic)</span></span>

<span data-ttu-id="91120-103">Genera una concatenación de cadenas de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="91120-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91120-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91120-104">Syntax</span></span>  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="91120-105">Partes</span><span class="sxs-lookup"><span data-stu-id="91120-105">Parts</span></span>  

 `result`  
 <span data-ttu-id="91120-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="91120-106">Required.</span></span> <span data-ttu-id="91120-107">Cualquier `String` `Object` variable o.</span><span class="sxs-lookup"><span data-stu-id="91120-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="91120-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="91120-108">Required.</span></span> <span data-ttu-id="91120-109">Cualquier expresión con un tipo de datos que se amplíe a `String` .</span><span class="sxs-lookup"><span data-stu-id="91120-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="91120-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="91120-110">Required.</span></span> <span data-ttu-id="91120-111">Cualquier expresión con un tipo de datos que se amplíe a `String` .</span><span class="sxs-lookup"><span data-stu-id="91120-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91120-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="91120-112">Remarks</span></span>  

 <span data-ttu-id="91120-113">Si el tipo de datos de `expression1` o `expression2` no es `String` pero se amplía a `String` , se convierte en `String` .</span><span class="sxs-lookup"><span data-stu-id="91120-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="91120-114">Si uno de los tipos de datos no se amplía a `String` , el compilador genera un error.</span><span class="sxs-lookup"><span data-stu-id="91120-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="91120-115">El tipo de datos de `result` es `String` .</span><span class="sxs-lookup"><span data-stu-id="91120-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="91120-116">Si una o ambas expresiones se evalúan como [Nothing](../nothing.md) o tienen un valor de <xref:System.DBNull.Value?displayProperty=nameWithType> , se tratan como una cadena con un valor de "".</span><span class="sxs-lookup"><span data-stu-id="91120-116">If one or both expressions evaluate to [Nothing](../nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="91120-117">El `&` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="91120-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="91120-118">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="91120-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="91120-119">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="91120-119">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="91120-120">El carácter de y comercial (&) también se puede usar para identificar variables como tipo `Long` .</span><span class="sxs-lookup"><span data-stu-id="91120-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="91120-121">Para obtener más información, vea [caracteres de tipo](../../programming-guide/language-features/data-types/type-characters.md).</span><span class="sxs-lookup"><span data-stu-id="91120-121">For more information, see [Type Characters](../../programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="91120-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="91120-122">Example</span></span>  

 <span data-ttu-id="91120-123">En este ejemplo se usa el `&` operador para forzar la concatenación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="91120-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="91120-124">El resultado es un valor de cadena que representa la concatenación de los dos operandos de cadena.</span><span class="sxs-lookup"><span data-stu-id="91120-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="91120-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="91120-125">See also</span></span>

- [<span data-ttu-id="91120-126">&= (operador)</span><span class="sxs-lookup"><span data-stu-id="91120-126">&= Operator</span></span>](and-assignment-operator.md)
- [<span data-ttu-id="91120-127">Operadores de concatenación</span><span class="sxs-lookup"><span data-stu-id="91120-127">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="91120-128">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="91120-128">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="91120-129">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="91120-129">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="91120-130">Operadores de concatenación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="91120-130">Concatenation Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
