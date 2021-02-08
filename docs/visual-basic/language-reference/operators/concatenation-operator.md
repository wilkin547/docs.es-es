---
description: 'Más información acerca de: &amp; operador (Visual Basic)'
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
ms.openlocfilehash: ba7c94805e805c841d05241fef557ca972a19ae9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774101"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="e5ca0-103">&amp; Operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5ca0-103">&amp; Operator (Visual Basic)</span></span>

<span data-ttu-id="e5ca0-104">Genera una concatenación de cadenas de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-104">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5ca0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5ca0-105">Syntax</span></span>  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="e5ca0-106">Partes</span><span class="sxs-lookup"><span data-stu-id="e5ca0-106">Parts</span></span>  

 `result`  
 <span data-ttu-id="e5ca0-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-107">Required.</span></span> <span data-ttu-id="e5ca0-108">Cualquier `String` `Object` variable o.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-108">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="e5ca0-109">Necesario.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-109">Required.</span></span> <span data-ttu-id="e5ca0-110">Cualquier expresión con un tipo de datos que se amplíe a `String` .</span><span class="sxs-lookup"><span data-stu-id="e5ca0-110">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="e5ca0-111">Necesario.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-111">Required.</span></span> <span data-ttu-id="e5ca0-112">Cualquier expresión con un tipo de datos que se amplíe a `String` .</span><span class="sxs-lookup"><span data-stu-id="e5ca0-112">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5ca0-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e5ca0-113">Remarks</span></span>  

 <span data-ttu-id="e5ca0-114">Si el tipo de datos de `expression1` o `expression2` no es `String` pero se amplía a `String` , se convierte en `String` .</span><span class="sxs-lookup"><span data-stu-id="e5ca0-114">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="e5ca0-115">Si uno de los tipos de datos no se amplía a `String` , el compilador genera un error.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-115">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="e5ca0-116">El tipo de datos de `result` es `String` .</span><span class="sxs-lookup"><span data-stu-id="e5ca0-116">The data type of `result` is `String`.</span></span> <span data-ttu-id="e5ca0-117">Si una o ambas expresiones se evalúan como [Nothing](../nothing.md) o tienen un valor de <xref:System.DBNull.Value?displayProperty=nameWithType> , se tratan como una cadena con un valor de "".</span><span class="sxs-lookup"><span data-stu-id="e5ca0-117">If one or both expressions evaluate to [Nothing](../nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5ca0-118">El `&` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-118">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e5ca0-119">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="e5ca0-120">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e5ca0-120">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5ca0-121">El carácter de y comercial (&) también se puede usar para identificar variables como tipo `Long` .</span><span class="sxs-lookup"><span data-stu-id="e5ca0-121">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="e5ca0-122">Para obtener más información, vea [caracteres de tipo](../../programming-guide/language-features/data-types/type-characters.md).</span><span class="sxs-lookup"><span data-stu-id="e5ca0-122">For more information, see [Type Characters](../../programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5ca0-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5ca0-123">Example</span></span>  

 <span data-ttu-id="e5ca0-124">En este ejemplo se usa el `&` operador para forzar la concatenación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-124">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="e5ca0-125">El resultado es un valor de cadena que representa la concatenación de los dos operandos de cadena.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-125">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e5ca0-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5ca0-126">See also</span></span>

- [<span data-ttu-id="e5ca0-127">&= (operador)</span><span class="sxs-lookup"><span data-stu-id="e5ca0-127">&= Operator</span></span>](and-assignment-operator.md)
- [<span data-ttu-id="e5ca0-128">Operadores de concatenación</span><span class="sxs-lookup"><span data-stu-id="e5ca0-128">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="e5ca0-129">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5ca0-129">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="e5ca0-130">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="e5ca0-130">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="e5ca0-131">Operadores de concatenación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5ca0-131">Concatenation Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
