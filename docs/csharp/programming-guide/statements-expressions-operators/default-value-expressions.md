---
title: "Expresiones de valor predeterminado (Guía de programación de C#)"
description: Las expresiones de valor predeterminado generan el valor predeterminado de cualquier tipo de referencia o valor.
ms.date: 2017-08-23
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 0dc2fcee3903b80816c98bab47e2b9a2e5ef78b0
ms.openlocfilehash: 7b5b53d7ed92c6f6377a3e494daf1d02a4cf0934
ms.contentlocale: es-es
ms.lasthandoff: 08/28/2017

---
# <a name="default-value-expressions-c-programming-guide"></a><span data-ttu-id="e030e-103">Expresiones de valor predeterminado (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="e030e-103">default value expressions (C# programming guide)</span></span>

<span data-ttu-id="e030e-104">Una expresión de valor predeterminado genera el valor predeterminado de un tipo.</span><span class="sxs-lookup"><span data-stu-id="e030e-104">A default value expression produces the default value for a type.</span></span> <span data-ttu-id="e030e-105">Las expresiones de valor predeterminado son particularmente útiles en clases y métodos genéricos.</span><span class="sxs-lookup"><span data-stu-id="e030e-105">Default value expressions are particularly useful in generic classes and methods.</span></span> <span data-ttu-id="e030e-106">Un problema que aparece tras usar elementos genéricos es cómo asignar un valor predeterminado a un `T` de tipo parametrizado cuando no conoce la información siguiente de antemano:</span><span class="sxs-lookup"><span data-stu-id="e030e-106">One issue that arises using generics is how to assign a default value to a parameterized type `T` when you do not know the following in advance:</span></span>

- <span data-ttu-id="e030e-107">Si `T` es un tipo de referencia o un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="e030e-107">Whether `T` is a reference type or a value type.</span></span>
- <span data-ttu-id="e030e-108">Si `T` es un tipo de valor, un valor numérico o una estructura definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e030e-108">If `T` is a value type, whether is a numeric value or a user-defined struct.</span></span>

 <span data-ttu-id="e030e-109">Dada una variable `t` de un `T` de tipo parametrizado, la instrucción `t = null` solo es válida si `T` es un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="e030e-109">Given a variable `t` of a parameterized type `T`, the statement `t = null` is only valid if `T` is a reference type.</span></span> <span data-ttu-id="e030e-110">La asignación `t = 0` solo funciona para los tipos de valor numérico, pero no para las estructuras.</span><span class="sxs-lookup"><span data-stu-id="e030e-110">The assignment `t = 0` only works for numeric value types but not for structs.</span></span> <span data-ttu-id="e030e-111">La solución consiste en usar una expresión de valor predeterminado, que devuelve `null` para los tipos de referencia (tipos de clase y de interfaz) y cero para los tipos de valor numérico.</span><span class="sxs-lookup"><span data-stu-id="e030e-111">The solution is to use a default value expression, which returns `null` for reference types (class types and interface types) and zero for numeric value types.</span></span> <span data-ttu-id="e030e-112">Para las estructuras definidas por el usuario, devuelve la estructura inicializada con el patrón de bit cero, lo que produce 0 o `null` para cada miembro dependiendo de si es un tipo de valor o referencia.</span><span class="sxs-lookup"><span data-stu-id="e030e-112">For user-defined structs, it returns the struct initialized to the zero bit pattern, which produces 0 or `null` for each member depending on whether that member is a value or reference type.</span></span> <span data-ttu-id="e030e-113">Para los tipos de valor que aceptan valores NULL, `default` devuelve un <xref:System.Nullable%601?displayProperty=fullName>, que se inicializa como cualquier estructura.</span><span class="sxs-lookup"><span data-stu-id="e030e-113">For nullable value types, `default` returns a <xref:System.Nullable%601?displayProperty=fullName>, which is initialized like any struct.</span></span>

