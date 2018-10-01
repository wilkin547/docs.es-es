---
title: Expresiones de valor predeterminado (Guía de programación de C#)
description: Las expresiones de valor predeterminado generan el valor predeterminado de cualquier tipo de referencia o valor.
ms.date: 04/25/2018
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.openlocfilehash: 94866f22fb3ad921a834cffb16fe17e44cef5965
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "47192633"
---
# <a name="default-value-expressions-c-programming-guide"></a><span data-ttu-id="2823d-103">Expresiones de valor predeterminado (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="2823d-103">default value expressions (C# programming guide)</span></span>

<span data-ttu-id="2823d-104">Una expresión de valor predeterminado `default(T)` genera el valor predeterminado de un tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="2823d-104">A default value expression `default(T)` produces the default value of a type `T`.</span></span> <span data-ttu-id="2823d-105">La siguiente tabla muestra los valores que se generan para distintos tipos:</span><span class="sxs-lookup"><span data-stu-id="2823d-105">The following table shows which values are produced for various types:</span></span>

|<span data-ttu-id="2823d-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="2823d-106">Type</span></span>|<span data-ttu-id="2823d-107">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="2823d-107">Default value</span></span>|
|---------|---------|
|<span data-ttu-id="2823d-108">Cualquier tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="2823d-108">Any reference type</span></span>|`null`|
|<span data-ttu-id="2823d-109">Tipo de valor numérico</span><span class="sxs-lookup"><span data-stu-id="2823d-109">Numeric value type</span></span>|<span data-ttu-id="2823d-110">Cero</span><span class="sxs-lookup"><span data-stu-id="2823d-110">Zero</span></span>|
|[<span data-ttu-id="2823d-111">bool</span><span class="sxs-lookup"><span data-stu-id="2823d-111">bool</span></span>](../../language-reference/keywords/bool.md)|`false`|
|[<span data-ttu-id="2823d-112">char</span><span class="sxs-lookup"><span data-stu-id="2823d-112">char</span></span>](../../language-reference/keywords/char.md)|`'\0'`|
|[<span data-ttu-id="2823d-113">enum</span><span class="sxs-lookup"><span data-stu-id="2823d-113">enum</span></span>](../../language-reference/keywords/enum.md)|<span data-ttu-id="2823d-114">Valor generado por la expresión `(E)0`, donde `E` es el identificador de enumeración.</span><span class="sxs-lookup"><span data-stu-id="2823d-114">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="2823d-115">struct</span><span class="sxs-lookup"><span data-stu-id="2823d-115">struct</span></span>](../../language-reference/keywords/struct.md)|<span data-ttu-id="2823d-116">Valor generado al establecer todos los campos de tipo de valor en sus valores predeterminados y todos los campos de tipo de referencia en `null`.</span><span class="sxs-lookup"><span data-stu-id="2823d-116">The value produced by setting all value type fields to their default value and all reference type fields to `null`.</span></span>|
|<span data-ttu-id="2823d-117">Tipo que acepta valores NULL</span><span class="sxs-lookup"><span data-stu-id="2823d-117">Nullable type</span></span>|<span data-ttu-id="2823d-118">Instancia para la que la propiedad <xref:System.Nullable%601.HasValue%2A> es `false` y la propiedad <xref:System.Nullable%601.Value%2A> no está definida.</span><span class="sxs-lookup"><span data-stu-id="2823d-118">An instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span>|

<span data-ttu-id="2823d-119">Las expresiones de valor predeterminado son particularmente útiles en clases y métodos genéricos.</span><span class="sxs-lookup"><span data-stu-id="2823d-119">Default value expressions are particularly useful in generic classes and methods.</span></span> <span data-ttu-id="2823d-120">Un problema que aparece tras usar elementos genéricos es cómo asignar un valor predeterminado a un `T` de tipo parametrizado cuando no conoce la información siguiente de antemano:</span><span class="sxs-lookup"><span data-stu-id="2823d-120">One issue that arises using generics is how to assign a default value of a parameterized type `T` when you don't know the following in advance:</span></span>

- <span data-ttu-id="2823d-121">Si `T` es un tipo de referencia o un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="2823d-121">Whether `T` is a reference type or a value type.</span></span>
- <span data-ttu-id="2823d-122">Si `T` es un tipo de valor, si es un valor numérico o un struct.</span><span class="sxs-lookup"><span data-stu-id="2823d-122">If `T` is a value type, whether it's a numeric value or a struct.</span></span>

 <span data-ttu-id="2823d-123">Dada una variable `t` de un `T` de tipo parametrizado, la instrucción `t = null` solo es válida si `T` es un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="2823d-123">Given a variable `t` of a parameterized type `T`, the statement `t = null` is only valid if `T` is a reference type.</span></span> <span data-ttu-id="2823d-124">La asignación `t = 0` solo funciona para los tipos de valor numérico, pero no para las estructuras.</span><span class="sxs-lookup"><span data-stu-id="2823d-124">The assignment `t = 0` only works for numeric value types but not for structs.</span></span> <span data-ttu-id="2823d-125">Para resolverlo, use una expresión de valor predeterminado:</span><span class="sxs-lookup"><span data-stu-id="2823d-125">To solve that, use a default value expression:</span></span>

