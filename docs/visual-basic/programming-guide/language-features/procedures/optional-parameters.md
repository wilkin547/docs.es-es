---
description: 'Más información acerca de: parámetros opcionales (Visual Basic)'
title: Parámetros opcionales
ms.date: 07/20/2015
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
ms.openlocfilehash: 048f940f25fc05a66245e267ff23dc9845fcafdd
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100436141"
---
# <a name="optional-parameters-visual-basic"></a><span data-ttu-id="570d4-103">Parámetros opcionales (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="570d4-103">Optional Parameters (Visual Basic)</span></span>

<span data-ttu-id="570d4-104">Un parámetro de un procedimiento puede ser opcional si así se especifica y no es necesario proporcionarle argumentos al llamar al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="570d4-104">You can specify that a procedure parameter is optional and no argument has to be supplied for it when the procedure is called.</span></span> <span data-ttu-id="570d4-105">Los *parámetros opcionales* se indican mediante la `Optional` palabra clave en la definición del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="570d4-105">*Optional parameters* are indicated by the `Optional` keyword in the procedure definition.</span></span> <span data-ttu-id="570d4-106">Se aplican las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="570d4-106">The following rules apply:</span></span>  
  
- <span data-ttu-id="570d4-107">Todos los parámetros opcionales de la definición del procedimiento deben especificar un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="570d4-107">Every optional parameter in the procedure definition must specify a default value.</span></span>  
  
- <span data-ttu-id="570d4-108">El valor predeterminado de un parámetro opcional debe ser una expresión constante.</span><span class="sxs-lookup"><span data-stu-id="570d4-108">The default value for an optional parameter must be a constant expression.</span></span>  
  
- <span data-ttu-id="570d4-109">Todos los parámetros que vayan a continuación de un parámetro opcional en la definición del procedimiento también deben ser opcionales.</span><span class="sxs-lookup"><span data-stu-id="570d4-109">Every parameter following an optional parameter in the procedure definition must also be optional.</span></span>  
  
 <span data-ttu-id="570d4-110">La siguiente sintaxis muestra una declaración de procedimiento con un parámetro opcional:</span><span class="sxs-lookup"><span data-stu-id="570d4-110">The following syntax shows a procedure declaration with an optional parameter:</span></span>  
  
```vb  
Sub name(ByVal parameter1 As datatype1, Optional ByVal parameter2 As datatype2 = defaultvalue)  
```  
  
## <a name="calling-procedures-with-optional-parameters"></a><span data-ttu-id="570d4-111">Llamar a procedimientos con parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="570d4-111">Calling Procedures with Optional Parameters</span></span>  

 <span data-ttu-id="570d4-112">Cuando se llama a un procedimiento con un parámetro opcional, se puede elegir si se proporciona o no el argumento.</span><span class="sxs-lookup"><span data-stu-id="570d4-112">When you call a procedure with an optional parameter, you can choose whether to supply the argument.</span></span> <span data-ttu-id="570d4-113">Si no se proporciona, el procedimiento utiliza el valor predeterminado declarado para dicho parámetro.</span><span class="sxs-lookup"><span data-stu-id="570d4-113">If you do not, the procedure uses the default value declared for that parameter.</span></span>  
  
 <span data-ttu-id="570d4-114">Si se omiten uno o más argumentos opcionales de la lista de argumentos, hay que utilizar comas sucesivas para delimitar sus posiciones.</span><span class="sxs-lookup"><span data-stu-id="570d4-114">When you omit one or more optional arguments in the argument list, you use successive commas to mark their positions.</span></span> <span data-ttu-id="570d4-115">En el ejemplo de llamada siguiente se suministran los argumentos primero y cuarto, pero no el segundo ni el tercero:</span><span class="sxs-lookup"><span data-stu-id="570d4-115">The following example call supplies the first and fourth arguments but not the second or third:</span></span>  
  
```vb  
Sub name(argument 1, , , argument 4)  
```  
  
 <span data-ttu-id="570d4-116">En el ejemplo siguiente se realizan algunas llamadas a la función `MsgBox`.</span><span class="sxs-lookup"><span data-stu-id="570d4-116">The following example makes several calls to the `MsgBox` function.</span></span> <span data-ttu-id="570d4-117">`MsgBox` tiene un parámetro obligatorio y dos parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="570d4-117">`MsgBox` has one required parameter and two optional parameters.</span></span>  
  
 <span data-ttu-id="570d4-118">La primera llamada a `MsgBox` proporciona los tres argumentos en el orden en que `MsgBox` los define.</span><span class="sxs-lookup"><span data-stu-id="570d4-118">The first call to `MsgBox` supplies all three arguments in the order that `MsgBox` defines them.</span></span> <span data-ttu-id="570d4-119">La segunda llamada únicamente proporciona el argumento obligatorio.</span><span class="sxs-lookup"><span data-stu-id="570d4-119">The second call supplies only the required argument.</span></span> <span data-ttu-id="570d4-120">La tercera y la cuarta llamada proporcionan el primer y el tercer argumento.</span><span class="sxs-lookup"><span data-stu-id="570d4-120">The third and fourth calls supply the first and third arguments.</span></span> <span data-ttu-id="570d4-121">La tercera llamada lo hace por posición y la llamada cuarta, por nombre.</span><span class="sxs-lookup"><span data-stu-id="570d4-121">The third call does this by position, and the fourth call does it by name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#47)]  
  
