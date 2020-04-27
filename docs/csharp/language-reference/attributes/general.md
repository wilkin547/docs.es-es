---
title: 'Atributos reservados de C#: Conditional, Obsolete, AttributeUsage'
ms.date: 04/09/2020
description: El compilador interpreta estos atributos para que afecten al código generado por el compilador.
ms.openlocfilehash: c6d697dd08233ffc88900949998047137ee170a9
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021768"
---
# <a name="reserved-attributes-conditionalattribute-obsoleteattribute-attributeusageattribute"></a><span data-ttu-id="da198-103">Atributos reservados: ConditionalAttribute, ObsoleteAttribute, AttributeUsageAttribute</span><span class="sxs-lookup"><span data-stu-id="da198-103">Reserved attributes: ConditionalAttribute, ObsoleteAttribute, AttributeUsageAttribute</span></span>

<span data-ttu-id="da198-104">Estos atributos se pueden aplicar a los elementos del código.</span><span class="sxs-lookup"><span data-stu-id="da198-104">These attributes can be applied to elements in your code.</span></span> <span data-ttu-id="da198-105">Agregan significado semántico a esos elementos.</span><span class="sxs-lookup"><span data-stu-id="da198-105">They add semantic meaning to those elements.</span></span> <span data-ttu-id="da198-106">El compilador usa esos significados semánticos para modificar su salida e informar de los posibles errores por parte de los desarrolladores que usan el código.</span><span class="sxs-lookup"><span data-stu-id="da198-106">The compiler uses those semantic meanings to alter its output and report possible mistakes by developers using your code.</span></span>

## <a name="conditional-attribute"></a><span data-ttu-id="da198-107">Atributo `Conditional`</span><span class="sxs-lookup"><span data-stu-id="da198-107">`Conditional` attribute</span></span>

<span data-ttu-id="da198-108">El atributo `Conditional` hace que la ejecución de un método dependa de un identificador de preprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="da198-108">The `Conditional` attribute makes the execution of a method dependent on a preprocessing identifier.</span></span> <span data-ttu-id="da198-109">El atributo `Conditional` es un alias de <xref:System.Diagnostics.ConditionalAttribute> y se puede aplicar a un método o a una clase de atributo.</span><span class="sxs-lookup"><span data-stu-id="da198-109">The `Conditional` attribute is an alias for <xref:System.Diagnostics.ConditionalAttribute>, and can be applied to a method or an attribute class.</span></span>

<span data-ttu-id="da198-110">En el ejemplo siguiente, `Conditional` se aplica a un método para habilitar o deshabilitar la representación de información de diagnóstico específica del programa:</span><span class="sxs-lookup"><span data-stu-id="da198-110">In the following example, `Conditional` is applied to a method to enable or disable the display of program-specific diagnostic information:</span></span>

:::code language="csharp" source="snippets/trace.cs" interactive="try-dotnet" :::

<span data-ttu-id="da198-111">Si no se define el identificador `TRACE_ON`, no se muestra el resultado del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="da198-111">If the `TRACE_ON` identifier isn't defined, the trace output isn't displayed.</span></span> <span data-ttu-id="da198-112">Explore por sí mismo en la ventana interactiva.</span><span class="sxs-lookup"><span data-stu-id="da198-112">Explore for yourself in the interactive window.</span></span>

<span data-ttu-id="da198-113">El atributo `Conditional` se suele usar con el identificador `DEBUG` para habilitar las funciones de seguimiento y de registro para las compilaciones de depuración, pero no en las compilaciones de versión, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="da198-113">The `Conditional` attribute is often used with the `DEBUG` identifier to enable trace and logging features for debug builds but not in release builds, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetConditional" :::

<span data-ttu-id="da198-114">Al llamar a un método marcado como condicional, la presencia o ausencia del símbolo de preprocesamiento especificado determina si se incluye o se omite la llamada.</span><span class="sxs-lookup"><span data-stu-id="da198-114">When a method marked conditional is called, the presence or absence of the specified preprocessing symbol determines whether the call is included or omitted.</span></span> <span data-ttu-id="da198-115">Si el símbolo está definido, se incluye la llamada; de lo contrario, se omite la llamada.</span><span class="sxs-lookup"><span data-stu-id="da198-115">If the symbol is defined, the call is included; otherwise, the call is omitted.</span></span> <span data-ttu-id="da198-116">Un método condicional debe ser un método de una declaración de clase o estructura, y no debe tener un tipo de valor devuelto `void`.</span><span class="sxs-lookup"><span data-stu-id="da198-116">A conditional method must be a method in a class or struct declaration and must have a `void` return type.</span></span> <span data-ttu-id="da198-117">El uso de `Conditional` resulta más limpio y elegante, y menos propenso a generar errores que incluir los métodos dentro de bloques `#if…#endif`.</span><span class="sxs-lookup"><span data-stu-id="da198-117">Using `Conditional` is cleaner, more elegant, and less error-prone than enclosing methods inside `#if…#endif` blocks.</span></span>

