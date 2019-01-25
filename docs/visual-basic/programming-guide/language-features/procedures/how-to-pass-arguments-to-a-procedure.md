---
title: Procedimiento Pasar argumentos a un procedimiento (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- arguments [Visual Basic], passing to procedures
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], calling
- argument passing [Visual Basic], procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
ms.openlocfilehash: 6d9daf47b8d9300e9de8add1423fa1824fc62d5d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691234"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="44a94-102">Procedimiento Pasar argumentos a un procedimiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44a94-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="44a94-103">Cuando se llama a un procedimiento, siga el nombre del procedimiento con una lista de argumentos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="44a94-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="44a94-104">Se proporciona un argumento correspondiente a cada parámetro necesario que se define el procedimiento y, opcionalmente, puede proporcionar argumentos a la `Optional` parámetros.</span><span class="sxs-lookup"><span data-stu-id="44a94-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="44a94-105">Si no se suministra un `Optional` parámetro de la llamada, debe incluir una coma para marcar su lugar en la lista de argumentos si está proporcionando los argumentos subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="44a94-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="44a94-106">Si va a pasar un argumento de tipo de datos diferente del parámetro correspondiente, como `Byte` a `String`, puede establecer el modificador de comprobación de tipos ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) a `Off`.</span><span class="sxs-lookup"><span data-stu-id="44a94-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="44a94-107">Si `Option Strict` es `On`, se deben usar conversiones de ampliación o palabras clave de conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="44a94-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="44a94-108">Para obtener más información, consulte [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) y [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="44a94-108">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="44a94-109">Para obtener más información, consulte [argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="44a94-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="44a94-110">Para pasar uno o más argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="44a94-110">To pass one or more arguments to a procedure</span></span>  
  
1.  <span data-ttu-id="44a94-111">En la instrucción de llamada, siga el nombre del procedimiento con paréntesis.</span><span class="sxs-lookup"><span data-stu-id="44a94-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2.  <span data-ttu-id="44a94-112">Dentro de los paréntesis, coloque una lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="44a94-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="44a94-113">Incluir un argumento para cada parámetro necesario que el procedimiento define y separe los argumentos con comas.</span><span class="sxs-lookup"><span data-stu-id="44a94-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3.  <span data-ttu-id="44a94-114">Asegúrese de que cada argumento es una expresión válida que se evalúa como un tipo de datos convertible al tipo el procedimiento se define para el parámetro correspondiente.</span><span class="sxs-lookup"><span data-stu-id="44a94-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4.  <span data-ttu-id="44a94-115">Si se define un parámetro como [opcional](../../../../visual-basic/language-reference/modifiers/optional.md), puede incluirlo en la lista de argumentos u omitirlo.</span><span class="sxs-lookup"><span data-stu-id="44a94-115">If a parameter is defined as [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="44a94-116">Si se omite, el procedimiento utiliza el valor predeterminado definido para ese parámetro.</span><span class="sxs-lookup"><span data-stu-id="44a94-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5.  <span data-ttu-id="44a94-117">Si se omite un argumento para un `Optional` parámetro y hay otro parámetro después de él en la lista de parámetros, puede marcar el lugar del argumento omitido por una coma adicional en la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="44a94-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="44a94-118">El ejemplo siguiente se llama a la de Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> función.</span><span class="sxs-lookup"><span data-stu-id="44a94-118">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     [!code-vb[VbVbcnProcedures#34](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]  
  
     <span data-ttu-id="44a94-119">El ejemplo anterior proporciona el primer argumento necesario, que es la cadena de mensaje que se mostrará.</span><span class="sxs-lookup"><span data-stu-id="44a94-119">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="44a94-120">Omite un argumento para el segundo parámetro opcional que especifica los botones que deben mostrarse en el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="44a94-120">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="44a94-121">Dado que la llamada no proporciona un valor, `MsgBox` utiliza el valor predeterminado, `MsgBoxStyle.OKOnly`, que muestra sólo un **Aceptar** botón.</span><span class="sxs-lookup"><span data-stu-id="44a94-121">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="44a94-122">El segundo punto y coma en la lista de argumentos marca el lugar del segundo argumento se omite y la última cadena se pasa al tercer parámetro opcional de `MsgBox`, que es el texto que se mostrará en la barra de título.</span><span class="sxs-lookup"><span data-stu-id="44a94-122">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44a94-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="44a94-123">See also</span></span>

- [<span data-ttu-id="44a94-124">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="44a94-124">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="44a94-125">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="44a94-125">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="44a94-126">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="44a94-126">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="44a94-127">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="44a94-127">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="44a94-128">Cómo: Definir un parámetro para un procedimiento</span><span class="sxs-lookup"><span data-stu-id="44a94-128">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="44a94-129">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="44a94-129">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="44a94-130">Procedimientos recursivos</span><span class="sxs-lookup"><span data-stu-id="44a94-130">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="44a94-131">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="44a94-131">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="44a94-132">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="44a94-132">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="44a94-133">Programación orientada a objetos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44a94-133">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
