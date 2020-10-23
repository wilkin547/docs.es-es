---
title: Tipos de referencia que aceptan valores NULL
description: En este artículo se proporciona información general sobre los tipos de referencia que aceptan valores NULL, una novedad de C# 8.0. Conocerá cómo esta característica proporciona protección contra excepciones de referencia NULL, tanto para proyectos nuevos como para los existentes.
ms.technology: csharp-null-safety
ms.date: 04/21/2020
ms.openlocfilehash: 9c253d02c287d7a113536ac148b352486d450cc2
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160885"
---
# <a name="nullable-reference-types"></a><span data-ttu-id="33e9b-104">Tipos de referencia que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="33e9b-104">Nullable reference types</span></span>

<span data-ttu-id="33e9b-105">Una de las novedades de C# 8.0 son los **tipos de referencia que aceptan valores NULL** y los **tipos de referencia que no aceptan valores NULL**, que permiten usar instrucciones importantes sobre las propiedades de variables de tipos de referencia:</span><span class="sxs-lookup"><span data-stu-id="33e9b-105">C# 8.0 introduces **nullable reference types** and **non-nullable reference types** that enable you to make important statements about the properties for reference type variables:</span></span>

- <span data-ttu-id="33e9b-106">**Se supone que una referencia no debe ser NULL**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-106">**A reference isn't supposed to be null**.</span></span> <span data-ttu-id="33e9b-107">Si las variables no deben ser NULL, el compilador aplica reglas que garantizan que sea seguro desreferenciar dichas variables sin comprobar primero que no se trata de un valor NULL:</span><span class="sxs-lookup"><span data-stu-id="33e9b-107">When variables aren't supposed to be null, the compiler enforces rules that ensure it's safe to dereference these variables without first checking that it isn't null:</span></span>
  - <span data-ttu-id="33e9b-108">La variable debe inicializarse como un valor distinto a NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-108">The variable must be initialized to a non-null value.</span></span>
  - <span data-ttu-id="33e9b-109">No se puede asignar el valor `null` a la variable.</span><span class="sxs-lookup"><span data-stu-id="33e9b-109">The variable can never be assigned the value `null`.</span></span>
- <span data-ttu-id="33e9b-110">**Una referencia puede ser NULL**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-110">**A reference may be null**.</span></span> <span data-ttu-id="33e9b-111">Si las variables pueden ser NULL, el compilador aplica reglas para garantizar que haya comprobado correctamente si hay referencias NULL:</span><span class="sxs-lookup"><span data-stu-id="33e9b-111">When variables may be null, the compiler enforces different rules to ensure that you've correctly checked for a null reference:</span></span>
  - <span data-ttu-id="33e9b-112">Solo se puede desreferenciar la variable si el compilador pueda garantizar que el valor no sea NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-112">The variable may only be dereferenced when the compiler can guarantee that the value isn't null.</span></span>
  - <span data-ttu-id="33e9b-113">Estas variables se pueden inicializar con el valor `null` predeterminado, y se les puede asignar el valor `null` en otro código.</span><span class="sxs-lookup"><span data-stu-id="33e9b-113">These variables may be initialized with the default `null` value and may be assigned the value `null` in other code.</span></span>

<span data-ttu-id="33e9b-114">Esta nueva característica proporciona grandes ventajas sobre el control de variables de referencia con respecto a versiones anteriores de C#, donde la intención del diseño no se puede determinar a partir de la declaración de la variable.</span><span class="sxs-lookup"><span data-stu-id="33e9b-114">This new feature provides significant benefits over the handling of reference variables in earlier versions of C# where the design intent can't be determined from the variable declaration.</span></span> <span data-ttu-id="33e9b-115">El compilador no proporcionaba protección contra excepciones de referencia NULL para los tipos de referencia:</span><span class="sxs-lookup"><span data-stu-id="33e9b-115">The compiler didn't provide safety against null reference exceptions for reference types:</span></span>

