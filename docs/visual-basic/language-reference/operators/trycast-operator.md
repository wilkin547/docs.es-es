---
description: 'Más información acerca de: operador TryCast (Visual Basic)'
title: Operador TryCast
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: 5b941ec40c4ba0198fced64d0ef039605efad472
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795253"
---
# <a name="trycast-operator-visual-basic"></a><span data-ttu-id="4ad60-103">TryCast (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ad60-103">TryCast Operator (Visual Basic)</span></span>

<span data-ttu-id="4ad60-104">Introduce una operación de conversión de tipos que no produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="4ad60-104">Introduces a type conversion operation that does not throw an exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ad60-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4ad60-105">Remarks</span></span>  

 <span data-ttu-id="4ad60-106">Si se produce un error en una conversión intentada `CType` y `DirectCast` ambos producen un <xref:System.InvalidCastException> error.</span><span class="sxs-lookup"><span data-stu-id="4ad60-106">If an attempted conversion fails, `CType` and `DirectCast` both throw an <xref:System.InvalidCastException> error.</span></span> <span data-ttu-id="4ad60-107">Esto puede afectar negativamente al rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4ad60-107">This can adversely affect the performance of your application.</span></span> <span data-ttu-id="4ad60-108">`TryCast` no devuelve [nada](../nothing.md), de modo que, en lugar de tener que controlar una posible excepción, solo se necesita probar el resultado devuelto con `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="4ad60-108">`TryCast` returns [Nothing](../nothing.md), so that instead of having to handle a possible exception, you need only test the returned result against `Nothing`.</span></span>  
  
 <span data-ttu-id="4ad60-109">La `TryCast` palabra clave se usa de la misma manera que se usa la [función ctype](../functions/ctype-function.md) y la palabra clave del [operador DirectCast](directcast-operator.md) .</span><span class="sxs-lookup"><span data-stu-id="4ad60-109">You use the `TryCast` keyword the same way you use the [CType Function](../functions/ctype-function.md) and the [DirectCast Operator](directcast-operator.md) keyword.</span></span> <span data-ttu-id="4ad60-110">Proporcione una expresión como primer argumento y un tipo al que convertirlo como segundo argumento.</span><span class="sxs-lookup"><span data-stu-id="4ad60-110">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="4ad60-111">`TryCast` solo funciona en tipos de referencia, como clases e interfaces.</span><span class="sxs-lookup"><span data-stu-id="4ad60-111">`TryCast` operates only on reference types, such as classes and interfaces.</span></span> <span data-ttu-id="4ad60-112">Requiere una relación de herencia o implementación entre los dos tipos.</span><span class="sxs-lookup"><span data-stu-id="4ad60-112">It requires an inheritance or implementation relationship between the two types.</span></span> <span data-ttu-id="4ad60-113">Esto significa que un tipo debe heredar de o implementar el otro.</span><span class="sxs-lookup"><span data-stu-id="4ad60-113">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="4ad60-114">Errores y errores</span><span class="sxs-lookup"><span data-stu-id="4ad60-114">Errors and Failures</span></span>  

 <span data-ttu-id="4ad60-115">`TryCast` genera un error del compilador si detecta que no existe ninguna relación de herencia o de implementación.</span><span class="sxs-lookup"><span data-stu-id="4ad60-115">`TryCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="4ad60-116">Pero la falta de un error del compilador no garantiza una conversión correcta.</span><span class="sxs-lookup"><span data-stu-id="4ad60-116">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="4ad60-117">Si la conversión deseada es de restricción, podría producirse un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4ad60-117">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="4ad60-118">Si esto ocurre, no `TryCast` devuelve [nada](../nothing.md).</span><span class="sxs-lookup"><span data-stu-id="4ad60-118">If this happens, `TryCast` returns [Nothing](../nothing.md).</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="4ad60-119">Palabras clave para conversiones</span><span class="sxs-lookup"><span data-stu-id="4ad60-119">Conversion Keywords</span></span>  

 <span data-ttu-id="4ad60-120">A continuación se muestra una comparación de las palabras clave de conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="4ad60-120">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="4ad60-121">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="4ad60-121">Keyword</span></span>|<span data-ttu-id="4ad60-122">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="4ad60-122">Data types</span></span>|<span data-ttu-id="4ad60-123">Relación entre argumentos</span><span class="sxs-lookup"><span data-stu-id="4ad60-123">Argument relationship</span></span>|<span data-ttu-id="4ad60-124">Error en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4ad60-124">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="4ad60-125">CType Function</span><span class="sxs-lookup"><span data-stu-id="4ad60-125">CType Function</span></span>](../functions/ctype-function.md)|<span data-ttu-id="4ad60-126">Cualquier tipo de datos</span><span class="sxs-lookup"><span data-stu-id="4ad60-126">Any data types</span></span>|<span data-ttu-id="4ad60-127">La conversión de ampliación o de restricción debe definirse entre los dos tipos de datos</span><span class="sxs-lookup"><span data-stu-id="4ad60-127">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="4ad60-128">Produce <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="4ad60-128">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="4ad60-129">Operador DirectCast</span><span class="sxs-lookup"><span data-stu-id="4ad60-129">DirectCast Operator</span></span>](directcast-operator.md)|<span data-ttu-id="4ad60-130">Cualquier tipo de datos</span><span class="sxs-lookup"><span data-stu-id="4ad60-130">Any data types</span></span>|<span data-ttu-id="4ad60-131">Un tipo debe heredar de o implementar el otro tipo</span><span class="sxs-lookup"><span data-stu-id="4ad60-131">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="4ad60-132">Produce <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="4ad60-132">Throws <xref:System.InvalidCastException></span></span>|  
|`TryCast`|<span data-ttu-id="4ad60-133">Solo tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="4ad60-133">Reference types only</span></span>|<span data-ttu-id="4ad60-134">Un tipo debe heredar de o implementar el otro tipo</span><span class="sxs-lookup"><span data-stu-id="4ad60-134">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="4ad60-135">No devuelve [nada](../nothing.md)</span><span class="sxs-lookup"><span data-stu-id="4ad60-135">Returns [Nothing](../nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4ad60-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4ad60-136">Example</span></span>  

 <span data-ttu-id="4ad60-137">En el ejemplo siguiente se muestra cómo utilizar `TryCast`.</span><span class="sxs-lookup"><span data-stu-id="4ad60-137">The following example shows how to use `TryCast`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="4ad60-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ad60-138">See also</span></span>

- [<span data-ttu-id="4ad60-139">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="4ad60-139">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="4ad60-140">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="4ad60-140">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
