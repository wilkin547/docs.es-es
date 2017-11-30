---
title: "Pasar argumentos por posición o por nombre (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 164f69fcf23049441a0acbe05058c792d5363a03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="78327-102">Pasar argumentos por posición o por nombre (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78327-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>
<span data-ttu-id="78327-103">Cuando se llama a un `Sub` o `Function` procedimiento, puede pasar argumentos *por posición* : en el orden en que aparecen en la definición del procedimiento, o se les pueden pasar *por su nombre*, sin tener en cuenta para colocar.</span><span class="sxs-lookup"><span data-stu-id="78327-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>  
  
 <span data-ttu-id="78327-104">Cuando se pasa un argumento por nombre, especifique el declarado del argumento nombre seguido de dos puntos y un signo igual (`:=`), seguido por el valor del argumento.</span><span class="sxs-lookup"><span data-stu-id="78327-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="78327-105">Puede proporcionar argumentos con nombre en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="78327-105">You can supply named arguments in any order.</span></span>  
  
 <span data-ttu-id="78327-106">Por ejemplo, la siguiente `Sub` procedimiento toma tres argumentos:</span><span class="sxs-lookup"><span data-stu-id="78327-106">For example, the following `Sub` procedure takes three arguments:</span></span>  
  
 [!code-vb[VbVbcnProcedures#41](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_1.vb)]  
  
 <span data-ttu-id="78327-107">Cuando se llama a este procedimiento, puede proporcionar los argumentos por posición, por nombre o mediante una combinación de ambos.</span><span class="sxs-lookup"><span data-stu-id="78327-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>  
  
## <a name="passing-arguments-by-position"></a><span data-ttu-id="78327-108">Pasar argumentos por posición</span><span class="sxs-lookup"><span data-stu-id="78327-108">Passing Arguments by Position</span></span>  
 <span data-ttu-id="78327-109">Puede llamar al procedimiento `studentInfo` con los argumentos pasados por posición y delimitados por comas, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="78327-109">You can call the procedure `studentInfo` with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#42](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_2.vb)]  
  
 <span data-ttu-id="78327-110">Si se omite un argumento opcional de una lista de argumentos posicionales, debe mantener su posición mediante una coma.</span><span class="sxs-lookup"><span data-stu-id="78327-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="78327-111">El ejemplo siguiente se llama `studentInfo` sin el `age` argumento:</span><span class="sxs-lookup"><span data-stu-id="78327-111">The following example calls `studentInfo` without the `age` argument:</span></span>  
  
 [!code-vb[VbVbcnProcedures#43](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_3.vb)]  
  
## <a name="passing-arguments-by-name"></a><span data-ttu-id="78327-112">Pasar argumentos por nombre</span><span class="sxs-lookup"><span data-stu-id="78327-112">Passing Arguments by Name</span></span>  
 <span data-ttu-id="78327-113">Como alternativa, puede llamar a `studentInfo` con los argumentos pasados por nombre, también delimitados por comas, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="78327-113">Alternatively, you can call `studentInfo` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#44](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_4.vb)]  
  
## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="78327-114">Pasar argumentos por posición o por nombre</span><span class="sxs-lookup"><span data-stu-id="78327-114">Mixing Arguments by Position and by Name</span></span>  
 <span data-ttu-id="78327-115">Puede proporcionar argumentos por posición o por su nombre en una llamada de procedimiento único, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="78327-115">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#45](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_5.vb)]  
  
 <span data-ttu-id="78327-116">En el ejemplo anterior, no hay ninguna coma adicional es necesaria para mantener la posición de la omitido `age` argumento, ya que `birth` se pasó por nombre.</span><span class="sxs-lookup"><span data-stu-id="78327-116">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>  
  
 <span data-ttu-id="78327-117">Al proporcionar argumentos, una mezcla de posición y el nombre, los argumentos posicionales deben preceder al resto.</span><span class="sxs-lookup"><span data-stu-id="78327-117">When you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="78327-118">Una vez que se proporciona un argumento por nombre, los argumentos restantes deben ser por su nombre.</span><span class="sxs-lookup"><span data-stu-id="78327-118">Once you supply an argument by name, the remaining arguments must all be by name.</span></span>  
  
## <a name="supplying-optional-arguments-by-name"></a><span data-ttu-id="78327-119">Proporcionar argumentos opcionales por nombre</span><span class="sxs-lookup"><span data-stu-id="78327-119">Supplying Optional Arguments by Name</span></span>  
 <span data-ttu-id="78327-120">Pasar argumentos por nombre es especialmente útil cuando se llama a un procedimiento que tiene más de un argumento opcional.</span><span class="sxs-lookup"><span data-stu-id="78327-120">Passing arguments by name is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="78327-121">Si proporciona argumentos por nombre, no es necesario utilizar comas consecutivas para denotar falta argumentos posicionales.</span><span class="sxs-lookup"><span data-stu-id="78327-121">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="78327-122">Pasar argumentos por nombre también resulta más fácil realizar un seguimiento de los argumentos que se pasan y cuáles se omiten.</span><span class="sxs-lookup"><span data-stu-id="78327-122">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>  
  
## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="78327-123">Restricciones sobre cómo proporcionar argumentos por nombre</span><span class="sxs-lookup"><span data-stu-id="78327-123">Restrictions on Supplying Arguments by Name</span></span>  
 <span data-ttu-id="78327-124">No se puede pasar argumentos por nombre para evitar especificar argumentos requeridos.</span><span class="sxs-lookup"><span data-stu-id="78327-124">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="78327-125">Puede omitir solo los argumentos opcionales.</span><span class="sxs-lookup"><span data-stu-id="78327-125">You can omit only the optional arguments.</span></span>  
  
 <span data-ttu-id="78327-126">No se puede pasar una matriz de parámetros por nombre.</span><span class="sxs-lookup"><span data-stu-id="78327-126">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="78327-127">Esto es porque cuando se llama al procedimiento, se proporciona un número indefinido de argumentos separados por comas para la matriz de parámetros, y el compilador no puede asociar más de un argumento con un nombre único.</span><span class="sxs-lookup"><span data-stu-id="78327-127">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78327-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="78327-128">See Also</span></span>  
 [<span data-ttu-id="78327-129">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="78327-129">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="78327-130">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="78327-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="78327-131">Pasar argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="78327-131">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="78327-132">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="78327-132">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="78327-133">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="78327-133">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="78327-134">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="78327-134">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="78327-135">Opcional</span><span class="sxs-lookup"><span data-stu-id="78327-135">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [<span data-ttu-id="78327-136">ParamArray</span><span class="sxs-lookup"><span data-stu-id="78327-136">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