- <span data-ttu-id="33e9b-116">**Una referencia puede ser NULL**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-116">**A reference can be null**.</span></span> <span data-ttu-id="33e9b-117">El compilador no emite ninguna advertencia cuando un tipo de referencia se inicializa con un valor NULL o posteriormente se asigna a un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-117">The compiler doesn't issue warnings when a reference type is initialized to null, or later assigned to null.</span></span> <span data-ttu-id="33e9b-118">El compilador emite advertencias cuando estas variables se desreferencian sin comprobaciones de valores NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-118">The compiler issues warnings when these variables are dereferenced without null checks.</span></span>
- <span data-ttu-id="33e9b-119">**Se asume que una referencia no es NULL**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-119">**A reference is assumed to be not null**.</span></span> <span data-ttu-id="33e9b-120">Si se desreferencian tipos de referencia, el compilador no emite ninguna advertencia.</span><span class="sxs-lookup"><span data-stu-id="33e9b-120">The compiler doesn't issue any warnings when reference types are dereferenced.</span></span> <span data-ttu-id="33e9b-121">El compilador emite advertencias si una variable se establece en una expresión que puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-121">The compiler issues warnings if a variable is set to an expression that may be null.</span></span>

<span data-ttu-id="33e9b-122">Estas advertencias se emiten en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="33e9b-122">These warnings are emitted at compile time.</span></span> <span data-ttu-id="33e9b-123">El compilador no agrega comprobaciones de valores NULL ni otras construcciones de tiempo de ejecución en un contexto que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-123">The compiler doesn't add any null checks or other runtime constructs in a nullable context.</span></span> <span data-ttu-id="33e9b-124">En tiempo de ejecución, una referencia que acepta valores NULL y una referencia que no acepta valores NULL son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="33e9b-124">At runtime, a nullable reference and a non-nullable reference are equivalent.</span></span>

<span data-ttu-id="33e9b-125">Con la incorporación de los tipos de referencia que aceptan valores NULL, puede declarar su intención de forma más clara.</span><span class="sxs-lookup"><span data-stu-id="33e9b-125">With the addition of nullable reference types, you can declare your intent more clearly.</span></span> <span data-ttu-id="33e9b-126">El valor `null` es la forma adecuada de representar que una variable que no hace referencia a un valor.</span><span class="sxs-lookup"><span data-stu-id="33e9b-126">The `null` value is the correct way to represent that a variable doesn't refer to a value.</span></span> <span data-ttu-id="33e9b-127">No use esta característica para eliminar todos los valores `null` de su código.</span><span class="sxs-lookup"><span data-stu-id="33e9b-127">Don't use this feature to remove all `null` values from your code.</span></span> <span data-ttu-id="33e9b-128">En su lugar, debería declarar su intención al compilador para que los demás desarrolladores la puedan ver al leer el código.</span><span class="sxs-lookup"><span data-stu-id="33e9b-128">Rather, you should declare your intent to the compiler and other developers that read your code.</span></span> <span data-ttu-id="33e9b-129">Al declarar su intención, el compilador le informa de cuándo escribe código que no es coherente con esa intención.</span><span class="sxs-lookup"><span data-stu-id="33e9b-129">By declaring your intent, the compiler informs you when you write code that is inconsistent with that intent.</span></span>

<span data-ttu-id="33e9b-130">Un **tipo de referencia que acepta valores NULL** se anota con la misma sintaxis que los [tipos de valor que aceptan valores NULL](language-reference/builtin-types/nullable-value-types.md): se agrega `?` junto al tipo de la variable.</span><span class="sxs-lookup"><span data-stu-id="33e9b-130">A **nullable reference type** is noted using the same syntax as [nullable value types](language-reference/builtin-types/nullable-value-types.md): a `?` is appended to the type of the variable.</span></span> <span data-ttu-id="33e9b-131">Por ejemplo, la siguiente declaración de variable representa una variable de cadena que acepta valores NULL, `name`:</span><span class="sxs-lookup"><span data-stu-id="33e9b-131">For example, the following variable declaration represents a nullable string variable, `name`:</span></span>

```csharp
string? name;
```

<span data-ttu-id="33e9b-132">Cualquier variable en la que `?` no se anexe al nombre de tipo es un **tipo de referencia que no acepta valores NULL**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-132">Any variable where the `?` isn't appended to the type name is a **non-nullable reference type**.</span></span> <span data-ttu-id="33e9b-133">Esto incluye todas las variables de tipo de referencia en el código existente en el momento en el que se habilita esta característica.</span><span class="sxs-lookup"><span data-stu-id="33e9b-133">That includes all reference type variables in existing code when you've enabled this feature.</span></span>

