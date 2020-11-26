---
description: -nullable (opciones del compilador de C#)
title: -nullable (opciones del compilador de C#)
author: IEvangelist
ms.author: dapine
ms.date: 06/04/2020
f1_keywords:
- /nullable
helpviewer_keywords:
- nullable compiler option [C#]
- /nullable compiler option [C#]
- -nullable compiler option [C#]
ms.openlocfilehash: 68857d0cb4d0cd1177506e0b7ce897d2cfc3aa5b
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099229"
---
# <a name="-nullable-c-compiler-options"></a><span data-ttu-id="5f051-103">-nullable (opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="5f051-103">-nullable (C# Compiler Options)</span></span>

<span data-ttu-id="5f051-104">La opción **-nullable** le permite especificar el contexto que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="5f051-104">The **-nullable** option lets you specify the nullable context.</span></span>

## <a name="syntax"></a><span data-ttu-id="5f051-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f051-105">Syntax</span></span>

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a><span data-ttu-id="5f051-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5f051-106">Arguments</span></span>

<span data-ttu-id="5f051-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="5f051-107">`+` &#124; `-`</span></span>  
<span data-ttu-id="5f051-108">Si se especifica `+`, o bien **-nullable**, el compilador habilita el contexto que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="5f051-108">Specifying `+`, or **-nullable**, causes the compiler to enable nullable context.</span></span> <span data-ttu-id="5f051-109">Si se especifica `-`, que se aplica si no se especifica **-nullable**, se deshabilita el contexto que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="5f051-109">Specifying `-`, which is in effect if you don't specify **-nullable**, disables nullable context.</span></span>

<span data-ttu-id="5f051-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span><span class="sxs-lookup"><span data-stu-id="5f051-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span></span>  
<span data-ttu-id="5f051-111">Especifica la opción de contexto que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="5f051-111">Specifies the nullable context option.</span></span> <span data-ttu-id="5f051-112">Es similar a `+` o `-` en cuanto a habilitación y deshabilitación, pero permite una mayor granularidad de la especificidad del contexto que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="5f051-112">Similar to `+` or `-`, to enable and disable, but allows for more granularity of nullable context specificity.</span></span> <span data-ttu-id="5f051-113">El argumento `enable`, que se aplica del mismo modo que al especificar **-nullable**, habilita el contexto que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="5f051-113">The `enable` argument, which is in effect the same as if you specify **-nullable**, enables the nullable context.</span></span> <span data-ttu-id="5f051-114">Si se especifica `disable`, se deshabilitará el contexto que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="5f051-114">Specifying `disable` will disable nullable context.</span></span> <span data-ttu-id="5f051-115">Al proporcionar el argumento `warnings`, **-nullable:warnings**, se habilita el contexto de advertencia que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="5f051-115">When providing the `warnings` argument, **-nullable:warnings**, the nullable warning context is enabled.</span></span> <span data-ttu-id="5f051-116">Al especificar el argumento `annotations`, **-nullable:warnings**, se habilita el contexto de anotación que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="5f051-116">When specifying the `annotations` argument, **-nullable:annotations**, the nullable annotation context is enabled.</span></span>

## <a name="remarks"></a><span data-ttu-id="5f051-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5f051-117">Remarks</span></span>

<span data-ttu-id="5f051-118">El análisis de flujo se utiliza para inferir la nulabilidad de las variables del código ejecutable.</span><span class="sxs-lookup"><span data-stu-id="5f051-118">Flow analysis is used to infer the nullability of variables within executable code.</span></span> <span data-ttu-id="5f051-119">La nulabilidad inferida de una variable es independiente de la nulabilidad declarada de dicha variable.</span><span class="sxs-lookup"><span data-stu-id="5f051-119">The inferred nullability of a variable is independent of the variable's declared nullability.</span></span> <span data-ttu-id="5f051-120">Las llamadas de método se analizan incluso cuando se omiten de forma condicional.</span><span class="sxs-lookup"><span data-stu-id="5f051-120">Method calls are analyzed even when they're conditionally omitted.</span></span> <span data-ttu-id="5f051-121">Es el caso de <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> en modo de versión.</span><span class="sxs-lookup"><span data-stu-id="5f051-121">For instance, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in release mode.</span></span>

<span data-ttu-id="5f051-122">La invocación de métodos anotados con los siguientes atributos también afectará al análisis de flujo:</span><span class="sxs-lookup"><span data-stu-id="5f051-122">Invocation of methods annotated with the following attributes will also affect flow analysis:</span></span>

- <span data-ttu-id="5f051-123">Condiciones previas simples: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> y <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span><span class="sxs-lookup"><span data-stu-id="5f051-123">Simple pre-conditions: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span></span>
- <span data-ttu-id="5f051-124">Condiciones posteriores simples: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> y <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span><span class="sxs-lookup"><span data-stu-id="5f051-124">Simple post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span></span>
- <span data-ttu-id="5f051-125">Condiciones posteriores condicionales: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> y <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span><span class="sxs-lookup"><span data-stu-id="5f051-125">Conditional post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span></span>
- <span data-ttu-id="5f051-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (por ejemplo, `DoesNotReturnIf(false)` para <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) y <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span><span class="sxs-lookup"><span data-stu-id="5f051-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (for example, `DoesNotReturnIf(false)` for <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) and <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span></span>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- <span data-ttu-id="5f051-127">Condiciones posteriores de miembros: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> y <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span><span class="sxs-lookup"><span data-stu-id="5f051-127">Member post-conditions: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> and <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f051-128">El contexto global que admite un valor NULL no se aplica a los archivos de código generado.</span><span class="sxs-lookup"><span data-stu-id="5f051-128">The global nullable context does not apply for generated code files.</span></span> <span data-ttu-id="5f051-129">Con independencia de este valor, el contexto que admite un valor NULL está *deshabilitado* para cualquier archivo de código fuente marcado como generado.</span><span class="sxs-lookup"><span data-stu-id="5f051-129">Regardless of this setting, the nullable context is *disabled* for any source file marked as generated.</span></span> <span data-ttu-id="5f051-130">Hay cuatro maneras de marcar un archivo como generado:</span><span class="sxs-lookup"><span data-stu-id="5f051-130">There are four ways a file is marked as generated:</span></span>
>
> 1. <span data-ttu-id="5f051-131">En el archivo .editorconfig, especifique `generated_code = true` en una sección que se aplique a ese archivo.</span><span class="sxs-lookup"><span data-stu-id="5f051-131">In the .editorconfig, specify `generated_code = true` in a section that applies to that file.</span></span>
> 1. <span data-ttu-id="5f051-132">Coloque `<auto-generated>` o `<auto-generated/>` en un comentario en la parte superior del archivo.</span><span class="sxs-lookup"><span data-stu-id="5f051-132">Put `<auto-generated>` or `<auto-generated/>` in a comment at the top of the file.</span></span> <span data-ttu-id="5f051-133">Puede estar en cualquier línea de ese comentario, pero el bloque de comentario debe ser el primer elemento del archivo.</span><span class="sxs-lookup"><span data-stu-id="5f051-133">It can be on any line in that comment, but the comment block must be the first element in the file.</span></span>
> 1. <span data-ttu-id="5f051-134">Inicie el nombre de archivo con *TemporaryGeneratedFile_*</span><span class="sxs-lookup"><span data-stu-id="5f051-134">Start the file name with *TemporaryGeneratedFile_*</span></span>
> 1. <span data-ttu-id="5f051-135">Finalice el nombre de archivo con *.designer.cs*, *.generated.cs*, *.g.cs* o *.g.i.cs*.</span><span class="sxs-lookup"><span data-stu-id="5f051-135">End the file name with *.designer.cs*, *.generated.cs*, *.g.cs*, or *.g.i.cs*.</span></span>
>
> <span data-ttu-id="5f051-136">Los generadores pueden optar por usar la directiva de preprocesador [`#nullable`](../preprocessor-directives/preprocessor-nullable.md).</span><span class="sxs-lookup"><span data-stu-id="5f051-136">Generators can opt-in using the [`#nullable`](../preprocessor-directives/preprocessor-nullable.md) preprocessor directive.</span></span>

### <a name="to-set-this-compiler-option-in-a-project"></a><span data-ttu-id="5f051-137">Cómo establecer esta opción del compilador en un proyecto</span><span class="sxs-lookup"><span data-stu-id="5f051-137">To set this compiler option in a project</span></span>

<span data-ttu-id="5f051-138">Edite el archivo *.csproj* para agregar la etiqueta `<Nullable>` dentro de una jerarquía `Project/PropertyGroup`:</span><span class="sxs-lookup"><span data-stu-id="5f051-138">Edit the *.csproj* file to add the `<Nullable>` tag within a `Project/PropertyGroup` hierarchy:</span></span>

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a><span data-ttu-id="5f051-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f051-139">See also</span></span>

- [<span data-ttu-id="5f051-140">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="5f051-140">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="5f051-141">Directiva de preprocesador `#nullable`</span><span class="sxs-lookup"><span data-stu-id="5f051-141">`#nullable` preprocessor directive</span></span>](../preprocessor-directives/preprocessor-nullable.md)
- [<span data-ttu-id="5f051-142">Tipos de referencia que aceptan valores null</span><span class="sxs-lookup"><span data-stu-id="5f051-142">Nullable reference types</span></span>](../../nullable-references.md)
