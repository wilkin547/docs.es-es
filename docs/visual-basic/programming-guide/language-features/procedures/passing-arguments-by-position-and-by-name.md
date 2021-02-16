---
description: Más información acerca de cómo pasar argumentos por posición y por nombre (Visual Basic)
title: Pasar argumentos por posición o por nombre
ms.date: 02/01/2018
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
ms.openlocfilehash: 2938638bbdeb411bec53f338371d4215140dc4a0
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466697"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="a23a6-103">Pasar argumentos por posición o por nombre (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a23a6-103">Passing Arguments by Position and by Name (Visual Basic)</span></span>

<span data-ttu-id="a23a6-104">Cuando se llama a `Sub` un `Function` procedimiento o, se pueden pasar argumentos *por posición* , en el orden en que aparecen en la definición del procedimiento, o bien se pueden pasar *por nombre*, sin tener en cuenta la posición.</span><span class="sxs-lookup"><span data-stu-id="a23a6-104">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>

<span data-ttu-id="a23a6-105">Cuando se pasa un argumento por nombre, se especifica el nombre declarado del argumento seguido de dos puntos y un signo igual ( `:=` ), seguido del valor del argumento.</span><span class="sxs-lookup"><span data-stu-id="a23a6-105">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="a23a6-106">Puede proporcionar argumentos con nombre en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="a23a6-106">You can supply named arguments in any order.</span></span>

<span data-ttu-id="a23a6-107">Por ejemplo, el siguiente `Sub` procedimiento toma tres argumentos:</span><span class="sxs-lookup"><span data-stu-id="a23a6-107">For example, the following `Sub` procedure takes three arguments:</span></span>

[!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]

<span data-ttu-id="a23a6-108">Al llamar a este procedimiento, puede proporcionar los argumentos por posición, por nombre o mediante una combinación de ambos.</span><span class="sxs-lookup"><span data-stu-id="a23a6-108">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>

## <a name="passing-arguments-by-position"></a><span data-ttu-id="a23a6-109">Pasar argumentos por posición</span><span class="sxs-lookup"><span data-stu-id="a23a6-109">Passing Arguments by Position</span></span>

<span data-ttu-id="a23a6-110">Puede llamar al `Display` método con sus argumentos pasados por posición y delimitados por comas, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a23a6-110">You can call the `Display` method with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>

[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)]

<span data-ttu-id="a23a6-111">Si omite un argumento opcional en una lista de argumentos posicionales, debe mantener su lugar con una coma.</span><span class="sxs-lookup"><span data-stu-id="a23a6-111">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="a23a6-112">En el ejemplo siguiente se llama al `Display` método sin el `age` argumento:</span><span class="sxs-lookup"><span data-stu-id="a23a6-112">The following example calls the `Display` method without the `age` argument:</span></span>

[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)]

## <a name="passing-arguments-by-name"></a><span data-ttu-id="a23a6-113">Pasar argumentos por nombre</span><span class="sxs-lookup"><span data-stu-id="a23a6-113">Passing Arguments by Name</span></span>

<span data-ttu-id="a23a6-114">Como alternativa, puede llamar a `Display` con los argumentos pasados por nombre, también delimitados por comas, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a23a6-114">Alternatively, you can call `Display` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>

[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)]

<span data-ttu-id="a23a6-115">Pasar argumentos por nombre de esta manera es especialmente útil cuando se llama a un procedimiento que tiene más de un argumento opcional.</span><span class="sxs-lookup"><span data-stu-id="a23a6-115">Passing arguments by name in this way is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="a23a6-116">Si proporciona argumentos por nombre, no tiene que usar comas consecutivas para indicar que faltan argumentos posicionales.</span><span class="sxs-lookup"><span data-stu-id="a23a6-116">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="a23a6-117">Pasar argumentos por nombre también facilita la realización de un seguimiento de los argumentos que se superan y de los que se omiten.</span><span class="sxs-lookup"><span data-stu-id="a23a6-117">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>

## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="a23a6-118">Mezclar argumentos por posición y por nombre</span><span class="sxs-lookup"><span data-stu-id="a23a6-118">Mixing Arguments by Position and by Name</span></span>

<span data-ttu-id="a23a6-119">Puede proporcionar argumentos por posición y por nombre en una única llamada de procedimiento, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a23a6-119">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)]

<span data-ttu-id="a23a6-120">En el ejemplo anterior, no es necesario disponer de una coma adicional para contener el lugar del argumento omitido `age` , ya que `birth` se pasa por nombre.</span><span class="sxs-lookup"><span data-stu-id="a23a6-120">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>