<span data-ttu-id="33e9b-134">El compilador usa el análisis estático para determinar si se sabe si una referencia que acepta valores NULL no tiene este tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="33e9b-134">The compiler uses static analysis to determine if a nullable reference is known to be non-null.</span></span> <span data-ttu-id="33e9b-135">Si desreferencia una referencia que acepta valores NULL cuando esta puede ser NULL, el compilador genera una advertencia.</span><span class="sxs-lookup"><span data-stu-id="33e9b-135">The compiler warns you if you dereference a nullable reference when it may be null.</span></span> <span data-ttu-id="33e9b-136">Puede invalidar este comportamiento con el [operador de limitación de advertencias de valores NULL](language-reference/operators/null-forgiving.md)`!` después del nombre de una variable.</span><span class="sxs-lookup"><span data-stu-id="33e9b-136">You can override this behavior by using the [null-forgiving operator](language-reference/operators/null-forgiving.md) `!` following a variable name.</span></span> <span data-ttu-id="33e9b-137">Por ejemplo, si sabe que la variable `name` no es NULL, pero el compilador genera una advertencia, puede escribir el código siguiente para invalidar el análisis del compilador:</span><span class="sxs-lookup"><span data-stu-id="33e9b-137">For example, if you know the `name` variable isn't null but the compiler issues a warning, you can write the following code to override the compiler's analysis:</span></span>

```csharp
name!.Length;
```

## <a name="nullability-of-types"></a><span data-ttu-id="33e9b-138">Nulabilidad de tipos</span><span class="sxs-lookup"><span data-stu-id="33e9b-138">Nullability of types</span></span>

<span data-ttu-id="33e9b-139">Cualquier tipo de referencia puede tener una de cuatro *nulabilidades*, que describen cuándo se generan las advertencias:</span><span class="sxs-lookup"><span data-stu-id="33e9b-139">Any reference type can have one of four *nullabilities*, which describes when warnings are generated:</span></span>

- <span data-ttu-id="33e9b-140">*No acepta valores NULL*: no se pueden asignar valores NULL a las variables de este tipo.</span><span class="sxs-lookup"><span data-stu-id="33e9b-140">*Nonnullable*: Null can't be assigned to variables of this type.</span></span> <span data-ttu-id="33e9b-141">No es necesario comprobar si estas tienen un valor NULL antes de desreferenciarlas.</span><span class="sxs-lookup"><span data-stu-id="33e9b-141">Variables of this type don't need to be null-checked before dereferencing.</span></span>
- <span data-ttu-id="33e9b-142">*Acepta valores NULL*: se pueden asignar valores NULL a las variables de este tipo.</span><span class="sxs-lookup"><span data-stu-id="33e9b-142">*Nullable*: Null can be assigned to variables of this type.</span></span> <span data-ttu-id="33e9b-143">Si se desreferencian sin comprobar primero la existencia de valores `null`, se producirá una advertencia.</span><span class="sxs-lookup"><span data-stu-id="33e9b-143">Dereferencing variables of this type without first checking for `null` causes a warning.</span></span>
- <span data-ttu-id="33e9b-144">*Inconsciente*: se trata del estado previo a C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="33e9b-144">*Oblivious*: Oblivious is the pre-C# 8.0 state.</span></span> <span data-ttu-id="33e9b-145">Las variables de este tipo se pueden desreferenciar o asignar sin advertencias.</span><span class="sxs-lookup"><span data-stu-id="33e9b-145">Variables of this type can be dereferenced or assigned without warnings.</span></span>
- <span data-ttu-id="33e9b-146">*Desconocido*: este es generalmente el caso de los parámetros de tipo en los que las restricciones no indican al compilador que el tipo debe *aceptar valores NULL* o *no aceptar valores NULL*.</span><span class="sxs-lookup"><span data-stu-id="33e9b-146">*Unknown*: Unknown is generally for type parameters where constraints don't tell the compiler that the type must be *nullable* or *nonnullable*.</span></span>

<span data-ttu-id="33e9b-147">La nulabilidad de un tipo en una declaración de variable se controla mediante el *contexto que acepta valores NULL* en el que se declara la variable.</span><span class="sxs-lookup"><span data-stu-id="33e9b-147">The nullability of a type in a variable declaration is controlled by the *nullable context* in which the variable is declared.</span></span>

## <a name="nullable-contexts"></a><span data-ttu-id="33e9b-148">Contextos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="33e9b-148">Nullable contexts</span></span>

