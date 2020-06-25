---
title: -nullable (opciones del compilador de C#)
ms.date: 06/04/2020
f1_keywords:
- /nullable
helpviewer_keywords:
- nullable compiler option [C#]
- /nullable compiler option [C#]
- -nullable compiler option [C#]
ms.openlocfilehash: 7454bb316507c3aaea208094127552712421dff6
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990125"
---
# <a name="-nullable-c-compiler-options"></a><span data-ttu-id="1d536-102">-nullable (opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="1d536-102">-nullable (C# Compiler Options)</span></span>

<span data-ttu-id="1d536-103">La opción **-nullable** le permite especificar el contexto que admite un valor NULL que quiera.</span><span class="sxs-lookup"><span data-stu-id="1d536-103">The **-nullable** option lets you specify the desired nullable context.</span></span>

## <a name="syntax"></a><span data-ttu-id="1d536-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d536-104">Syntax</span></span>

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a><span data-ttu-id="1d536-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1d536-105">Arguments</span></span>

<span data-ttu-id="1d536-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="1d536-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="1d536-107">Si se especifica `+`, o simplemente **-nullable**, el compilador habilitará el contexto que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="1d536-107">Specifying `+`, or just **-nullable**, causes the compiler to enable nullable context.</span></span> <span data-ttu-id="1d536-108">Si se especifica `-`, que se aplica si no se especifica **-nullable**, se deshabilita el contexto que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="1d536-108">Specifying `-`, which is in effect if you do not specify **-nullable**, disables nullable context.</span></span>

<span data-ttu-id="1d536-109">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span><span class="sxs-lookup"><span data-stu-id="1d536-109">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span></span>  
<span data-ttu-id="1d536-110">Especifica la opción de contexto que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="1d536-110">Specifies the nullable context option.</span></span> <span data-ttu-id="1d536-111">Es similar a `+` o `-` en cuanto a habilitación y deshabilitación, pero permite una mayor granularidad de la especificidad del contexto que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="1d536-111">Similar to `+` or `-`, to enable and disable, but allows for more granularity of nullable context specificity.</span></span> <span data-ttu-id="1d536-112">El argumento `enable`, que se aplica del mismo modo que al especificar **-nullable**, habilita el contexto que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="1d536-112">The `enable` argument, which is in effect the same as if you specify **-nullable**, enables the nullable context.</span></span> <span data-ttu-id="1d536-113">Si se especifica `disable`, se deshabilitará el contexto que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="1d536-113">Specifying `disable` will disable nullable context.</span></span> <span data-ttu-id="1d536-114">Al proporcionar el argumento `warnings`, **-nullable:warnings**, se habilita el contexto de advertencia que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="1d536-114">When providing the `warnings` argument, **-nullable:warnings**, the nullable warning context is enabled.</span></span> <span data-ttu-id="1d536-115">Al especificar el argumento `annotations`, **-nullable:warnings**, se habilita el contexto de anotación que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="1d536-115">When specifying the `annotations` argument, **-nullable:annotations**, the nullable annotation context is enabled.</span></span>

## <a name="remarks"></a><span data-ttu-id="1d536-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1d536-116">Remarks</span></span>

<span data-ttu-id="1d536-117">El análisis de flujo se utiliza para inferir la nulabilidad de las variables del código ejecutable.</span><span class="sxs-lookup"><span data-stu-id="1d536-117">Flow analysis is used to infer the nullability of variables within executable code.</span></span> <span data-ttu-id="1d536-118">La nulabilidad inferida de una variable es independiente de la nulabilidad declarada de dicha variable.</span><span class="sxs-lookup"><span data-stu-id="1d536-118">The inferred nullability of a variable is independent of the variable's declared nullability.</span></span> <span data-ttu-id="1d536-119">Las llamadas de métodos se analizan incluso cuando se omiten de forma condicional.</span><span class="sxs-lookup"><span data-stu-id="1d536-119">Method calls are analyzed even when they are conditionally omitted.</span></span> <span data-ttu-id="1d536-120">Es el caso de <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> en modo de versión.</span><span class="sxs-lookup"><span data-stu-id="1d536-120">For instance, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in release mode.</span></span>

<span data-ttu-id="1d536-121">La invocación de métodos anotados con los siguientes atributos también afectará al análisis de flujo:</span><span class="sxs-lookup"><span data-stu-id="1d536-121">Invocation of methods annotated with the following attributes will also affect flow analysis:</span></span>

- <span data-ttu-id="1d536-122">Condiciones previas simples: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> y <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span><span class="sxs-lookup"><span data-stu-id="1d536-122">Simple pre-conditions: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span></span>
- <span data-ttu-id="1d536-123">Condiciones posteriores simples: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> y <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span><span class="sxs-lookup"><span data-stu-id="1d536-123">Simple post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span></span>
- <span data-ttu-id="1d536-124">Condiciones posteriores condicionales: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> y <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span><span class="sxs-lookup"><span data-stu-id="1d536-124">Conditional post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span></span>
- <span data-ttu-id="1d536-125"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (por ejemplo, `DoesNotReturnIf(false)` para <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) y <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span><span class="sxs-lookup"><span data-stu-id="1d536-125"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (for example, `DoesNotReturnIf(false)` for <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) and <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span></span>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- <span data-ttu-id="1d536-126">Condiciones posteriores de miembros: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> y <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span><span class="sxs-lookup"><span data-stu-id="1d536-126">Member post-conditions: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> and <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span></span>

### <a name="to-set-this-compiler-option-in-a-project"></a><span data-ttu-id="1d536-127">Cómo establecer esta opción del compilador en un proyecto</span><span class="sxs-lookup"><span data-stu-id="1d536-127">To set this compiler option in a project</span></span>

<span data-ttu-id="1d536-128">Edite el archivo *.csproj* para agregar la etiqueta `<Nullable>` dentro de una jerarquía `Project/PropertyGroup`:</span><span class="sxs-lookup"><span data-stu-id="1d536-128">Edit the *.csproj* file to add the `<Nullable>` tag within a `Project/PropertyGroup` hierarchy:</span></span>

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a><span data-ttu-id="1d536-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d536-129">See also</span></span>

- [<span data-ttu-id="1d536-130">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="1d536-130">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="1d536-131">Tipos de referencia que aceptan valores null</span><span class="sxs-lookup"><span data-stu-id="1d536-131">Nullable reference types</span></span>](../../nullable-references.md)
