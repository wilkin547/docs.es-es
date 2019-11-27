---
title: ParamArray
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: fbc87bffebc265e6062512e96fc29a64334b3c65
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351369"
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="524cc-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="524cc-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="524cc-103">Especifica que un parámetro de procedimiento toma una matriz opcional de elementos del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="524cc-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="524cc-104">`ParamArray` solo se puede usar en el último parámetro de una lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="524cc-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="524cc-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="524cc-105">Remarks</span></span>  
 <span data-ttu-id="524cc-106">`ParamArray` permite pasar un número arbitrario de argumentos al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="524cc-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="524cc-107">Un parámetro `ParamArray` siempre se declara mediante [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="524cc-107">A `ParamArray` parameter is always declared using [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
 <span data-ttu-id="524cc-108">Puede proporcionar uno o varios argumentos a un parámetro `ParamArray` pasando una matriz del tipo de datos adecuado, una lista separada por comas de valores o nada en absoluto.</span><span class="sxs-lookup"><span data-stu-id="524cc-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="524cc-109">Para obtener más información, vea "llamar a ParamArray" en [matrices de parámetros](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="524cc-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="524cc-110">Siempre que se trata de una matriz que puede ser indefinidamente grande, existe el riesgo de que se produzca una gran cantidad de capacidad interna de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="524cc-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="524cc-111">Si acepta una matriz de parámetros del código de llamada, debe probar su longitud y tomar las medidas adecuadas si es demasiado grande para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="524cc-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="524cc-112">El modificador `ParamArray` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="524cc-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="524cc-113">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="524cc-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="524cc-114">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="524cc-114">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="524cc-115">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="524cc-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="524cc-116">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="524cc-116">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="524cc-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="524cc-117">See also</span></span>

- [<span data-ttu-id="524cc-118">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="524cc-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="524cc-119">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="524cc-119">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