<span data-ttu-id="33e9b-149">Los contextos que aceptan valores NULL permiten un control preciso sobre cómo interpreta el compilador las variables de tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="33e9b-149">Nullable contexts enable fine-grained control for how the compiler interprets reference type variables.</span></span> <span data-ttu-id="33e9b-150">El **contexto de anotación que acepta valores NULL** de cualquier línea de origen está habilitado o deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="33e9b-150">The **nullable annotation context** of any given source line is either enabled or disabled.</span></span> <span data-ttu-id="33e9b-151">Puede considerar que el compilador anterior al de C# 8.0 compilaba todo el código con el contexto que acepta valores NULL deshabilitado: cualquier tipo de referencia puede tener el valor NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-151">You can think of the pre-C# 8.0 compiler as compiling all your code in a disabled nullable context: any reference type may be null.</span></span> <span data-ttu-id="33e9b-152">El **contexto de advertencia que acepta valores NULL** también se puede habilitar o deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="33e9b-152">The **nullable warnings context** may also be enabled or disabled.</span></span> <span data-ttu-id="33e9b-153">Este contexto especifica las advertencias que genera el compilador usando el análisis de flujos.</span><span class="sxs-lookup"><span data-stu-id="33e9b-153">The nullable warnings context specifies the warnings generated by the compiler using its flow analysis.</span></span>

<span data-ttu-id="33e9b-154">Tanto el contexto de anotación que acepta valores NULL como el contexto de advertencia que acepta valores NULL pueden establecerse para un proyecto con el elemento `Nullable` del archivo *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="33e9b-154">The nullable annotation context and nullable warning context can be set for a project using the `Nullable` element in your *.csproj* file.</span></span> <span data-ttu-id="33e9b-155">Este elemento configura la forma en la que el compilador interpreta la nulabilidad de los tipos y las advertencias que se generan.</span><span class="sxs-lookup"><span data-stu-id="33e9b-155">This element configures how the compiler interprets the nullability of types and what warnings are generated.</span></span> <span data-ttu-id="33e9b-156">Estos son los valores válidos:</span><span class="sxs-lookup"><span data-stu-id="33e9b-156">Valid settings are:</span></span>

- <span data-ttu-id="33e9b-157">`enable`: el contexto de anotación que acepta valores NULL es **enabled**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-157">`enable`: The nullable annotation context is **enabled**.</span></span> <span data-ttu-id="33e9b-158">El contexto de advertencia que acepta valores NULL es **enabled**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-158">The nullable warning context is **enabled**.</span></span>
  - <span data-ttu-id="33e9b-159">Las variables de un tipo de referencia, como `string`, no aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-159">Variables of a reference type, `string` for example, are non-nullable.</span></span>  <span data-ttu-id="33e9b-160">Todas las advertencias de nulabilidad están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="33e9b-160">All nullability warnings are enabled.</span></span>
- <span data-ttu-id="33e9b-161">`warnings`: el contexto de anotación que acepta valores NULL es **disabled**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-161">`warnings`: The nullable annotation context is **disabled**.</span></span> <span data-ttu-id="33e9b-162">El contexto de advertencia que acepta valores NULL es **enabled**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-162">The nullable warning context is **enabled**.</span></span>
  - <span data-ttu-id="33e9b-163">Las variables de un tipo de referencia son inconscientes.</span><span class="sxs-lookup"><span data-stu-id="33e9b-163">Variables of a reference type are oblivious.</span></span> <span data-ttu-id="33e9b-164">Todas las advertencias de nulabilidad están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="33e9b-164">All nullability warnings are enabled.</span></span>
- <span data-ttu-id="33e9b-165">`annotations`: el contexto de anotación que acepta valores NULL es **enabled**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-165">`annotations`: The nullable annotation context is **enabled**.</span></span> <span data-ttu-id="33e9b-166">el contexto de advertencia que acepta valores NULL es **disabled**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-166">The nullable warning context is **disabled**.</span></span>
  - <span data-ttu-id="33e9b-167">Las variables de un tipo de referencia, como cadena, no admiten un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-167">Variables of a reference type, string for example, are non-nullable.</span></span> <span data-ttu-id="33e9b-168">Todas las advertencias de nulabilidad están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="33e9b-168">All nullability warnings are disabled.</span></span>
- <span data-ttu-id="33e9b-169">`disable`: el contexto de anotación que acepta valores NULL es **disabled**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-169">`disable`: The nullable annotation context is **disabled**.</span></span> <span data-ttu-id="33e9b-170">el contexto de advertencia que acepta valores NULL es **disabled**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-170">The nullable warning context is **disabled**.</span></span>
  - <span data-ttu-id="33e9b-171">Las variables de tipo de referencia son inconscientes, como en versiones anteriores de C#.</span><span class="sxs-lookup"><span data-stu-id="33e9b-171">Variables of a reference type are oblivious, just like earlier versions of C#.</span></span> <span data-ttu-id="33e9b-172">Todas las advertencias de nulabilidad están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="33e9b-172">All nullability warnings are disabled.</span></span>

