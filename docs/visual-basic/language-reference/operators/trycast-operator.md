---
title: TryCast (Operador) (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6be11b49eb3b9d98e3bf147e9b1026d4ffc860c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="trycast-operator-visual-basic"></a><span data-ttu-id="9ee68-102">TryCast (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ee68-102">TryCast Operator (Visual Basic)</span></span>
<span data-ttu-id="9ee68-103">Introduce una operación de conversión de tipos que no produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="9ee68-103">Introduces a type conversion operation that does not throw an exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ee68-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9ee68-104">Remarks</span></span>  
 <span data-ttu-id="9ee68-105">Si se produce un error en un intento de conversión, `CType` y `DirectCast` ambos producen un <xref:System.InvalidCastException> error.</span><span class="sxs-lookup"><span data-stu-id="9ee68-105">If an attempted conversion fails, `CType` and `DirectCast` both throw an <xref:System.InvalidCastException> error.</span></span> <span data-ttu-id="9ee68-106">Esto puede afectar negativamente al rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9ee68-106">This can adversely affect the performance of your application.</span></span> <span data-ttu-id="9ee68-107">`TryCast`Devuelve [nada](../../../visual-basic/language-reference/nothing.md), de modo que en lugar de tener que controlar una posible excepción, solo necesita comprobar el resultado devuelto con `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="9ee68-107">`TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md), so that instead of having to handle a possible exception, you need only test the returned result against `Nothing`.</span></span>  
  
 <span data-ttu-id="9ee68-108">Usa el `TryCast` palabra clave de la misma forma que usa el [CType (función)](../../../visual-basic/language-reference/functions/ctype-function.md) y [DirectCast (operador)](../../../visual-basic/language-reference/operators/directcast-operator.md) (palabra clave).</span><span class="sxs-lookup"><span data-stu-id="9ee68-108">You use the `TryCast` keyword the same way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) keyword.</span></span> <span data-ttu-id="9ee68-109">Proporcione una expresión como el primer argumento y un tipo para convertir como segundo argumento.</span><span class="sxs-lookup"><span data-stu-id="9ee68-109">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="9ee68-110">`TryCast`sólo funciona en tipos de referencia, como clases e interfaces.</span><span class="sxs-lookup"><span data-stu-id="9ee68-110">`TryCast` operates only on reference types, such as classes and interfaces.</span></span> <span data-ttu-id="9ee68-111">Requiere una relación de herencia o implementación entre los dos tipos.</span><span class="sxs-lookup"><span data-stu-id="9ee68-111">It requires an inheritance or implementation relationship between the two types.</span></span> <span data-ttu-id="9ee68-112">Esto significa que un tipo debe heredar de o implementar la otra.</span><span class="sxs-lookup"><span data-stu-id="9ee68-112">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="9ee68-113">Errores y errores</span><span class="sxs-lookup"><span data-stu-id="9ee68-113">Errors and Failures</span></span>  
 <span data-ttu-id="9ee68-114">`TryCast`genera un error del compilador si detecta que no existe ninguna relación de herencia o implementación.</span><span class="sxs-lookup"><span data-stu-id="9ee68-114">`TryCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="9ee68-115">Pero la falta de un error del compilador no garantiza una conversión correcta.</span><span class="sxs-lookup"><span data-stu-id="9ee68-115">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="9ee68-116">Si la conversión deseada es de restricción, podría producirse un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9ee68-116">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="9ee68-117">Si esto ocurre, `TryCast` devuelve [nada](../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="9ee68-117">If this happens, `TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="9ee68-118">Palabras clave para conversiones</span><span class="sxs-lookup"><span data-stu-id="9ee68-118">Conversion Keywords</span></span>  
 <span data-ttu-id="9ee68-119">Una comparación de las palabras clave de conversión de tipo es como sigue.</span><span class="sxs-lookup"><span data-stu-id="9ee68-119">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="9ee68-120">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="9ee68-120">Keyword</span></span>|<span data-ttu-id="9ee68-121">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="9ee68-121">Data types</span></span>|<span data-ttu-id="9ee68-122">Relación de argumentos</span><span class="sxs-lookup"><span data-stu-id="9ee68-122">Argument relationship</span></span>|<span data-ttu-id="9ee68-123">Error de tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="9ee68-123">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="9ee68-124">Función CType</span><span class="sxs-lookup"><span data-stu-id="9ee68-124">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="9ee68-125">Los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="9ee68-125">Any data types</span></span>|<span data-ttu-id="9ee68-126">De ampliación o conversión de restricción se debe definir entre los dos tipos de datos</span><span class="sxs-lookup"><span data-stu-id="9ee68-126">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="9ee68-127">Produce<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="9ee68-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="9ee68-128">DirectCast (operador)</span><span class="sxs-lookup"><span data-stu-id="9ee68-128">DirectCast Operator</span></span>](../../../visual-basic/language-reference/operators/directcast-operator.md)|<span data-ttu-id="9ee68-129">Los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="9ee68-129">Any data types</span></span>|<span data-ttu-id="9ee68-130">Un tipo debe heredar de tipo ni lo implementa otro</span><span class="sxs-lookup"><span data-stu-id="9ee68-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="9ee68-131">Produce<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="9ee68-131">Throws <xref:System.InvalidCastException></span></span>|  
|`TryCast`|<span data-ttu-id="9ee68-132">Solo los tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="9ee68-132">Reference types only</span></span>|<span data-ttu-id="9ee68-133">Un tipo debe heredar de tipo ni lo implementa otro</span><span class="sxs-lookup"><span data-stu-id="9ee68-133">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="9ee68-134">Devuelve [nada](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="9ee68-134">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9ee68-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9ee68-135">Example</span></span>  
 <span data-ttu-id="9ee68-136">En el ejemplo siguiente se muestra cómo utilizar `TryCast`.</span><span class="sxs-lookup"><span data-stu-id="9ee68-136">The following example shows how to use `TryCast`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#6](../../../visual-basic/language-reference/codesnippet/VisualBasic/trycast-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9ee68-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ee68-137">See Also</span></span>  
 [<span data-ttu-id="9ee68-138">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="9ee68-138">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="9ee68-139">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="9ee68-139">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
