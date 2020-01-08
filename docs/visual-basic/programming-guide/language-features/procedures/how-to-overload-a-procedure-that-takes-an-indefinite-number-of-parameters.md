---
title: 'Cómo: Sobrecargar un procedimiento que toma un número indefinido de parámetros'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], indefinite number of parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
ms.openlocfilehash: 94f12b4cc6cb35864fefbb3b5bb1378bec5e974c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347561"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="7d35c-102">Cómo: Sobrecargar un procedimiento que toma un número indefinido de parámetros (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d35c-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="7d35c-103">Si un procedimiento tiene un parámetro [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) , no se puede definir una versión sobrecargada que tome una matriz unidimensional para la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="7d35c-103">If a procedure has a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="7d35c-104">Para obtener más información, vea "sobrecargas implícitas para un parámetro paramarray" en [consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7d35c-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="7d35c-105">Para sobrecargar un procedimiento que toma un número variable de parámetros</span><span class="sxs-lookup"><span data-stu-id="7d35c-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1. <span data-ttu-id="7d35c-106">Asegúrese de que el procedimiento y la lógica de llamada del código se benefician de las versiones sobrecargadas más que de un parámetro `ParamArray`.</span><span class="sxs-lookup"><span data-stu-id="7d35c-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="7d35c-107">Vea "Overloads and ParamArray" en [consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7d35c-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2. <span data-ttu-id="7d35c-108">Determine qué números de valores proporcionados debe aceptar el procedimiento en la parte variable de la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="7d35c-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="7d35c-109">Esto podría incluir el caso de ningún valor y podría incluir el caso de una sola matriz unidimensional.</span><span class="sxs-lookup"><span data-stu-id="7d35c-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3. <span data-ttu-id="7d35c-110">Para cada número aceptable de valores proporcionados, escriba una instrucción de declaración `Sub` o `Function` que defina la lista de parámetros correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7d35c-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="7d35c-111">No use el `Optional` ni la palabra clave `ParamArray` en esta versión sobrecargada.</span><span class="sxs-lookup"><span data-stu-id="7d35c-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4. <span data-ttu-id="7d35c-112">En cada declaración, preceda a la palabra clave `Sub` o `Function` con la palabra clave [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) .</span><span class="sxs-lookup"><span data-stu-id="7d35c-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5. <span data-ttu-id="7d35c-113">Después de cada declaración, escriba el código de procedimiento que debe ejecutarse cuando el código de llamada suministre valores correspondientes a la lista de parámetros de la declaración.</span><span class="sxs-lookup"><span data-stu-id="7d35c-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6. <span data-ttu-id="7d35c-114">Finalice cada procedimiento con la instrucción `End Sub` o `End Function` según corresponda.</span><span class="sxs-lookup"><span data-stu-id="7d35c-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d35c-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d35c-115">Example</span></span>  
 <span data-ttu-id="7d35c-116">En el ejemplo siguiente se muestra un procedimiento definido con un parámetro [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) y, a continuación, un conjunto equivalente de procedimientos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="7d35c-116">The following example shows a procedure defined with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 [!code-vb[VbVbcnProcedures#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#69)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="7d35c-117">No se puede sobrecargar este procedimiento con una lista de parámetros que tome una matriz unidimensional para la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="7d35c-117">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="7d35c-118">Sin embargo, puede utilizar las firmas de las otras sobrecargas implícitas.</span><span class="sxs-lookup"><span data-stu-id="7d35c-118">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="7d35c-119">Las declaraciones siguientes muestran esto.</span><span class="sxs-lookup"><span data-stu-id="7d35c-119">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
 <span data-ttu-id="7d35c-120">El código de las versiones sobrecargadas no tiene que comprobar si el código de llamada proporcionó uno o varios valores para el parámetro `ParamArray`, o si es así, el número de.</span><span class="sxs-lookup"><span data-stu-id="7d35c-120">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> <span data-ttu-id="7d35c-121">Visual Basic pasa el control a la versión que coincide con la lista de argumentos de llamada.</span><span class="sxs-lookup"><span data-stu-id="7d35c-121">Visual Basic passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="7d35c-122">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="7d35c-122">Compile the code</span></span>  
 <span data-ttu-id="7d35c-123">Dado que un procedimiento con un parámetro `ParamArray` es equivalente a un conjunto de versiones sobrecargadas, no puede sobrecargar este procedimiento con una lista de parámetros que se corresponda con cualquiera de estas sobrecargas implícitas.</span><span class="sxs-lookup"><span data-stu-id="7d35c-123">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="7d35c-124">Para obtener más información, vea [consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7d35c-124">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="7d35c-125">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7d35c-125">.NET Framework Security</span></span>  
 <span data-ttu-id="7d35c-126">Siempre que se trata de una matriz que puede ser indefinidamente grande, existe el riesgo de que se produzca una gran cantidad de capacidad interna de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d35c-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="7d35c-127">Si acepta una matriz de parámetros, debe comprobar la longitud de la matriz que se le ha pasado al código de llamada y tomar los pasos adecuados si es demasiado grande para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d35c-127">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d35c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d35c-128">See also</span></span>

- [<span data-ttu-id="7d35c-129">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="7d35c-129">Procedures</span></span>](./index.md)
- [<span data-ttu-id="7d35c-130">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="7d35c-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="7d35c-131">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="7d35c-131">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="7d35c-132">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="7d35c-132">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="7d35c-133">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="7d35c-133">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="7d35c-134">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="7d35c-134">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="7d35c-135">Definir varias versiones de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="7d35c-135">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="7d35c-136">Llamar a un procedimiento sobrecargado</span><span class="sxs-lookup"><span data-stu-id="7d35c-136">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="7d35c-137">Sobrecargar un procedimiento que toma parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="7d35c-137">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="7d35c-138">Resolución de sobrecargas</span><span class="sxs-lookup"><span data-stu-id="7d35c-138">Overload Resolution</span></span>](./overload-resolution.md)