<span data-ttu-id="33e9b-173">**Ejemplo**:</span><span class="sxs-lookup"><span data-stu-id="33e9b-173">**Example**:</span></span>

```xml
<Nullable>enable</Nullable>
```

<span data-ttu-id="33e9b-174">También puede usar directivas para establecer los mismos contextos en cualquier lugar del proyecto:</span><span class="sxs-lookup"><span data-stu-id="33e9b-174">You can also use directives to set these same contexts anywhere in your project:</span></span>

- <span data-ttu-id="33e9b-175">`#nullable enable`: establece el contexto de anotación que acepta valores NULL y el contexto de advertencia que acepta valores NULL en **enabled**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-175">`#nullable enable`: Sets the nullable annotation context and nullable warning context to **enabled**.</span></span>
- <span data-ttu-id="33e9b-176">`#nullable disable`: establece el contexto de anotación que acepta valores NULL y el contexto de advertencia que acepta valores NULL en **disabled**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-176">`#nullable disable`: Sets the nullable annotation context and nullable warning context to **disabled**.</span></span>
- <span data-ttu-id="33e9b-177">`#nullable restore`: restaura el contexto de anotación que acepta valores NULL y el contexto de advertencia que acepta valores NULL según la configuración del proyecto.</span><span class="sxs-lookup"><span data-stu-id="33e9b-177">`#nullable restore`: Restores the nullable annotation context and nullable warning context to the project settings.</span></span>
- <span data-ttu-id="33e9b-178">`#nullable disable warnings`: establece el contexto de advertencia que acepta valores NULL en **disabled**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-178">`#nullable disable warnings`: Set the nullable warning context to **disabled**.</span></span>
- <span data-ttu-id="33e9b-179">`#nullable enable warnings`: establece el contexto de advertencia que acepta valores NULL en **enabled**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-179">`#nullable enable warnings`: Set the nullable warning context to **enabled**.</span></span>
- <span data-ttu-id="33e9b-180">`#nullable restore warnings`: restaura el contexto de advertencia que acepta valores NULL según la configuración del proyecto.</span><span class="sxs-lookup"><span data-stu-id="33e9b-180">`#nullable restore warnings`: Restores the nullable warning context to the project settings.</span></span>
- <span data-ttu-id="33e9b-181">`#nullable disable annotations`: establezca el contexto de anotación que admite un valor NULL en **disabled**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-181">`#nullable disable annotations`: Set the nullable annotation context to **disabled**.</span></span>
- <span data-ttu-id="33e9b-182">`#nullable enable annotations`: establezca el contexto de anotación que admite un valor NULL en **enabled**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-182">`#nullable enable annotations`: Set the nullable annotation context to **enabled**.</span></span>
- <span data-ttu-id="33e9b-183">`#nullable restore annotations`: restaura el contexto de advertencia de anotación según la configuración del proyecto.</span><span class="sxs-lookup"><span data-stu-id="33e9b-183">`#nullable restore annotations`: Restores the annotation warning context to the project settings.</span></span>

<span data-ttu-id="33e9b-184">De forma predeterminada, los contextos de advertencias y anotaciones que aceptan valores NULL están **deshabilitados**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-184">By default, nullable annotation and warning contexts are **disabled**, including new projects.</span></span> <span data-ttu-id="33e9b-185">Esto implica que el código existente se compila sin cambios y sin generar ninguna advertencia nueva.</span><span class="sxs-lookup"><span data-stu-id="33e9b-185">That means that your existing code compiles without changes and without generating any new warnings.</span></span>

<span data-ttu-id="33e9b-186">Estas opciones proporcionan dos estrategias distintas para [actualizar un código base existente](nullable-migration-strategies.md) para usar tipos de referencia que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-186">These options provide two distinct strategies to [update an existing codebase](nullable-migration-strategies.md) to use nullable reference types.</span></span>

## <a name="nullable-annotation-context"></a><span data-ttu-id="33e9b-187">Contexto de anotación que admite valores NULL</span><span class="sxs-lookup"><span data-stu-id="33e9b-187">Nullable annotation context</span></span>