<span data-ttu-id="da198-118">Si un método tiene varios atributos `Conditional`, se incluye una llamada al método si se define uno o más símbolos condicionales (los símbolos se vinculan de manera lógica entre sí mediante el operador OR).</span><span class="sxs-lookup"><span data-stu-id="da198-118">If a method has multiple `Conditional` attributes, a call to the method is included if at one or more conditional symbols is defined (the symbols are logically linked together by using the OR operator).</span></span> <span data-ttu-id="da198-119">En el ejemplo siguiente, la presencia de `A` o `B` da como resultado una llamada al método:</span><span class="sxs-lookup"><span data-stu-id="da198-119">In the following example, the presence of either `A` or `B` results in a method call:</span></span>

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetMultipleConditions" :::

### <a name="using-conditional-with-attribute-classes"></a><span data-ttu-id="da198-120">Uso de `Conditional` con clases de atributos</span><span class="sxs-lookup"><span data-stu-id="da198-120">Using `Conditional` with attribute classes</span></span>

<span data-ttu-id="da198-121">El atributo `Conditional` también se puede aplicar a una definición de clase de atributo.</span><span class="sxs-lookup"><span data-stu-id="da198-121">The `Conditional` attribute can also be applied to an attribute class definition.</span></span> <span data-ttu-id="da198-122">En el ejemplo siguiente, el atributo personalizado `Documentation` solo agregará información a los metadatos si se define `DEBUG`.</span><span class="sxs-lookup"><span data-stu-id="da198-122">In the following example, the custom attribute `Documentation` will only add information to the metadata if `DEBUG` is defined.</span></span>

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetConditionalConditionalAttribute" :::

## <a name="obsolete-attribute"></a><span data-ttu-id="da198-123">Atributo `Obsolete`</span><span class="sxs-lookup"><span data-stu-id="da198-123">`Obsolete` attribute</span></span>

<span data-ttu-id="da198-124">El atributo `Obsolete` marca un elemento de código como ya no recomendado para su uso.</span><span class="sxs-lookup"><span data-stu-id="da198-124">The `Obsolete` attribute marks a code element as no longer recommended for use.</span></span> <span data-ttu-id="da198-125">El uso de una entidad marcada como obsoleta genera una advertencia o un error.</span><span class="sxs-lookup"><span data-stu-id="da198-125">Use of an entity marked obsolete generates a warning or an error.</span></span> <span data-ttu-id="da198-126">El atributo `Obsolete` es un atributo de uso único y se puede aplicar a cualquier entidad que admita atributos.</span><span class="sxs-lookup"><span data-stu-id="da198-126">The `Obsolete` attribute is a single-use attribute and can be applied to any entity that allows attributes.</span></span> <span data-ttu-id="da198-127">`Obsolete` es un alias de <xref:System.ObsoleteAttribute>.</span><span class="sxs-lookup"><span data-stu-id="da198-127">`Obsolete` is an alias for <xref:System.ObsoleteAttribute>.</span></span>

<span data-ttu-id="da198-128">En el ejemplo siguiente, el atributo `Obsolete` se aplica a la clase `A` y al método `B.OldMethod`.</span><span class="sxs-lookup"><span data-stu-id="da198-128">In the following example the `Obsolete` attribute is applied to class `A` and to method `B.OldMethod`.</span></span> <span data-ttu-id="da198-129">Dado que el segundo argumento del constructor de atributos aplicado a `B.OldMethod` está establecido en `true`, este método producirá un error del compilador, mientras que, si se usa la clase `A`, solo se generará una advertencia.</span><span class="sxs-lookup"><span data-stu-id="da198-129">Because the second argument of the attribute constructor applied to `B.OldMethod` is set to `true`, this method will cause a compiler error, whereas using class `A` will just produce a warning.</span></span> <span data-ttu-id="da198-130">En cambio, si se llama a `B.NewMethod`, no se generará ninguna advertencia o error.</span><span class="sxs-lookup"><span data-stu-id="da198-130">Calling `B.NewMethod`, however, produces no warning or error.</span></span> <span data-ttu-id="da198-131">Por ejemplo, al usarla con las definiciones anteriores, el código siguiente genera dos advertencias y un error:</span><span class="sxs-lookup"><span data-stu-id="da198-131">For example, when you use it with the previous definitions, the following code generates two warnings and one error:</span></span>

:::code language="csharp" source="snippets/ObsoleteExample.cs" interactive="try-dotnet" :::

