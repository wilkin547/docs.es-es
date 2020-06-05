---
title: Procedimiento para pasar argumentos a un procedimiento
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
ms.openlocfilehash: 903e05facccd1f2afdf4bb51b200531feb64aa79
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387782"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="ad242-102">Cómo: Pasar argumentos a un procedimiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad242-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="ad242-103">Cuando se llama a un procedimiento, se sigue el nombre del procedimiento con una lista de argumentos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="ad242-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="ad242-104">Proporcione un argumento correspondiente a cada parámetro necesario que el procedimiento define y, opcionalmente, puede proporcionar argumentos a los `Optional` parámetros.</span><span class="sxs-lookup"><span data-stu-id="ad242-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="ad242-105">Si no proporciona un `Optional` parámetro en la llamada, debe incluir una coma para marcar su lugar en la lista de argumentos si está proporcionando los argumentos subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="ad242-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="ad242-106">Si piensa pasar un argumento de un tipo de datos distinto del parámetro correspondiente, como `Byte` a `String` , puede establecer el modificador de comprobación de tipo ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) en `Off` .</span><span class="sxs-lookup"><span data-stu-id="ad242-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="ad242-107">Si `Option Strict` es `On` , se deben usar conversiones de ampliación o palabras clave de conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="ad242-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="ad242-108">Para obtener más información, vea [conversiones de ampliación y de restricción](../data-types/widening-and-narrowing-conversions.md) y [funciones de conversión de tipos](../../../language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="ad242-108">For more information, see [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="ad242-109">Para obtener más información, vea [argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="ad242-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="ad242-110">Para pasar uno o más argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="ad242-110">To pass one or more arguments to a procedure</span></span>  
  
1. <span data-ttu-id="ad242-111">En la instrucción de llamada, siga el nombre del procedimiento entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="ad242-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2. <span data-ttu-id="ad242-112">Dentro de los paréntesis, coloque una lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="ad242-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="ad242-113">Incluya un argumento para cada parámetro necesario que defina el procedimiento y sepárelos con comas.</span><span class="sxs-lookup"><span data-stu-id="ad242-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3. <span data-ttu-id="ad242-114">Asegúrese de que cada argumento es una expresión válida que se evalúa como un tipo de datos que se pueda convertir al tipo definido por el procedimiento para el parámetro correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ad242-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4. <span data-ttu-id="ad242-115">Si un parámetro se define como [opcional](../../../language-reference/modifiers/optional.md), puede incluirlo en la lista de argumentos u omitirlo.</span><span class="sxs-lookup"><span data-stu-id="ad242-115">If a parameter is defined as [Optional](../../../language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="ad242-116">Si lo omite, el procedimiento utiliza el valor predeterminado definido para ese parámetro.</span><span class="sxs-lookup"><span data-stu-id="ad242-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5. <span data-ttu-id="ad242-117">Si omite un argumento para un `Optional` parámetro y hay otro parámetro detrás de él en la lista de parámetros, puede marcar el lugar del argumento omitido mediante una coma adicional en la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="ad242-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="ad242-118">En el ejemplo siguiente se llama a la <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> función Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ad242-118">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     <span data-ttu-id="ad242-119">En el ejemplo anterior se proporciona el primer argumento necesario, que es la cadena de mensaje que se va a mostrar.</span><span class="sxs-lookup"><span data-stu-id="ad242-119">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="ad242-120">Omite un argumento para el segundo parámetro opcional, que especifica los botones que se van a mostrar en el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="ad242-120">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="ad242-121">Dado que la llamada no proporciona un valor, `MsgBox` usa el valor predeterminado, `MsgBoxStyle.OKOnly` , que solo muestra un botón **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="ad242-121">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="ad242-122">La segunda coma de la lista de argumentos marca el lugar del segundo argumento omitido, y la última cadena se pasa al tercer parámetro opcional de `MsgBox` , que es el texto que se va a mostrar en la barra de título.</span><span class="sxs-lookup"><span data-stu-id="ad242-122">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad242-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ad242-123">See also</span></span>

- [<span data-ttu-id="ad242-124">Procedimientos Sub</span><span class="sxs-lookup"><span data-stu-id="ad242-124">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="ad242-125">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="ad242-125">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="ad242-126">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="ad242-126">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="ad242-127">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="ad242-127">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="ad242-128">Procedimiento para definir un parámetro para un procedimiento</span><span class="sxs-lookup"><span data-stu-id="ad242-128">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="ad242-129">Pasar argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="ad242-129">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="ad242-130">Procedimientos recursivos</span><span class="sxs-lookup"><span data-stu-id="ad242-130">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="ad242-131">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="ad242-131">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="ad242-132">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="ad242-132">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="ad242-133">Programación orientada a objetos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad242-133">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