<span data-ttu-id="33e9b-188">El compilador usa las siguientes reglas en un contexto de anotación deshabilitado que acepta valores NULL:</span><span class="sxs-lookup"><span data-stu-id="33e9b-188">The compiler uses the following rules in a disabled nullable annotation context:</span></span>

- <span data-ttu-id="33e9b-189">No se pueden declarar referencias que aceptan valores NULL en un contexto deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="33e9b-189">You can't declare nullable references in a disabled context.</span></span>
- <span data-ttu-id="33e9b-190">Todas las variables de referencia se pueden asignar a un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-190">All reference variables may be assigned a value of null.</span></span>
- <span data-ttu-id="33e9b-191">No se genera ninguna advertencia al desreferenciar una variable de un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="33e9b-191">No warnings are generated when a variable of a reference type is dereferenced.</span></span>
- <span data-ttu-id="33e9b-192">El operador de limitación de advertencias de valores NULL no se puede usar en un contexto deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="33e9b-192">The null-forgiving operator may not be used in a disabled context.</span></span>

<span data-ttu-id="33e9b-193">El comportamiento es el mismo que en versiones anteriores de C#.</span><span class="sxs-lookup"><span data-stu-id="33e9b-193">The behavior is the same as previous versions of C#.</span></span>

<span data-ttu-id="33e9b-194">El compilador usa las siguientes reglas en un contexto de anotación habilitado que acepta valores NULL:</span><span class="sxs-lookup"><span data-stu-id="33e9b-194">The compiler uses the following rules in an enabled nullable annotation context:</span></span>

- <span data-ttu-id="33e9b-195">Todas las variables de tipo de referencia son **referencias que no aceptan valores NULL**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-195">Any variable of a reference type is a **non-nullable reference**.</span></span>
- <span data-ttu-id="33e9b-196">Estas referencias se pueden desreferenciar sin problemas.</span><span class="sxs-lookup"><span data-stu-id="33e9b-196">Any non-nullable reference may be dereferenced safely.</span></span>
- <span data-ttu-id="33e9b-197">Todos los tipos de referencia que aceptan valores NULL (con la anotación de `?` después del tipo en la declaración de la variable) pueden ser NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-197">Any nullable reference type (noted by `?` after the type in the variable declaration) may be null.</span></span> <span data-ttu-id="33e9b-198">El análisis estático determina si se sabe que el valor no admite valores NULL cuando se desreferencia.</span><span class="sxs-lookup"><span data-stu-id="33e9b-198">Static analysis determines if the value is known to be non-null when it's dereferenced.</span></span> <span data-ttu-id="33e9b-199">Si no, el compilador emite una advertencia.</span><span class="sxs-lookup"><span data-stu-id="33e9b-199">If not, the compiler warns you.</span></span>
- <span data-ttu-id="33e9b-200">Puede usar el operador de limitación de advertencias de valores NULL para declarar que una referencia que acepta valores NULL no tiene un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-200">You can use the null-forgiving operator to declare that a nullable reference isn't null.</span></span>

<span data-ttu-id="33e9b-201">En un contexto de anotación que acepta valores NULL, el carácter `?` junto a un tipo de referencia declara un **tipo de referencia que acepta valores NULL**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-201">In an enabled nullable annotation context, the `?` character appended to a reference type declares a **nullable reference type**.</span></span> <span data-ttu-id="33e9b-202">Se puede incorporar un **operador de limitación de advertencias de valores NULL**`!` junto a una expresión para declarar que no tiene un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-202">The **null-forgiving operator** `!` may be appended to an expression to declare that the expression isn't null.</span></span>

## <a name="nullable-warning-context"></a><span data-ttu-id="33e9b-203">Contexto de advertencia que acepta valores NULL</span><span class="sxs-lookup"><span data-stu-id="33e9b-203">Nullable warning context</span></span>

