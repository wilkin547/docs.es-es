---
description: 'Más información acerca de: ParamArray (Visual Basic)'
title: ParamArray
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: 064bad8a558308ee3361c11d07020e0e3bf40c13
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730400"
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="db812-103">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db812-103">ParamArray (Visual Basic)</span></span>

<span data-ttu-id="db812-104">Especifica que un parámetro de procedimiento toma una matriz opcional de elementos del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="db812-104">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="db812-105">`ParamArray` solo se puede usar en el último parámetro de una lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="db812-105">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db812-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="db812-106">Remarks</span></span>  

 <span data-ttu-id="db812-107">`ParamArray` permite pasar un número arbitrario de argumentos al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="db812-107">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="db812-108">Un `ParamArray` parámetro siempre se declara mediante [ByVal](byval.md).</span><span class="sxs-lookup"><span data-stu-id="db812-108">A `ParamArray` parameter is always declared using [ByVal](byval.md).</span></span>  
  
 <span data-ttu-id="db812-109">Puede proporcionar uno o varios argumentos a un `ParamArray` parámetro pasando una matriz del tipo de datos adecuado, una lista separada por comas de valores o nada en absoluto.</span><span class="sxs-lookup"><span data-stu-id="db812-109">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="db812-110">Para obtener más información, vea "llamar a ParamArray" en [matrices de parámetros](../../programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="db812-110">For details, see "Calling a ParamArray" in [Parameter Arrays](../../programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="db812-111">Siempre que se trata de una matriz que puede ser indefinidamente grande, existe el riesgo de que se produzca una gran cantidad de capacidad interna de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="db812-111">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="db812-112">Si acepta una matriz de parámetros del código de llamada, debe probar su longitud y tomar las medidas adecuadas si es demasiado grande para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="db812-112">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="db812-113">El modificador `ParamArray` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="db812-113">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="db812-114">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="db812-114">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="db812-115">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="db812-115">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="db812-116">Property Statement</span><span class="sxs-lookup"><span data-stu-id="db812-116">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="db812-117">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="db812-117">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="db812-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="db812-118">See also</span></span>

- [<span data-ttu-id="db812-119">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="db812-119">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="db812-120">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="db812-120">Parameter Arrays</span></span>](../../programming-guide/language-features/procedures/parameter-arrays.md)
