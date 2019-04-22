---
title: ParamArray (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: b9dee0fc876c6e7a02d085db7db4bf1c5dd2c68d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816671"
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="989cb-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="989cb-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="989cb-103">Especifica que un parámetro de procedimiento toma una matriz opcional de elementos del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="989cb-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="989cb-104">`ParamArray` puede usarse solo en el último parámetro de una lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="989cb-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="989cb-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="989cb-105">Remarks</span></span>  
 <span data-ttu-id="989cb-106">`ParamArray` permite pasar un número arbitrario de argumentos al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="989cb-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="989cb-107">Un `ParamArray` parámetro siempre se declara mediante [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="989cb-107">A `ParamArray` parameter is always declared using [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
 <span data-ttu-id="989cb-108">Puede proporcionar uno o más argumentos a un `ParamArray` tipo de parámetro pasando una matriz de los datos adecuados, una lista separada por comas de valores, o nada en absoluto.</span><span class="sxs-lookup"><span data-stu-id="989cb-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="989cb-109">Para obtener más información, vea "Llamar a un lista de parámetros" en [las matrices de parámetros](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="989cb-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="989cb-110">Si se trabaja con una matriz que puede ser excesivamente grande, hay un riesgo de sobrecargar alguna capacidad interna de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="989cb-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="989cb-111">Si acepta una matriz de parámetros desde el código de llamada, debe comprobar su longitud y seguir los pasos adecuados si es demasiado grande para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="989cb-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="989cb-112">El modificador `ParamArray` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="989cb-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="989cb-113">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="989cb-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="989cb-114">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="989cb-114">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="989cb-115">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="989cb-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="989cb-116">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="989cb-116">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="989cb-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="989cb-117">See also</span></span>

- [<span data-ttu-id="989cb-118">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="989cb-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="989cb-119">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="989cb-119">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