<span data-ttu-id="da198-132">La cadena proporcionada como primer argumento al constructor del atributo se mostrará como parte de la advertencia o el error.</span><span class="sxs-lookup"><span data-stu-id="da198-132">The string provided as the first argument to the attribute constructor will be displayed as part of the warning or error.</span></span> <span data-ttu-id="da198-133">Se generan dos advertencias para la clase `A`: una para la declaración de la referencia de clase y otra para el constructor de clases.</span><span class="sxs-lookup"><span data-stu-id="da198-133">Two warnings for class `A` are generated: one for the declaration of the class reference, and one for the class constructor.</span></span> <span data-ttu-id="da198-134">El atributo `Obsolete` se puede usar sin argumentos, pero se recomienda incluir una explicación de qué se debe usar en su lugar.</span><span class="sxs-lookup"><span data-stu-id="da198-134">The `Obsolete` attribute can be used without arguments, but including an explanation what to use instead is recommended.</span></span>

## <a name="attributeusage-attribute"></a><span data-ttu-id="da198-135">Atributo `AttributeUsage`</span><span class="sxs-lookup"><span data-stu-id="da198-135">`AttributeUsage` attribute</span></span>

<span data-ttu-id="da198-136">El atributo `AttributeUsage` determina cómo se puede usar una clase de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="da198-136">The `AttributeUsage` attribute determines how a custom attribute class can be used.</span></span> <span data-ttu-id="da198-137"><xref:System.AttributeUsageAttribute> es un atributo que se aplica a las definiciones de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="da198-137"><xref:System.AttributeUsageAttribute> is an attribute you apply to custom attribute definitions.</span></span> <span data-ttu-id="da198-138">El atributo `AttributeUsage` permite controlar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="da198-138">The `AttributeUsage` attribute enables you to control:</span></span>

- <span data-ttu-id="da198-139">Los atributos de elementos de programa que se pueden aplicar.</span><span class="sxs-lookup"><span data-stu-id="da198-139">Which program elements attribute may be applied to.</span></span> <span data-ttu-id="da198-140">A menos que el uso esté restringido, un atributo se puede aplicar a cualquiera de los siguientes elementos de programa:</span><span class="sxs-lookup"><span data-stu-id="da198-140">Unless you restrict its usage, an attribute may be applied to any of the following program elements:</span></span>
  - <span data-ttu-id="da198-141">ensamblado</span><span class="sxs-lookup"><span data-stu-id="da198-141">assembly</span></span>
  - <span data-ttu-id="da198-142">module</span><span class="sxs-lookup"><span data-stu-id="da198-142">module</span></span>
  - <span data-ttu-id="da198-143">campo</span><span class="sxs-lookup"><span data-stu-id="da198-143">field</span></span>
  - <span data-ttu-id="da198-144">event</span><span class="sxs-lookup"><span data-stu-id="da198-144">event</span></span>
  - <span data-ttu-id="da198-145">método</span><span class="sxs-lookup"><span data-stu-id="da198-145">method</span></span>
  - <span data-ttu-id="da198-146">param</span><span class="sxs-lookup"><span data-stu-id="da198-146">param</span></span>
  - <span data-ttu-id="da198-147">propiedad</span><span class="sxs-lookup"><span data-stu-id="da198-147">property</span></span>
  - <span data-ttu-id="da198-148">return</span><span class="sxs-lookup"><span data-stu-id="da198-148">return</span></span>
  - <span data-ttu-id="da198-149">type</span><span class="sxs-lookup"><span data-stu-id="da198-149">type</span></span>
- <span data-ttu-id="da198-150">Si un atributo se puede aplicar a un mismo elemento de programa varias veces.</span><span class="sxs-lookup"><span data-stu-id="da198-150">Whether an attribute can be applied to a single program element multiple times.</span></span>
- <span data-ttu-id="da198-151">Si las clases derivadas heredan atributos.</span><span class="sxs-lookup"><span data-stu-id="da198-151">Whether attributes are inherited by derived classes.</span></span>

<span data-ttu-id="da198-152">La configuración predeterminada se parece al siguiente ejemplo cuando se aplica explícitamente:</span><span class="sxs-lookup"><span data-stu-id="da198-152">The default settings look like the following example when applied explicitly:</span></span>

:::code language="csharp" source="snippets/NewAttribute.cs" id="SnippetUsageFirst" :::

<span data-ttu-id="da198-153">En este ejemplo, la clase `NewAttribute` se puede aplicar a cualquier elemento de programación compatible,</span><span class="sxs-lookup"><span data-stu-id="da198-153">In this example, the `NewAttribute` class can be applied to any supported program element.</span></span> <span data-ttu-id="da198-154">pero solamente se puede aplicar una vez a cada entidad.</span><span class="sxs-lookup"><span data-stu-id="da198-154">But it can be applied only once to each entity.</span></span> <span data-ttu-id="da198-155">Las clases derivadas heredan el atributo cuando se aplica a una clase base.</span><span class="sxs-lookup"><span data-stu-id="da198-155">The attribute is inherited by derived classes when applied to a base class.</span></span>

