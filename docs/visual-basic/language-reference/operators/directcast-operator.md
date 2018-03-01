---
title: DirectCast (Operador) (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d9b81abea364e328b831ee98c3b847161c3f7dd3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="directcast-operator-visual-basic"></a><span data-ttu-id="b64c8-102">DirectCast (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b64c8-102">DirectCast Operator (Visual Basic)</span></span>
<span data-ttu-id="b64c8-103">Introduce una operación de conversión de tipos en función de herencia o implementación.</span><span class="sxs-lookup"><span data-stu-id="b64c8-103">Introduces a type conversion operation based on inheritance or implementation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b64c8-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b64c8-104">Remarks</span></span>  
 <span data-ttu-id="b64c8-105">`DirectCast`no se utiliza Visual Basic rutinas auxiliares de tiempo de ejecución para la conversión, por lo que puede proporcionar un poco retrasada con un rendimiento mayor que `CType` al convertir a y desde el tipo de datos `Object`.</span><span class="sxs-lookup"><span data-stu-id="b64c8-105">`DirectCast` does not use the Visual Basic run-time helper routines for conversion, so it can provide somewhat better performance than `CType` when converting to and from data type `Object`.</span></span>  
  
 <span data-ttu-id="b64c8-106">Usa el `DirectCast` palabra clave similar a la forma de usar el [CType (función)](../../../visual-basic/language-reference/functions/ctype-function.md) y [TryCast (operador)](../../../visual-basic/language-reference/operators/trycast-operator.md) (palabra clave).</span><span class="sxs-lookup"><span data-stu-id="b64c8-106">You use the `DirectCast` keyword similar to the way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) keyword.</span></span> <span data-ttu-id="b64c8-107">Proporcione una expresión como el primer argumento y un tipo para convertir como segundo argumento.</span><span class="sxs-lookup"><span data-stu-id="b64c8-107">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="b64c8-108">`DirectCast`requiere una relación de herencia o implementación entre los tipos de datos de los dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="b64c8-108">`DirectCast` requires an inheritance or implementation relationship between the data types of the two arguments.</span></span> <span data-ttu-id="b64c8-109">Esto significa que un tipo debe heredar de o implementar la otra.</span><span class="sxs-lookup"><span data-stu-id="b64c8-109">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="b64c8-110">Errores y errores</span><span class="sxs-lookup"><span data-stu-id="b64c8-110">Errors and Failures</span></span>  
 <span data-ttu-id="b64c8-111">`DirectCast`genera un error del compilador si detecta que no existe ninguna relación de herencia o implementación.</span><span class="sxs-lookup"><span data-stu-id="b64c8-111">`DirectCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="b64c8-112">Pero la falta de un error del compilador no garantiza una conversión correcta.</span><span class="sxs-lookup"><span data-stu-id="b64c8-112">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="b64c8-113">Si la conversión deseada es de restricción, podría producirse un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b64c8-113">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="b64c8-114">Si esto ocurre, el runtime produce una <xref:System.InvalidCastException> error.</span><span class="sxs-lookup"><span data-stu-id="b64c8-114">If this happens, the runtime throws an <xref:System.InvalidCastException> error.</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="b64c8-115">Palabras clave para conversiones</span><span class="sxs-lookup"><span data-stu-id="b64c8-115">Conversion Keywords</span></span>  
 <span data-ttu-id="b64c8-116">Una comparación de las palabras clave de conversión de tipo es como sigue.</span><span class="sxs-lookup"><span data-stu-id="b64c8-116">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="b64c8-117">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="b64c8-117">Keyword</span></span>|<span data-ttu-id="b64c8-118">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="b64c8-118">Data types</span></span>|<span data-ttu-id="b64c8-119">Relación de argumentos</span><span class="sxs-lookup"><span data-stu-id="b64c8-119">Argument relationship</span></span>|<span data-ttu-id="b64c8-120">Error de tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b64c8-120">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="b64c8-121">Función CType</span><span class="sxs-lookup"><span data-stu-id="b64c8-121">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="b64c8-122">Los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="b64c8-122">Any data types</span></span>|<span data-ttu-id="b64c8-123">De ampliación o conversión de restricción se debe definir entre los dos tipos de datos</span><span class="sxs-lookup"><span data-stu-id="b64c8-123">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="b64c8-124">Produce<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="b64c8-124">Throws <xref:System.InvalidCastException></span></span>|  
|`DirectCast`|<span data-ttu-id="b64c8-125">Los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="b64c8-125">Any data types</span></span>|<span data-ttu-id="b64c8-126">Un tipo debe heredar de tipo ni lo implementa otro</span><span class="sxs-lookup"><span data-stu-id="b64c8-126">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="b64c8-127">Produce<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="b64c8-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="b64c8-128">TryCast (operador)</span><span class="sxs-lookup"><span data-stu-id="b64c8-128">TryCast Operator</span></span>](../../../visual-basic/language-reference/operators/trycast-operator.md)|<span data-ttu-id="b64c8-129">Solo los tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="b64c8-129">Reference types only</span></span>|<span data-ttu-id="b64c8-130">Un tipo debe heredar de tipo ni lo implementa otro</span><span class="sxs-lookup"><span data-stu-id="b64c8-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="b64c8-131">Devuelve [nada](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="b64c8-131">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b64c8-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b64c8-132">Example</span></span>  
 <span data-ttu-id="b64c8-133">En el ejemplo siguiente se muestra dos usos de `DirectCast`, uno que se produce un error en tiempo de ejecución y uno que sea correcto.</span><span class="sxs-lookup"><span data-stu-id="b64c8-133">The following example demonstrates two uses of `DirectCast`, one that fails at run time and one that succeeds.</span></span>  
  
 [!code-vb[VbVbalrKeywords#1](../../../visual-basic/language-reference/codesnippet/VisualBasic/directcast-operator_1.vb)]  
  
 <span data-ttu-id="b64c8-134">En el ejemplo anterior, escriba el tiempo de ejecución de `q` es `Double`.</span><span class="sxs-lookup"><span data-stu-id="b64c8-134">In the preceding example, the run-time type of `q` is `Double`.</span></span> <span data-ttu-id="b64c8-135">`CType`se realiza correctamente porque `Double` puede convertirse a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="b64c8-135">`CType` succeeds because `Double` can be converted to `Integer`.</span></span> <span data-ttu-id="b64c8-136">Sin embargo, la primera `DirectCast` se produce un error en tiempo de ejecución porque el tiempo de ejecución de tipos de `Double` no tiene ninguna relación de herencia con `Integer`, aunque existe una conversión.</span><span class="sxs-lookup"><span data-stu-id="b64c8-136">However, the first `DirectCast` fails at run time because the run-time type of `Double` has no inheritance relationship with `Integer`, even though a conversion exists.</span></span> <span data-ttu-id="b64c8-137">El segundo `DirectCast` se realiza correctamente porque convierte del tipo <xref:System.Windows.Forms.Form> al tipo <xref:System.Windows.Forms.Control>, desde el que <xref:System.Windows.Forms.Form> hereda.</span><span class="sxs-lookup"><span data-stu-id="b64c8-137">The second `DirectCast` succeeds because it converts from type <xref:System.Windows.Forms.Form> to type <xref:System.Windows.Forms.Control>, from which <xref:System.Windows.Forms.Form> inherits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b64c8-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="b64c8-138">See Also</span></span>  
 <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="b64c8-139">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="b64c8-139">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="b64c8-140">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="b64c8-140">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