```csharp
T t = default(T);
```

<span data-ttu-id="2823d-126">La expresión `default(T)` no se limita a métodos y clases genéricas.</span><span class="sxs-lookup"><span data-stu-id="2823d-126">The `default(T)` expression is not limited to generic classes and methods.</span></span> <span data-ttu-id="2823d-127">Las expresiones de valor predeterminado pueden usarse con cualquier tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="2823d-127">Default value expressions can be used with any managed type.</span></span> <span data-ttu-id="2823d-128">Cualquiera de estas expresiones es válida:</span><span class="sxs-lookup"><span data-stu-id="2823d-128">Any of these expressions are valid:</span></span>

 [!code-csharp[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]

 <span data-ttu-id="2823d-129">El ejemplo siguiente de la clase `GenericList<T>` muestra cómo usar el operador `default(T)` en una clase genérica.</span><span class="sxs-lookup"><span data-stu-id="2823d-129">The following example from the `GenericList<T>` class shows how to use the `default(T)` operator in a generic class.</span></span> <span data-ttu-id="2823d-130">Para obtener más información, vea [Introducción a los genéricos](../generics/introduction-to-generics.md).</span><span class="sxs-lookup"><span data-stu-id="2823d-130">For more information, see [Introduction to Generics](../generics/introduction-to-generics.md).</span></span>

 [!code-csharp[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]

## <a name="default-literal-and-type-inference"></a><span data-ttu-id="2823d-131">Literal e inferencia de tipo predeterminados</span><span class="sxs-lookup"><span data-stu-id="2823d-131">default literal and type inference</span></span>

<span data-ttu-id="2823d-132">A partir de C# 7.1, el literal `default` puede usarse para las expresiones de valor predeterminado cuando el compilador puede deducir el tipo de expresión.</span><span class="sxs-lookup"><span data-stu-id="2823d-132">Beginning with C# 7.1, the `default` literal can be used for default value expressions when the compiler can infer the type of the expression.</span></span> <span data-ttu-id="2823d-133">El literal `default` genera el mismo valor que el equivalente `default(T)` cuando se deduce el tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="2823d-133">The `default` literal produces the same value as the equivalent `default(T)` where `T` is the inferred type.</span></span> <span data-ttu-id="2823d-134">Esto puede simplificar el código disminuyendo la redundancia al declarar un tipo más de una vez.</span><span class="sxs-lookup"><span data-stu-id="2823d-134">This can make code more concise by reducing the redundancy of declaring a type more than once.</span></span> <span data-ttu-id="2823d-135">El literal `default` puede usarse en cualquiera de las ubicaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2823d-135">The `default` literal can be used in any of the following locations:</span></span>

- <span data-ttu-id="2823d-136">inicializador de variable</span><span class="sxs-lookup"><span data-stu-id="2823d-136">variable initializer</span></span>
- <span data-ttu-id="2823d-137">asignación de variables</span><span class="sxs-lookup"><span data-stu-id="2823d-137">variable assignment</span></span>
- <span data-ttu-id="2823d-138">Declarar el valor predeterminado de un parámetro opcional</span><span class="sxs-lookup"><span data-stu-id="2823d-138">declaring the default value for an optional parameter</span></span>
- <span data-ttu-id="2823d-139">Proporcionar el valor de un argumento de método de llamada</span><span class="sxs-lookup"><span data-stu-id="2823d-139">providing the value for a method call argument</span></span>
- <span data-ttu-id="2823d-140">Devolver la instrucción (o una expresión de un miembro con cuerpo de expresión)</span><span class="sxs-lookup"><span data-stu-id="2823d-140">return statement (or expression in an expression bodied member)</span></span>

<span data-ttu-id="2823d-141">El ejemplo siguiente muestra varios usos del literal `default` en una expresión de valor predeterminado:</span><span class="sxs-lookup"><span data-stu-id="2823d-141">The following example shows many usages of the `default` literal in a default value expression:</span></span>

[!code-csharp[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]

## <a name="see-also"></a><span data-ttu-id="2823d-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="2823d-142">See Also</span></span>

- <xref:System.Collections.Generic>  
- [<span data-ttu-id="2823d-143">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2823d-143">C# Programming Guide</span></span>](../index.md)  
- [<span data-ttu-id="2823d-144">Genéricos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="2823d-144">Generics (C# Programming Guide)</span></span>](../generics/index.md)  
- [<span data-ttu-id="2823d-145">Métodos genéricos</span><span class="sxs-lookup"><span data-stu-id="2823d-145">Generic Methods</span></span>](../generics/generic-methods.md)  
- [<span data-ttu-id="2823d-146">Elementos genéricos en .NET</span><span class="sxs-lookup"><span data-stu-id="2823d-146">Generics in .NET</span></span>](~/docs/standard/generics/index.md)  
- [<span data-ttu-id="2823d-147">Tabla de valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="2823d-147">Default values table</span></span>](../../language-reference/keywords/default-values-table.md)
