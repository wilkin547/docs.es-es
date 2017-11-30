---
title: "Parámetros opcionales (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- parameters [Visual Basic], optional
- Visual Basic code, procedures
- procedures [Visual Basic], optional arguments
- optional arguments
- named arguments [Visual Basic], and optional arguments
- optional parameters
- Optional keyword [Visual Basic], optional arguments
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], and named arguments
ms.assetid: 398d2845-1069-4e94-b934-a73b545c8b87
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e57023f594cfe4cd79d59cc8541fcf18018de0ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="optional-parameters-visual-basic"></a><span data-ttu-id="6dd73-102">Parámetros opcionales (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6dd73-102">Optional Parameters (Visual Basic)</span></span>
<span data-ttu-id="6dd73-103">Un parámetro de un procedimiento puede ser opcional si así se especifica y no es necesario proporcionarle argumentos al llamar al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6dd73-103">You can specify that a procedure parameter is optional and no argument has to be supplied for it when the procedure is called.</span></span> <span data-ttu-id="6dd73-104">*Parámetros opcionales* se indican mediante el `Optional` palabra clave en la definición del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6dd73-104">*Optional parameters* are indicated by the `Optional` keyword in the procedure definition.</span></span> <span data-ttu-id="6dd73-105">Se aplican las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="6dd73-105">The following rules apply:</span></span>  
  
-   <span data-ttu-id="6dd73-106">Todos los parámetros opcionales de la definición del procedimiento deben especificar un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6dd73-106">Every optional parameter in the procedure definition must specify a default value.</span></span>  
  
-   <span data-ttu-id="6dd73-107">El valor predeterminado de un parámetro opcional debe ser una expresión constante.</span><span class="sxs-lookup"><span data-stu-id="6dd73-107">The default value for an optional parameter must be a constant expression.</span></span>  
  
-   <span data-ttu-id="6dd73-108">Todos los parámetros que vayan a continuación de un parámetro opcional en la definición del procedimiento también deben ser opcionales.</span><span class="sxs-lookup"><span data-stu-id="6dd73-108">Every parameter following an optional parameter in the procedure definition must also be optional.</span></span>  
  
 <span data-ttu-id="6dd73-109">La siguiente sintaxis muestra una declaración de procedimiento con un parámetro opcional:</span><span class="sxs-lookup"><span data-stu-id="6dd73-109">The following syntax shows a procedure declaration with an optional parameter:</span></span>  
  
```vb  
Sub name(ByVal parameter1 As datatype1, Optional ByVal parameter2 As datatype2 = defaultvalue)  
```  
  
## <a name="calling-procedures-with-optional-parameters"></a><span data-ttu-id="6dd73-110">Llamar a procedimientos con parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="6dd73-110">Calling Procedures with Optional Parameters</span></span>  
 <span data-ttu-id="6dd73-111">Cuando se llama a un procedimiento con un parámetro opcional, se puede elegir si se proporciona o no el argumento.</span><span class="sxs-lookup"><span data-stu-id="6dd73-111">When you call a procedure with an optional parameter, you can choose whether to supply the argument.</span></span> <span data-ttu-id="6dd73-112">Si no se proporciona, el procedimiento utiliza el valor predeterminado declarado para dicho parámetro.</span><span class="sxs-lookup"><span data-stu-id="6dd73-112">If you do not, the procedure uses the default value declared for that parameter.</span></span>  
  
 <span data-ttu-id="6dd73-113">Si se omiten uno o más argumentos opcionales de la lista de argumentos, hay que utilizar comas sucesivas para delimitar sus posiciones.</span><span class="sxs-lookup"><span data-stu-id="6dd73-113">When you omit one or more optional arguments in the argument list, you use successive commas to mark their positions.</span></span> <span data-ttu-id="6dd73-114">En el ejemplo de llamada siguiente se suministran los argumentos primero y cuarto, pero no el segundo ni el tercero:</span><span class="sxs-lookup"><span data-stu-id="6dd73-114">The following example call supplies the first and fourth arguments but not the second or third:</span></span>  
  
```vb  
Sub name(argument 1, , , argument 4)  
```  
  
 <span data-ttu-id="6dd73-115">En el ejemplo siguiente se realizan algunas llamadas a la función `MsgBox`.</span><span class="sxs-lookup"><span data-stu-id="6dd73-115">The following example makes several calls to the `MsgBox` function.</span></span> <span data-ttu-id="6dd73-116">`MsgBox` tiene un parámetro obligatorio y dos parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="6dd73-116">`MsgBox` has one required parameter and two optional parameters.</span></span>  
  
 <span data-ttu-id="6dd73-117">La primera llamada a `MsgBox` proporciona los tres argumentos en el orden en que `MsgBox` los define.</span><span class="sxs-lookup"><span data-stu-id="6dd73-117">The first call to `MsgBox` supplies all three arguments in the order that `MsgBox` defines them.</span></span> <span data-ttu-id="6dd73-118">La segunda llamada únicamente proporciona el argumento obligatorio.</span><span class="sxs-lookup"><span data-stu-id="6dd73-118">The second call supplies only the required argument.</span></span> <span data-ttu-id="6dd73-119">La tercera y la cuarta llamada proporcionan el primer y el tercer argumento.</span><span class="sxs-lookup"><span data-stu-id="6dd73-119">The third and fourth calls supply the first and third arguments.</span></span> <span data-ttu-id="6dd73-120">La tercera llamada lo hace por posición y la llamada cuarta, por nombre.</span><span class="sxs-lookup"><span data-stu-id="6dd73-120">The third call does this by position, and the fourth call does it by name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#47](./codesnippet/VisualBasic/optional-parameters_1.vb)]  
  
## <a name="determining-whether-an-optional-argument-is-present"></a><span data-ttu-id="6dd73-121">Determinar si un argumento opcional está presente</span><span class="sxs-lookup"><span data-stu-id="6dd73-121">Determining Whether an Optional Argument Is Present</span></span>  
 <span data-ttu-id="6dd73-122">En tiempo de ejecución un procedimiento no puede detectar si un argumento determinado se ha omitido o si el código de llamada ha suministrado de forma explícita el valor predeterminado de dicho argumento.</span><span class="sxs-lookup"><span data-stu-id="6dd73-122">A procedure cannot detect at run time whether a given argument has been omitted or the calling code has explicitly supplied the default value.</span></span> <span data-ttu-id="6dd73-123">Si fuese necesario hacer esta distinción, se podría establecer como valor predeterminado un valor improbable.</span><span class="sxs-lookup"><span data-stu-id="6dd73-123">If you need to make this distinction, you can set an unlikely value as the default.</span></span> <span data-ttu-id="6dd73-124">El siguiente procedimiento define el parámetro opcional `office`y comprueba si su valor predeterminado, `QJZ`, para ver si se ha omitido en la llamada:</span><span class="sxs-lookup"><span data-stu-id="6dd73-124">The following procedure defines the optional parameter `office`, and tests for its default value, `QJZ`, to see if it has been omitted in the call:</span></span>  
  
 [!code-vb[VbVbcnProcedures#46](./codesnippet/VisualBasic/optional-parameters_2.vb)]  
  
 <span data-ttu-id="6dd73-125">Si el parámetro opcional es un tipo de referencia, como `String`, puede utilizar `Nothing` como valor predeterminado, siempre y cuando éste no sea un valor esperado para el argumento.</span><span class="sxs-lookup"><span data-stu-id="6dd73-125">If the optional parameter is a reference type such as a `String`, you can use `Nothing` as the default value, provided this is not an expected value for the argument.</span></span>  
  
## <a name="optional-parameters-and-overloading"></a><span data-ttu-id="6dd73-126">Parámetros opcionales y sobrecarga</span><span class="sxs-lookup"><span data-stu-id="6dd73-126">Optional Parameters and Overloading</span></span>  
 <span data-ttu-id="6dd73-127">Otra forma de definir un procedimiento con parámetros opcionales consiste en utilizar una sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="6dd73-127">Another way to define a procedure with optional parameters is to use overloading.</span></span> <span data-ttu-id="6dd73-128">Si tiene un parámetro opcional, puede definir dos versiones sobrecargadas del procedimiento, una que acepte el parámetro y otra sin él.</span><span class="sxs-lookup"><span data-stu-id="6dd73-128">If you have one optional parameter, you can define two overloaded versions of the procedure, one accepting the parameter and one without it.</span></span> <span data-ttu-id="6dd73-129">Este planteamiento se complica a medida que aumenta el número de parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="6dd73-129">This approach becomes more complicated as the number of optional parameters increases.</span></span> <span data-ttu-id="6dd73-130">No obstante, tiene la ventaja de que permite saber con total certeza si el programa de llamada ha suministrado o no cada argumento opcional.</span><span class="sxs-lookup"><span data-stu-id="6dd73-130">However, its advantage is that you can be absolutely sure whether the calling program supplied each optional argument.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dd73-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="6dd73-131">See Also</span></span>  
 [<span data-ttu-id="6dd73-132">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="6dd73-132">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="6dd73-133">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="6dd73-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="6dd73-134">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="6dd73-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="6dd73-135">Paso de argumentos por posición o por nombre</span><span class="sxs-lookup"><span data-stu-id="6dd73-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="6dd73-136">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="6dd73-136">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="6dd73-137">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="6dd73-137">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="6dd73-138">Opcional</span><span class="sxs-lookup"><span data-stu-id="6dd73-138">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [<span data-ttu-id="6dd73-139">ParamArray</span><span class="sxs-lookup"><span data-stu-id="6dd73-139">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
