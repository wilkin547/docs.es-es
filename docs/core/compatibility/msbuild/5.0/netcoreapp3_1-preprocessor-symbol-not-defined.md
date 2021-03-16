---
title: 'Cambio importante: Símbolo de preprocesador de NETCOREAPP3_1 no definido al establecer .NET 5 como destino'
description: Obtenga información sobre el cambio importante en .NET 5 por el que los proyectos ya no definen símbolos de preprocesador para versiones anteriores.
ms.date: 09/17/2020
ms.openlocfilehash: 390c8f5af97510db4652f3f42db577e6de158020
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256535"
---
# <a name="netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5"></a><span data-ttu-id="2863f-103">Símbolo de preprocesador de NETCOREAPP3_1 no definido al establecer .NET 5 como destino</span><span class="sxs-lookup"><span data-stu-id="2863f-103">NETCOREAPP3_1 preprocessor symbol is not defined when targeting .NET 5</span></span>

<span data-ttu-id="2863f-104">En .NET 5 RC2 y versiones posteriores, los proyectos ya no definen símbolos de preprocesador para versiones anteriores, sino solo la versión que tienen establecida como destino.</span><span class="sxs-lookup"><span data-stu-id="2863f-104">In .NET 5 RC2 and later versions, projects no longer define preprocessor symbols for earlier versions, but only for the version that they target.</span></span> <span data-ttu-id="2863f-105">Este comportamiento es el mismo que el de .NET Core 1.0 - 3.1.</span><span class="sxs-lookup"><span data-stu-id="2863f-105">This is the same behavior as .NET Core 1.0 - 3.1.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="2863f-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="2863f-106">Version introduced</span></span>

<span data-ttu-id="2863f-107">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="2863f-107">5.0 RC2</span></span>

## <a name="change-description"></a><span data-ttu-id="2863f-108">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="2863f-108">Change description</span></span>

<span data-ttu-id="2863f-109">En la versión preliminar 7 de .NET 5, hasta RC1, los proyectos que tienen `net5.0` como destino definen los dos símbolos de preprocesador `NETCOREAPP3_1` y `NET5_0`.</span><span class="sxs-lookup"><span data-stu-id="2863f-109">In .NET 5 preview 7 through RC1, projects that target `net5.0` define both `NETCOREAPP3_1` and `NET5_0` preprocessor symbols.</span></span> <span data-ttu-id="2863f-110">La intención de aplicar este cambio de comportamiento era que, a partir de .NET 5, los [símbolos de compilación condicional fuesen acumulativos](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).</span><span class="sxs-lookup"><span data-stu-id="2863f-110">The intent behind this behavior change was that starting with .NET 5, conditional compilation [symbols would be cumulative](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).</span></span>

<span data-ttu-id="2863f-111">En .NET 5 RC2 y versiones posteriores, los proyectos solo definen símbolos para los monikers de la plataforma de destino (TFM) que tiene como destino y no para ninguna versión anterior.</span><span class="sxs-lookup"><span data-stu-id="2863f-111">In .NET 5 RC2 and later, projects only define symbols for the target framework monikers (TFM) that it targets and not for any earlier versions.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="2863f-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="2863f-112">Reason for change</span></span>

<span data-ttu-id="2863f-113">El cambio aplicado en la versión preliminar 7 se ha revertido debido a los comentarios de los clientes.</span><span class="sxs-lookup"><span data-stu-id="2863f-113">The change from preview 7 was reverted due to customer feedback.</span></span> <span data-ttu-id="2863f-114">La definición de símbolos para versiones anteriores sorprendía y confundía a los clientes, y algunos de ellos dedujeron que se trataba de un error del compilador de C#.</span><span class="sxs-lookup"><span data-stu-id="2863f-114">Defining symbols for earlier versions surprised and confused customers, and some assumed it was a bug in the C# compiler.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="2863f-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="2863f-115">Recommended action</span></span>

<span data-ttu-id="2863f-116">Asegúrese de que la lógica de `#if` no deduce que se define `NETCOREAPP3_1` cuando el proyecto tiene como destino `net5.0` o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="2863f-116">Make sure that your `#if` logic doesn't assume that `NETCOREAPP3_1` is defined when the project targets `net5.0` or higher.</span></span> <span data-ttu-id="2863f-117">En su lugar, debe deducir que `NETCOREAPP3_1` solo se define cuando el proyecto tiene explícitamente establecido `netcoreapp3.1` como destino.</span><span class="sxs-lookup"><span data-stu-id="2863f-117">Instead, assume that `NETCOREAPP3_1` is only defined when the project explicitly targets `netcoreapp3.1`.</span></span>

<span data-ttu-id="2863f-118">Por ejemplo, si su proyecto tiene establecidos varios destinos para .NET Core 2.1 y .NET Core 3.1, y usted llama a las API que se han introducido en .NET Core 3.1, la lógica de `#if` debe ser la siguiente:</span><span class="sxs-lookup"><span data-stu-id="2863f-118">For example, if your project multitargets for .NET Core 2.1 and .NET Core 3.1 and you call APIs that were introduced in .NET Core 3.1, your `#if` logic should look as follows:</span></span>

```csharp
#if NETCOREAPP2_1 || NETCOREAPP3_0
    // Fallback behavior for old versions.
#elif NETCOREAPP
    // Behavior for .NET Core 3.1 and later.
#endif
```

## <a name="affected-apis"></a><span data-ttu-id="2863f-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="2863f-119">Affected APIs</span></span>

<span data-ttu-id="2863f-120">N/D</span><span class="sxs-lookup"><span data-stu-id="2863f-120">N/A</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
