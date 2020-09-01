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
ms.openlocfilehash: f9c6c204d2563865f741c6ddb4644eb56f956c12
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125051"
---
# <a name="-nullable-c-compiler-options"></a><span data-ttu-id="fa618-103">-nullable (opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="fa618-103">-nullable (C# Compiler Options)</span></span>

<span data-ttu-id="fa618-104">La opción **-nullable** le permite especificar el contexto que admite un valor NULL que quiera.</span><span class="sxs-lookup"><span data-stu-id="fa618-104">The **-nullable** option lets you specify the desired nullable context.</span></span>

## <a name="syntax"></a><span data-ttu-id="fa618-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa618-105">Syntax</span></span>

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a><span data-ttu-id="fa618-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="fa618-106">Arguments</span></span>

<span data-ttu-id="fa618-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="fa618-107">`+` &#124; `-`</span></span>  
<span data-ttu-id="fa618-108">Si se especifica `+`, o simplemente **-nullable**, el compilador habilitará el contexto que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="fa618-108">Specifying `+`, or just **-nullable**, causes the compiler to enable nullable context.</span></span> <span data-ttu-id="fa618-109">Si se especifica `-`, que se aplica si no se especifica **-nullable**, se deshabilita el contexto que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="fa618-109">Specifying `-`, which is in effect if you do not specify **-nullable**, disables nullable context.</span></span>

<span data-ttu-id="fa618-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span><span class="sxs-lookup"><span data-stu-id="fa618-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span></span>  
<span data-ttu-id="fa618-111">Especifica la opción de contexto que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="fa618-111">Specifies the nullable context option.</span></span> <span data-ttu-id="fa618-112">Es similar a `+` o `-` en cuanto a habilitación y deshabilitación, pero permite una mayor granularidad de la especificidad del contexto que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="fa618-112">Similar to `+` or `-`, to enable and disable, but allows for more granularity of nullable context specificity.</span></span> <span data-ttu-id="fa618-113">El argumento `enable`, que se aplica del mismo modo que al especificar **-nullable**, habilita el contexto que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="fa618-113">The `enable` argument, which is in effect the same as if you specify **-nullable**, enables the nullable context.</span></span> <span data-ttu-id="fa618-114">Si se especifica `disable`, se deshabilitará el contexto que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="fa618-114">Specifying `disable` will disable nullable context.</span></span> <span data-ttu-id="fa618-115">Al proporcionar el argumento `warnings`, **-nullable:warnings**, se habilita el contexto de advertencia que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="fa618-115">When providing the `warnings` argument, **-nullable:warnings**, the nullable warning context is enabled.</span></span> <span data-ttu-id="fa618-116">Al especificar el argumento `annotations`, **-nullable:warnings**, se habilita el contexto de anotación que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="fa618-116">When specifying the `annotations` argument, **-nullable:annotations**, the nullable annotation context is enabled.</span></span>

## <a name="remarks"></a><span data-ttu-id="fa618-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fa618-117">Remarks</span></span>

<span data-ttu-id="fa618-118">El análisis de flujo se utiliza para inferir la nulabilidad de las variables del código ejecutable.</span><span class="sxs-lookup"><span data-stu-id="fa618-118">Flow analysis is used to infer the nullability of variables within executable code.</span></span> <span data-ttu-id="fa618-119">La nulabilidad inferida de una variable es independiente de la nulabilidad declarada de dicha variable.</span><span class="sxs-lookup"><span data-stu-id="fa618-119">The inferred nullability of a variable is independent of the variable's declared nullability.</span></span> <span data-ttu-id="fa618-120">Las llamadas de métodos se analizan incluso cuando se omiten de forma condicional.</span><span class="sxs-lookup"><span data-stu-id="fa618-120">Method calls are analyzed even when they are conditionally omitted.</span></span> <span data-ttu-id="fa618-121">Es el caso de <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> en modo de versión.</span><span class="sxs-lookup"><span data-stu-id="fa618-121">For instance, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in release mode.</span></span>

<span data-ttu-id="fa618-122">La invocación de métodos anotados con los siguientes atributos también afectará al análisis de flujo:</span><span class="sxs-lookup"><span data-stu-id="fa618-122">Invocation of methods annotated with the following attributes will also affect flow analysis:</span></span>

- <span data-ttu-id="fa618-123">Condiciones previas simples: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> y <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span><span class="sxs-lookup"><span data-stu-id="fa618-123">Simple pre-conditions: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span></span>
- <span data-ttu-id="fa618-124">Condiciones posteriores simples: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> y <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span><span class="sxs-lookup"><span data-stu-id="fa618-124">Simple post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span></span>
- <span data-ttu-id="fa618-125">Condiciones posteriores condicionales: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> y <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span><span class="sxs-lookup"><span data-stu-id="fa618-125">Conditional post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span></span>
- <span data-ttu-id="fa618-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (por ejemplo, `DoesNotReturnIf(false)` para <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) y <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span><span class="sxs-lookup"><span data-stu-id="fa618-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (for example, `DoesNotReturnIf(false)` for <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) and <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span></span>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- <span data-ttu-id="fa618-127">Condiciones posteriores de miembros: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> y <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span><span class="sxs-lookup"><span data-stu-id="fa618-127">Member post-conditions: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> and <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span></span>

### <a name="to-set-this-compiler-option-in-a-project"></a><span data-ttu-id="fa618-128">Cómo establecer esta opción del compilador en un proyecto</span><span class="sxs-lookup"><span data-stu-id="fa618-128">To set this compiler option in a project</span></span>

<span data-ttu-id="fa618-129">Edite el archivo *.csproj* para agregar la etiqueta `<Nullable>` dentro de una jerarquía `Project/PropertyGroup`:</span><span class="sxs-lookup"><span data-stu-id="fa618-129">Edit the *.csproj* file to add the `<Nullable>` tag within a `Project/PropertyGroup` hierarchy:</span></span>

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a><span data-ttu-id="fa618-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa618-130">See also</span></span>

- [<span data-ttu-id="fa618-131">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="fa618-131">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="fa618-132">Tipos de referencia que aceptan valores null</span><span class="sxs-lookup"><span data-stu-id="fa618-132">Nullable reference types</span></span>](../../nullable-references.md)