<span data-ttu-id="e030e-114">La expresión `default(T)` no se limita a métodos y clases genéricas.</span><span class="sxs-lookup"><span data-stu-id="e030e-114">The `default(T)` expression is not limited to generic classes and methods.</span></span> <span data-ttu-id="e030e-115">Las expresiones de valor predeterminado pueden usarse con cualquier tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="e030e-115">Default value expressions can be used with any managed type.</span></span> <span data-ttu-id="e030e-116">Cualquiera de estas expresiones es válida:</span><span class="sxs-lookup"><span data-stu-id="e030e-116">Any of these expressions are valid:</span></span>

 <span data-ttu-id="e030e-117">[!code-cs[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]</span><span class="sxs-lookup"><span data-stu-id="e030e-117">[!code-cs[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]</span></span>

 <span data-ttu-id="e030e-118">El ejemplo siguiente de la clase `GenericList<T>` muestra cómo usar el operador `default(T)` en una clase genérica.</span><span class="sxs-lookup"><span data-stu-id="e030e-118">The following example from the `GenericList<T>` class shows how to use the `default(T)` operator in a generic class.</span></span> <span data-ttu-id="e030e-119">Para obtener más información, vea [Información general de genéricos](../generics/introduction-to-generics.md).</span><span class="sxs-lookup"><span data-stu-id="e030e-119">For more information, see [Generics Overview](../generics/introduction-to-generics.md).</span></span>

 <span data-ttu-id="e030e-120">[!code-cs[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]</span><span class="sxs-lookup"><span data-stu-id="e030e-120">[!code-cs[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]</span></span>

## <a name="default-literal-and-type-inference"></a><span data-ttu-id="e030e-121">Literal e inferencia de tipo predeterminados</span><span class="sxs-lookup"><span data-stu-id="e030e-121">default literal and type inference</span></span>

<span data-ttu-id="e030e-122">A partir de C# 7.1, el literal `default` puede usarse para las expresiones de valor predeterminado cuando el compilador puede deducir el tipo de expresión.</span><span class="sxs-lookup"><span data-stu-id="e030e-122">Beginning with C# 7.1, the `default` literal can be used for default value expressions when the compiler can infer the type of the expression.</span></span> <span data-ttu-id="e030e-123">El literal `default` genera el mismo valor que el equivalente `default(T)` cuando se deduce el tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="e030e-123">The `default` literal produces the same value as the equivalent `default(T)` where `T` is the inferred type.</span></span> <span data-ttu-id="e030e-124">Esto puede simplificar el código disminuyendo la redundancia al declarar un tipo más de una vez.</span><span class="sxs-lookup"><span data-stu-id="e030e-124">This can make code more concise by reducing the redundancy of declaring a type more than once.</span></span> <span data-ttu-id="e030e-125">El literal `default` puede usarse en cualquiera de las ubicaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e030e-125">The `default` literal can be used in any of the following locations:</span></span>

- <span data-ttu-id="e030e-126">inicializador de variable</span><span class="sxs-lookup"><span data-stu-id="e030e-126">variable initializer</span></span>
- <span data-ttu-id="e030e-127">asignación de variables</span><span class="sxs-lookup"><span data-stu-id="e030e-127">variable assignment</span></span>
- <span data-ttu-id="e030e-128">Declarar el valor predeterminado de un parámetro opcional</span><span class="sxs-lookup"><span data-stu-id="e030e-128">declaring the default value for an optional parameter</span></span>
- <span data-ttu-id="e030e-129">Proporcionar el valor de un argumento de método de llamada</span><span class="sxs-lookup"><span data-stu-id="e030e-129">providing the value for a method call argument</span></span>
- <span data-ttu-id="e030e-130">Devolver la instrucción (o una expresión de un miembro con cuerpo de expresión)</span><span class="sxs-lookup"><span data-stu-id="e030e-130">return statement (or expression in an expression bodied member)</span></span>

<span data-ttu-id="e030e-131">El ejemplo siguiente muestra varios usos del literal `default` en una expresión de valor predeterminado:</span><span class="sxs-lookup"><span data-stu-id="e030e-131">The following example shows many usages of the `default` literal in a default value expression:</span></span>

<span data-ttu-id="e030e-132">[!code-cs[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]</span><span class="sxs-lookup"><span data-stu-id="e030e-132">[!code-cs[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e030e-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="e030e-133">See also</span></span>

 <span data-ttu-id="e030e-134"><xref:System.Collections.Generic> [Guía de programación de C#](../index.md) </span><span class="sxs-lookup"><span data-stu-id="e030e-134"><xref:System.Collections.Generic> [C# Programming Guide](../index.md) </span></span>  
 <span data-ttu-id="e030e-135">[Genéricos](../generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="e030e-135">[Generics](../generics/index.md) </span></span>  
 <span data-ttu-id="e030e-136">[Métodos genéricos](../generics/generic-methods.md) </span><span class="sxs-lookup"><span data-stu-id="e030e-136">[Generic Methods](../generics/generic-methods.md) </span></span>  
 [<span data-ttu-id="e030e-137">Genéricos</span><span class="sxs-lookup"><span data-stu-id="e030e-137">Generics</span></span>](~/docs/standard/generics/index.md)   