## <a name="determining-whether-an-optional-argument-is-present"></a><span data-ttu-id="570d4-122">Determinar si un argumento opcional está presente</span><span class="sxs-lookup"><span data-stu-id="570d4-122">Determining Whether an Optional Argument Is Present</span></span>  

 <span data-ttu-id="570d4-123">En tiempo de ejecución un procedimiento no puede detectar si un argumento determinado se ha omitido o si el código de llamada ha suministrado de forma explícita el valor predeterminado de dicho argumento.</span><span class="sxs-lookup"><span data-stu-id="570d4-123">A procedure cannot detect at run time whether a given argument has been omitted or the calling code has explicitly supplied the default value.</span></span> <span data-ttu-id="570d4-124">Si fuese necesario hacer esta distinción, se podría establecer como valor predeterminado un valor improbable.</span><span class="sxs-lookup"><span data-stu-id="570d4-124">If you need to make this distinction, you can set an unlikely value as the default.</span></span> <span data-ttu-id="570d4-125">En el procedimiento siguiente se define el parámetro opcional `office` y se prueba su valor predeterminado, `QJZ` , para ver si se ha omitido en la llamada:</span><span class="sxs-lookup"><span data-stu-id="570d4-125">The following procedure defines the optional parameter `office`, and tests for its default value, `QJZ`, to see if it has been omitted in the call:</span></span>  
  
 [!code-vb[VbVbcnProcedures#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#46)]  
  
 <span data-ttu-id="570d4-126">Si el parámetro opcional es un tipo de referencia, como `String`, puede utilizar `Nothing` como valor predeterminado, siempre y cuando éste no sea un valor esperado para el argumento.</span><span class="sxs-lookup"><span data-stu-id="570d4-126">If the optional parameter is a reference type such as a `String`, you can use `Nothing` as the default value, provided this is not an expected value for the argument.</span></span>  
  
## <a name="optional-parameters-and-overloading"></a><span data-ttu-id="570d4-127">Parámetros opcionales y sobrecarga</span><span class="sxs-lookup"><span data-stu-id="570d4-127">Optional Parameters and Overloading</span></span>  

 <span data-ttu-id="570d4-128">Otra forma de definir un procedimiento con parámetros opcionales consiste en utilizar una sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="570d4-128">Another way to define a procedure with optional parameters is to use overloading.</span></span> <span data-ttu-id="570d4-129">Si tiene un parámetro opcional, puede definir dos versiones sobrecargadas del procedimiento, una que acepte el parámetro y otra sin él.</span><span class="sxs-lookup"><span data-stu-id="570d4-129">If you have one optional parameter, you can define two overloaded versions of the procedure, one accepting the parameter and one without it.</span></span> <span data-ttu-id="570d4-130">Este planteamiento se complica a medida que aumenta el número de parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="570d4-130">This approach becomes more complicated as the number of optional parameters increases.</span></span> <span data-ttu-id="570d4-131">No obstante, tiene la ventaja de que permite saber con total certeza si el programa de llamada ha suministrado o no cada argumento opcional.</span><span class="sxs-lookup"><span data-stu-id="570d4-131">However, its advantage is that you can be absolutely sure whether the calling program supplied each optional argument.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="570d4-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="570d4-132">See also</span></span>

- [<span data-ttu-id="570d4-133">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="570d4-133">Procedures</span></span>](./index.md)
- [<span data-ttu-id="570d4-134">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="570d4-134">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="570d4-135">Pasar argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="570d4-135">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="570d4-136">Paso de argumentos por posición o por nombre</span><span class="sxs-lookup"><span data-stu-id="570d4-136">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="570d4-137">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="570d4-137">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="570d4-138">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="570d4-138">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="570d4-139">Opcional</span><span class="sxs-lookup"><span data-stu-id="570d4-139">Optional</span></span>](../../../language-reference/modifiers/optional.md)
- [<span data-ttu-id="570d4-140">ParamArray</span><span class="sxs-lookup"><span data-stu-id="570d4-140">ParamArray</span></span>](../../../language-reference/modifiers/paramarray.md)