<span data-ttu-id="33e9b-204">El contexto de advertencia que acepta valores NULL no es igual al contexto de anotación que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-204">The nullable warning context is distinct from the nullable annotation context.</span></span> <span data-ttu-id="33e9b-205">Se pueden habilitar las advertencias incluso aunque las nuevas anotaciones estén deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="33e9b-205">Warnings can be enabled even when the new annotations are disabled.</span></span> <span data-ttu-id="33e9b-206">El compilador usa el análisis de flujos estático para determinar el **estado NULL** de cualquier referencia.</span><span class="sxs-lookup"><span data-stu-id="33e9b-206">The compiler uses static flow analysis to determine the **null state** of any reference.</span></span> <span data-ttu-id="33e9b-207">El estado NULL puede ser **no NULL** o **quizás NULL** cuando el *contexto de advertencia que acepta valores NULL* no está **deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="33e9b-207">The null state is either **not null** or **maybe null** when the *nullable warning context* isn't **disabled**.</span></span> <span data-ttu-id="33e9b-208">Si desreferencia una referencia cuando el compilador ha determinado el estado **quizás NULL**, el compilador emite una advertencia.</span><span class="sxs-lookup"><span data-stu-id="33e9b-208">If you dereference a reference when the compiler has determined it's **maybe null**, the compiler warns you.</span></span> <span data-ttu-id="33e9b-209">El estado de una referencia es **quizás NULL** a menos que el compilador pueda determinar una de estas dos condiciones:</span><span class="sxs-lookup"><span data-stu-id="33e9b-209">The state of a reference is **maybe null** unless the compiler can determine one of two conditions:</span></span>

1. <span data-ttu-id="33e9b-210">La variable se ha asignado definitivamente a un valor distinto a NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-210">The variable has been definitely assigned to a non-null value.</span></span>
1. <span data-ttu-id="33e9b-211">Se ha comprobado que la variable o la expresión no tiene un valor NULL antes de desreferenciarla.</span><span class="sxs-lookup"><span data-stu-id="33e9b-211">The variable or expression has been checked against null before de-referencing it.</span></span>

<span data-ttu-id="33e9b-212">El compilador genera advertencias cuando se desreferencia una variable o expresión que tiene un estado **quizás NULL** en un contexto de advertencia que admite valores NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-212">The compiler generates warnings when you dereference a variable or expression that is **maybe null** in a nullable warning context.</span></span> <span data-ttu-id="33e9b-213">Además, el compilador genera advertencias cuando se asigna una variable o expresión **quizás NULL** a un tipo de referencia que no acepta valores NULL en un contexto de anotación que sí los acepta.</span><span class="sxs-lookup"><span data-stu-id="33e9b-213">Furthermore, the compiler generates warnings when a nonnullable reference type is assigned to a **maybe null** variable or expression in an enabled nullable annotation context.</span></span>

## <a name="attributes-describe-apis"></a><span data-ttu-id="33e9b-214">Atributos que describen las API</span><span class="sxs-lookup"><span data-stu-id="33e9b-214">Attributes describe APIs</span></span>

<span data-ttu-id="33e9b-215">Agregue atributos a las API que proporcionen al compilador más información sobre cuándo los argumentos o valores devueltos pueden admitir o no valores NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-215">You add attributes to APIs that provide the compiler more information about when arguments or return values can or can't be null.</span></span> <span data-ttu-id="33e9b-216">Puede obtener más información sobre estos atributos en nuestro artículo de la referencia del lenguaje que trata de los [atributos que admiten valores NULL](language-reference/attributes/nullable-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="33e9b-216">You can learn more about these attributes in our article in the language reference covering the [nullable attributes](language-reference/attributes/nullable-analysis.md).</span></span> <span data-ttu-id="33e9b-217">Estos atributos se agregan a las bibliotecas de .NET a través de las versiones actuales y futuras.</span><span class="sxs-lookup"><span data-stu-id="33e9b-217">These attributes are being added to .NET libraries over current and upcoming releases.</span></span> <span data-ttu-id="33e9b-218">Las API que se usan más a menudo se actualizan primero.</span><span class="sxs-lookup"><span data-stu-id="33e9b-218">The most commonly used APIs are being updated first.</span></span>

## <a name="known-pitfalls"></a><span data-ttu-id="33e9b-219">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="33e9b-219">Known pitfalls</span></span>

<span data-ttu-id="33e9b-220">Las matrices y las estructuras que contienen tipos de referencia son problemas conocidos de la característica de tipos de referencia que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-220">Arrays and structs that contain reference types are known pitfalls in nullable reference types feature.</span></span>

### <a name="structs"></a><span data-ttu-id="33e9b-221">Estructuras</span><span class="sxs-lookup"><span data-stu-id="33e9b-221">Structs</span></span>

<span data-ttu-id="33e9b-222">Una estructura que contiene tipos de referencia que no aceptan valores NULL permite asignarle `default` sin ninguna advertencia.</span><span class="sxs-lookup"><span data-stu-id="33e9b-222">A struct that contains non-nullable reference types allows assigning `default` for it without any warnings.</span></span> <span data-ttu-id="33e9b-223">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="33e9b-223">Consider the following example:</span></span>