<span data-ttu-id="da198-156">Los argumentos <xref:System.AttributeUsageAttribute.AllowMultiple> y <xref:System.AttributeUsageAttribute.Inherited> son opcionales, por lo que el siguiente código tiene el mismo efecto:</span><span class="sxs-lookup"><span data-stu-id="da198-156">The <xref:System.AttributeUsageAttribute.AllowMultiple> and <xref:System.AttributeUsageAttribute.Inherited> arguments are optional, so the following code has the same effect:</span></span>

:::code language="csharp" source="snippets/NewAttribute.cs" id="SnippetUsageSecond" :::

<span data-ttu-id="da198-157">El primer argumento <xref:System.AttributeUsageAttribute> debe ser uno o varios elementos de la enumeración <xref:System.AttributeTargets>.</span><span class="sxs-lookup"><span data-stu-id="da198-157">The first <xref:System.AttributeUsageAttribute> argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="da198-158">Se pueden vincular diversos tipos de destino con el operador OR, como se refleja en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="da198-158">Multiple target types can be linked together with the OR operator, like the following example shows:</span></span>

:::code language="csharp" source="snippets/NewPropertyOrFieldAttribute.cs" id="SnippetDefinePropertyAttribute" :::

<span data-ttu-id="da198-159">A partir de C# 7.3, los atributos se pueden aplicar a la propiedad o el campo de respaldo de una propiedad implementada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="da198-159">Beginning in C# 7.3, attributes can be applied to either the property or the backing field for an auto-implemented property.</span></span> <span data-ttu-id="da198-160">El atributo se aplica a la propiedad, a menos que se indique el especificador `field` en el atributo.</span><span class="sxs-lookup"><span data-stu-id="da198-160">The attribute applies to the property, unless you specify the `field` specifier on the attribute.</span></span> <span data-ttu-id="da198-161">Ambos se muestran en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="da198-161">Both are shown in the following example:</span></span>

:::code language="csharp" source="snippets/NewPropertyOrFieldAttribute.cs" id="SnippetUsePropertyAttribute" :::

<span data-ttu-id="da198-162">Si el argumento <xref:System.AttributeUsageAttribute.AllowMultiple> es `true`, el atributo resultante se puede aplicar más de una vez a cada una de las entidades, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="da198-162">If the <xref:System.AttributeUsageAttribute.AllowMultiple> argument is `true`, then the resulting attribute can be applied more than once to a single entity, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/MultiUseAttribute.cs" id="SnippetMultiUse" :::

<span data-ttu-id="da198-163">En este caso, `MultiUseAttribute` se puede aplicar varias veces porque `AllowMultiple` está establecido en `true`.</span><span class="sxs-lookup"><span data-stu-id="da198-163">In this case, `MultiUseAttribute` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="da198-164">Los dos formatos mostrados para aplicar varios atributos son válidos.</span><span class="sxs-lookup"><span data-stu-id="da198-164">Both formats shown for applying multiple attributes are valid.</span></span>

<span data-ttu-id="da198-165">Si <xref:System.AttributeUsageAttribute.Inherited> se establece en `false`, las clases que se derivan de una clase con atributos no heredan el atributo.</span><span class="sxs-lookup"><span data-stu-id="da198-165">If <xref:System.AttributeUsageAttribute.Inherited> is `false`, then the attribute isn't inherited by classes derived from an attributed class.</span></span> <span data-ttu-id="da198-166">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="da198-166">For example:</span></span>

:::code language="csharp" source="snippets/NonInheritedAttribute.cs" id="SnippetNonInherited" :::

<span data-ttu-id="da198-167">En este caso, `NonInheritedAttribute` no se aplica a `DClass` a través de la herencia.</span><span class="sxs-lookup"><span data-stu-id="da198-167">In this case `NonInheritedAttribute` isn't applied to `DClass` via inheritance.</span></span>

## <a name="see-also"></a><span data-ttu-id="da198-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="da198-168">See also</span></span>

- <xref:System.Attribute>
- <xref:System.Reflection>
- [<span data-ttu-id="da198-169">Atributos</span><span class="sxs-lookup"><span data-stu-id="da198-169">Attributes</span></span>](../../../standard/attributes/index.md)
- [<span data-ttu-id="da198-170">Reflexión</span><span class="sxs-lookup"><span data-stu-id="da198-170">Reflection</span></span>](../../programming-guide/concepts/reflection.md)