<span data-ttu-id="a23a6-121">En las versiones de Visual Basic antes 15,5, cuando se proporcionan argumentos mediante una combinación de posición y nombre, los argumentos posicionales deben aparecer en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="a23a6-121">In versions of Visual Basic before 15.5, when you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="a23a6-122">Una vez que se proporciona un argumento por nombre, todos los argumentos restantes deben pasarse por nombre.</span><span class="sxs-lookup"><span data-stu-id="a23a6-122">Once you supply an argument by name, any remaining arguments must all be passed by name.</span></span>  <span data-ttu-id="a23a6-123">Por ejemplo, la siguiente llamada al `Display` método muestra el error del compilador [BC30241: se esperaba un argumento con nombre](../../../misc/bc30241.md).</span><span class="sxs-lookup"><span data-stu-id="a23a6-123">For example, the following call to the `Display` method displays compiler error [BC30241: Named argument expected](../../../misc/bc30241.md).</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)]

<span data-ttu-id="a23a6-124">A partir de Visual Basic 15,5, los argumentos posicionales pueden seguir los argumentos con nombre si los argumentos posicionales de final están en la posición correcta.</span><span class="sxs-lookup"><span data-stu-id="a23a6-124">Starting with Visual Basic 15.5, positional arguments can follow named arguments if the ending positional arguments are in the correct position.</span></span> <span data-ttu-id="a23a6-125">Si se compila en Visual Basic 15,5, la llamada anterior al `Display` método se compila correctamente y ya no genera un error del compilador [BC30241](../../../misc/bc30241.md).</span><span class="sxs-lookup"><span data-stu-id="a23a6-125">If compiled under Visual Basic 15.5, the previous call to the `Display` method compiles successfully and no longer generates compiler error [BC30241](../../../misc/bc30241.md).</span></span>

<span data-ttu-id="a23a6-126">Esta capacidad de mezclar y coincidir con argumentos con nombre y posicionales en cualquier orden es especialmente útil cuando se desea usar un argumento con nombre para que el código sea más legible.</span><span class="sxs-lookup"><span data-stu-id="a23a6-126">This ability to mix and match named and positional arguments in any order is particularly useful when you want to use a named argument to make your code more readable.</span></span> <span data-ttu-id="a23a6-127">Por ejemplo, el siguiente `Person` constructor de clase requiere dos argumentos de tipo `Person` , los cuales pueden ser `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="a23a6-127">For example, the following `Person` class constructor requires two arguments of type `Person`, both of which can be `Nothing`.</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)]

<span data-ttu-id="a23a6-128">El uso de argumentos con nombre y posicionales mixtos ayuda a hacer que el código sea claro cuando el valor de los `father` `mother` argumentos y es `Nothing` :</span><span class="sxs-lookup"><span data-stu-id="a23a6-128">Using mixed named and positional arguments helps to make the intent of the code clear when the value of the `father` and `mother` arguments is `Nothing`:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)]

<span data-ttu-id="a23a6-129">Para seguir los argumentos posicionales con argumentos con nombre, debe agregar el siguiente elemento al archivo de proyecto de Visual Basic ( \* . vbproj):</span><span class="sxs-lookup"><span data-stu-id="a23a6-129">To follow positional arguments with named arguments, you must add the following element to your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="a23a6-130">Para obtener más información, vea [establecer la versión de lenguaje Visual Basic](../../../language-reference/configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="a23a6-130">For more information see [setting the Visual Basic language version](../../../language-reference/configure-language-version.md).</span></span>

## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="a23a6-131">Restricciones en el suministro de argumentos por nombre</span><span class="sxs-lookup"><span data-stu-id="a23a6-131">Restrictions on Supplying Arguments by Name</span></span>

<span data-ttu-id="a23a6-132">No se pueden pasar argumentos por nombre para evitar escribir argumentos necesarios.</span><span class="sxs-lookup"><span data-stu-id="a23a6-132">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="a23a6-133">Solo se pueden omitir los argumentos opcionales.</span><span class="sxs-lookup"><span data-stu-id="a23a6-133">You can omit only the optional arguments.</span></span>

<span data-ttu-id="a23a6-134">No se puede pasar una matriz de parámetros por nombre.</span><span class="sxs-lookup"><span data-stu-id="a23a6-134">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="a23a6-135">Esto se debe a que cuando se llama al procedimiento, se proporciona un número indefinido de argumentos separados por comas para la matriz de parámetros y el compilador no puede asociar más de un argumento con un nombre único.</span><span class="sxs-lookup"><span data-stu-id="a23a6-135">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>

## <a name="see-also"></a><span data-ttu-id="a23a6-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a23a6-136">See also</span></span>

- [<span data-ttu-id="a23a6-137">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="a23a6-137">Procedures</span></span>](./index.md)
- [<span data-ttu-id="a23a6-138">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="a23a6-138">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="a23a6-139">Procedimiento para pasar argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="a23a6-139">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="a23a6-140">Pasar argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="a23a6-140">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="a23a6-141">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="a23a6-141">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="a23a6-142">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="a23a6-142">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="a23a6-143">Opcional</span><span class="sxs-lookup"><span data-stu-id="a23a6-143">Optional</span></span>](../../../language-reference/modifiers/optional.md)
- [<span data-ttu-id="a23a6-144">ParamArray</span><span class="sxs-lookup"><span data-stu-id="a23a6-144">ParamArray</span></span>](../../../language-reference/modifiers/paramarray.md)
