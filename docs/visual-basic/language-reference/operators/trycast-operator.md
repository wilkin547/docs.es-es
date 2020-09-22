---
title: Operador TryCast
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: dc4807781f9e1aaf894016952911bd7b32c42948
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875313"
---
# <a name="trycast-operator-visual-basic"></a><span data-ttu-id="de1f8-102">TryCast (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de1f8-102">TryCast Operator (Visual Basic)</span></span>

<span data-ttu-id="de1f8-103">Introduce una operación de conversión de tipos que no produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="de1f8-103">Introduces a type conversion operation that does not throw an exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de1f8-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de1f8-104">Remarks</span></span>  

 <span data-ttu-id="de1f8-105">Si se produce un error en una conversión intentada `CType` y `DirectCast` ambos producen un <xref:System.InvalidCastException> error.</span><span class="sxs-lookup"><span data-stu-id="de1f8-105">If an attempted conversion fails, `CType` and `DirectCast` both throw an <xref:System.InvalidCastException> error.</span></span> <span data-ttu-id="de1f8-106">Esto puede afectar negativamente al rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="de1f8-106">This can adversely affect the performance of your application.</span></span> <span data-ttu-id="de1f8-107">`TryCast` no devuelve [nada](../nothing.md), de modo que, en lugar de tener que controlar una posible excepción, solo se necesita probar el resultado devuelto con `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="de1f8-107">`TryCast` returns [Nothing](../nothing.md), so that instead of having to handle a possible exception, you need only test the returned result against `Nothing`.</span></span>  
  
 <span data-ttu-id="de1f8-108">La `TryCast` palabra clave se usa de la misma manera que se usa la [función ctype](../functions/ctype-function.md) y la palabra clave del [operador DirectCast](directcast-operator.md) .</span><span class="sxs-lookup"><span data-stu-id="de1f8-108">You use the `TryCast` keyword the same way you use the [CType Function](../functions/ctype-function.md) and the [DirectCast Operator](directcast-operator.md) keyword.</span></span> <span data-ttu-id="de1f8-109">Proporcione una expresión como primer argumento y un tipo al que convertirlo como segundo argumento.</span><span class="sxs-lookup"><span data-stu-id="de1f8-109">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="de1f8-110">`TryCast` solo funciona en tipos de referencia, como clases e interfaces.</span><span class="sxs-lookup"><span data-stu-id="de1f8-110">`TryCast` operates only on reference types, such as classes and interfaces.</span></span> <span data-ttu-id="de1f8-111">Requiere una relación de herencia o implementación entre los dos tipos.</span><span class="sxs-lookup"><span data-stu-id="de1f8-111">It requires an inheritance or implementation relationship between the two types.</span></span> <span data-ttu-id="de1f8-112">Esto significa que un tipo debe heredar de o implementar el otro.</span><span class="sxs-lookup"><span data-stu-id="de1f8-112">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="de1f8-113">Errores y errores</span><span class="sxs-lookup"><span data-stu-id="de1f8-113">Errors and Failures</span></span>  

 <span data-ttu-id="de1f8-114">`TryCast` genera un error del compilador si detecta que no existe ninguna relación de herencia o de implementación.</span><span class="sxs-lookup"><span data-stu-id="de1f8-114">`TryCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="de1f8-115">Pero la falta de un error del compilador no garantiza una conversión correcta.</span><span class="sxs-lookup"><span data-stu-id="de1f8-115">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="de1f8-116">Si la conversión deseada es de restricción, podría producirse un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="de1f8-116">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="de1f8-117">Si esto ocurre, no `TryCast` devuelve [nada](../nothing.md).</span><span class="sxs-lookup"><span data-stu-id="de1f8-117">If this happens, `TryCast` returns [Nothing](../nothing.md).</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="de1f8-118">Palabras clave para conversiones</span><span class="sxs-lookup"><span data-stu-id="de1f8-118">Conversion Keywords</span></span>  

 <span data-ttu-id="de1f8-119">A continuación se muestra una comparación de las palabras clave de conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="de1f8-119">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="de1f8-120">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="de1f8-120">Keyword</span></span>|<span data-ttu-id="de1f8-121">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="de1f8-121">Data types</span></span>|<span data-ttu-id="de1f8-122">Relación entre argumentos</span><span class="sxs-lookup"><span data-stu-id="de1f8-122">Argument relationship</span></span>|<span data-ttu-id="de1f8-123">Error en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="de1f8-123">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="de1f8-124">CType Function</span><span class="sxs-lookup"><span data-stu-id="de1f8-124">CType Function</span></span>](../functions/ctype-function.md)|<span data-ttu-id="de1f8-125">Cualquier tipo de datos</span><span class="sxs-lookup"><span data-stu-id="de1f8-125">Any data types</span></span>|<span data-ttu-id="de1f8-126">La conversión de ampliación o de restricción debe definirse entre los dos tipos de datos</span><span class="sxs-lookup"><span data-stu-id="de1f8-126">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="de1f8-127">Produce <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="de1f8-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="de1f8-128">Operador DirectCast</span><span class="sxs-lookup"><span data-stu-id="de1f8-128">DirectCast Operator</span></span>](directcast-operator.md)|<span data-ttu-id="de1f8-129">Cualquier tipo de datos</span><span class="sxs-lookup"><span data-stu-id="de1f8-129">Any data types</span></span>|<span data-ttu-id="de1f8-130">Un tipo debe heredar de o implementar el otro tipo</span><span class="sxs-lookup"><span data-stu-id="de1f8-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="de1f8-131">Produce <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="de1f8-131">Throws <xref:System.InvalidCastException></span></span>|  
|`TryCast`|<span data-ttu-id="de1f8-132">Solo tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="de1f8-132">Reference types only</span></span>|<span data-ttu-id="de1f8-133">Un tipo debe heredar de o implementar el otro tipo</span><span class="sxs-lookup"><span data-stu-id="de1f8-133">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="de1f8-134">No devuelve [nada](../nothing.md)</span><span class="sxs-lookup"><span data-stu-id="de1f8-134">Returns [Nothing](../nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="de1f8-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="de1f8-135">Example</span></span>  

 <span data-ttu-id="de1f8-136">En el ejemplo siguiente se muestra cómo utilizar `TryCast`.</span><span class="sxs-lookup"><span data-stu-id="de1f8-136">The following example shows how to use `TryCast`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="de1f8-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de1f8-137">See also</span></span>

- [<span data-ttu-id="de1f8-138">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="de1f8-138">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="de1f8-139">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="de1f8-139">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