```csharp
using System;

#nullable enable

public struct Student
{
    public string FirstName;
    public string? MiddleName;
    public string LastName;
}

public static class Program
{
    public static void PrintStudent(Student student)
    {
        Console.WriteLine($"First name: {student.FirstName.ToUpper()}");
        Console.WriteLine($"Middle name: {student.MiddleName.ToUpper()}");
        Console.WriteLine($"Last name: {student.LastName.ToUpper()}");
    }

    public static void Main() => PrintStudent(default);
}
```

<span data-ttu-id="33e9b-224">En el ejemplo anterior, no hay ninguna advertencia en `PrintStudent(default)` mientras que los tipos de referencia que no aceptan valores NULL `FirstName` y `LastName` son NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-224">In the preceding example, there is no warning in `PrintStudent(default)` while the non-nullable reference types `FirstName` and `LastName` are null.</span></span>

<span data-ttu-id="33e9b-225">Otro caso más común es cuando se trata de estructuras genéricas.</span><span class="sxs-lookup"><span data-stu-id="33e9b-225">Another more common case is when you deal with generic structs.</span></span> <span data-ttu-id="33e9b-226">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="33e9b-226">Consider the following example:</span></span>

```csharp
#nullable enable

public struct Foo<T>
{
    public T Bar { get; set; }
}

public static class Program
{
    public static void Main()
    {
        string s = default(Foo<string>).Bar;
    }
}
```

<span data-ttu-id="33e9b-227">En el ejemplo anterior, la propiedad `Bar` será `null` en tiempo de ejecución y se asigna a una cadena que no acepta valores NULL sin ninguna advertencia.</span><span class="sxs-lookup"><span data-stu-id="33e9b-227">In the preceding example, the property `Bar` is going to be `null` at runtime, and it's assigned to non-nullable string without any warnings.</span></span>

### <a name="arrays"></a><span data-ttu-id="33e9b-228">Matrices</span><span class="sxs-lookup"><span data-stu-id="33e9b-228">Arrays</span></span>

<span data-ttu-id="33e9b-229">Las matrices también son un problema conocido en los tipos de referencia que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-229">Arrays are also a known pitfall in nullable reference types.</span></span> <span data-ttu-id="33e9b-230">Considere el ejemplo siguiente, que no genera ninguna advertencia:</span><span class="sxs-lookup"><span data-stu-id="33e9b-230">Consider the following example which doesn't produce any warnings:</span></span>

```csharp
using System;

#nullable enable

public static class Program
{
    public static void Main()
    {
        string[] values = new string[10];
        string s = values[0];
        Console.WriteLine(s.ToUpper());
    }
}
```

<span data-ttu-id="33e9b-231">En el ejemplo anterior, la declaración de la matriz muestra que contiene cadenas que no aceptan valores NULL, mientras que todos sus elementos se inicializan en NULL.</span><span class="sxs-lookup"><span data-stu-id="33e9b-231">In the preceding example, the declaration of the array shows it holds non-nullable strings, while its elements are all initialized to null.</span></span> <span data-ttu-id="33e9b-232">Después, a la variable `s` se le asigna un valor NULL (el primer elemento de la matriz).</span><span class="sxs-lookup"><span data-stu-id="33e9b-232">Then, the variable `s` is assigned a null value (the first element of the array).</span></span> <span data-ttu-id="33e9b-233">Por último, se desreferencia la variable `s`, lo que genera una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="33e9b-233">Finally, the variable `s` is dereferenced causing a runtime exception.</span></span>

## <a name="see-also"></a><span data-ttu-id="33e9b-234">Vea también</span><span class="sxs-lookup"><span data-stu-id="33e9b-234">See also</span></span>

- [<span data-ttu-id="33e9b-235">Borrador de especificación de tipos de referencia que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="33e9b-235">Draft nullable reference types specification</span></span>](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md)
- [<span data-ttu-id="33e9b-236">Tutorial de introducción a las referencias que no aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="33e9b-236">Intro to nullable references tutorial</span></span>](tutorials/nullable-reference-types.md)
- [<span data-ttu-id="33e9b-237">Migración de un código base existente a referencias que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="33e9b-237">Migrate an existing codebase to nullable references</span></span>](tutorials/upgrade-to-nullable-references.md)
- [<span data-ttu-id="33e9b-238">-nullable (opción del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="33e9b-238">-nullable (C# Compiler option)</span></span>](language-reference/compiler-options/nullable-compiler-option.md)
