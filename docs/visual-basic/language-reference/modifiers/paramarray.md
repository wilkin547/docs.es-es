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
ms.openlocfilehash: e3c24818ea87884a0dd9b42c604e13e16ca6d3d7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84391825"
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="5d58c-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d58c-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="5d58c-103">Especifica que un parámetro de procedimiento toma una matriz opcional de elementos del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="5d58c-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="5d58c-104">`ParamArray`solo se puede usar en el último parámetro de una lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="5d58c-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d58c-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5d58c-105">Remarks</span></span>  
 <span data-ttu-id="5d58c-106">`ParamArray`permite pasar un número arbitrario de argumentos al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5d58c-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="5d58c-107">Un `ParamArray` parámetro siempre se declara mediante [ByVal](byval.md).</span><span class="sxs-lookup"><span data-stu-id="5d58c-107">A `ParamArray` parameter is always declared using [ByVal](byval.md).</span></span>  
  
 <span data-ttu-id="5d58c-108">Puede proporcionar uno o varios argumentos a un `ParamArray` parámetro pasando una matriz del tipo de datos adecuado, una lista separada por comas de valores o nada en absoluto.</span><span class="sxs-lookup"><span data-stu-id="5d58c-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="5d58c-109">Para obtener más información, vea "llamar a ParamArray" en [matrices de parámetros](../../programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="5d58c-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5d58c-110">Siempre que se trata de una matriz que puede ser indefinidamente grande, existe el riesgo de que se produzca una gran cantidad de capacidad interna de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5d58c-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="5d58c-111">Si acepta una matriz de parámetros del código de llamada, debe probar su longitud y tomar las medidas adecuadas si es demasiado grande para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5d58c-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="5d58c-112">El modificador `ParamArray` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5d58c-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="5d58c-113">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="5d58c-113">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="5d58c-114">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="5d58c-114">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="5d58c-115">Property Statement</span><span class="sxs-lookup"><span data-stu-id="5d58c-115">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="5d58c-116">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="5d58c-116">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="5d58c-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5d58c-117">See also</span></span>

- [<span data-ttu-id="5d58c-118">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d58c-118">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="5d58c-119">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="5d58c-119">Parameter Arrays</span></span>](../../programming-guide/language-features/procedures/parameter-arrays.md)
