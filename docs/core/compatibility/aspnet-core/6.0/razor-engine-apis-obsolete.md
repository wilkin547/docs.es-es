---
title: 'Cambio importante: Razor: API de RazorEngine marcadas como obsoletas'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 6.0 titulado Razor: API de RazorEngine marcadas como obsoletas.'
author: scottaddie
ms.author: scaddie
ms.date: 02/09/2021
ms.openlocfilehash: 173ff0ee5c062f050c967c6edc7bed333d1a2031
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488255"
---
# <a name="razor-razorengine-apis-marked-obsolete"></a><span data-ttu-id="1a8de-103">Razor: API de RazorEngine marcadas como obsoletas</span><span class="sxs-lookup"><span data-stu-id="1a8de-103">Razor: RazorEngine APIs marked obsolete</span></span>

<span data-ttu-id="1a8de-104">Los tipos relacionados con el tipo <xref:Microsoft.AspNetCore.Razor.Language.RazorEngine> en Blazor se han marcado como obsoletos.</span><span class="sxs-lookup"><span data-stu-id="1a8de-104">Types related to the <xref:Microsoft.AspNetCore.Razor.Language.RazorEngine> type in Blazor have been marked as obsolete.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="1a8de-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1a8de-105">Version introduced</span></span>

<span data-ttu-id="1a8de-106">6.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="1a8de-106">6.0 Preview 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="1a8de-107">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="1a8de-107">Old behavior</span></span>

<span data-ttu-id="1a8de-108">Las API `RazorEngine` no están obsoletas.</span><span class="sxs-lookup"><span data-stu-id="1a8de-108">The `RazorEngine` APIs aren't obsolete.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="1a8de-109">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="1a8de-109">New behavior</span></span>

<span data-ttu-id="1a8de-110">Las API de `RazorEngine` están obsoletas.</span><span class="sxs-lookup"><span data-stu-id="1a8de-110">The `RazorEngine` APIs are obsolete.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="1a8de-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="1a8de-111">Reason for change</span></span>

<span data-ttu-id="1a8de-112">El tipo `RazorEngine` ha quedado en desuso en favor del tipo <xref:Microsoft.AspNetCore.Razor.Language.RazorProjectEngine>.</span><span class="sxs-lookup"><span data-stu-id="1a8de-112">The `RazorEngine` type has been deprecated in favor of the <xref:Microsoft.AspNetCore.Razor.Language.RazorProjectEngine> type.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="1a8de-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="1a8de-113">Recommended action</span></span>

<span data-ttu-id="1a8de-114">Cambie el código fuente del tipo `RazorEngine` al tipo `RazorProjectEngine`.</span><span class="sxs-lookup"><span data-stu-id="1a8de-114">Migrate source code from the `RazorEngine` type to the `RazorProjectEngine` type.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="1a8de-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="1a8de-115">Affected APIs</span></span>

- [<span data-ttu-id="1a8de-116">Microsoft.AspNetCore.Mvc.Razor.Extensions.InjectDirective.Register</span><span class="sxs-lookup"><span data-stu-id="1a8de-116">Microsoft.AspNetCore.Mvc.Razor.Extensions.InjectDirective.Register</span></span>](/dotnet/api/microsoft.aspnetcore.mvc.razor.extensions.injectdirective.register?view=aspnetcore-3.1&preserve-view=true)
- [<span data-ttu-id="1a8de-117">Microsoft.AspNetCore.Mvc.Razor.Extensions.ModelDirective.Register</span><span class="sxs-lookup"><span data-stu-id="1a8de-117">Microsoft.AspNetCore.Mvc.Razor.Extensions.ModelDirective.Register</span></span>](/dotnet/api/microsoft.aspnetcore.mvc.razor.extensions.namespacedirective.register?view=aspnetcore-2.2&preserve-view=true)
- [<span data-ttu-id="1a8de-118">Microsoft.AspNetCore.Mvc.Razor.Extensions.PageDirective.Register</span><span class="sxs-lookup"><span data-stu-id="1a8de-118">Microsoft.AspNetCore.Mvc.Razor.Extensions.PageDirective.Register</span></span>](/dotnet/api/microsoft.aspnetcore.mvc.razor.extensions.namespacedirective.register?view=aspnetcore-2.2&preserve-view=true)
- [<span data-ttu-id="1a8de-119">Microsoft.AspNetCore.Razor.Language.Extensions.FunctionsDirective.Register</span><span class="sxs-lookup"><span data-stu-id="1a8de-119">Microsoft.AspNetCore.Razor.Language.Extensions.FunctionsDirective.Register</span></span>](/dotnet/api/microsoft.aspnetcore.razor.language.extensions.functionsdirective.register?view=aspnetcore-3.0&preserve-view=true)
- [<span data-ttu-id="1a8de-120">Microsoft.AspNetCore.Razor.Language.Extensions.InheritsDirective.Register</span><span class="sxs-lookup"><span data-stu-id="1a8de-120">Microsoft.AspNetCore.Razor.Language.Extensions.InheritsDirective.Register</span></span>](/dotnet/api/microsoft.aspnetcore.razor.language.extensions.inheritsdirective.register?view=aspnetcore-3.0&preserve-view=true)
- [<span data-ttu-id="1a8de-121">Microsoft.AspNetCore.Razor.Language.Extensions.SectionDirective.Register</span><span class="sxs-lookup"><span data-stu-id="1a8de-121">Microsoft.AspNetCore.Razor.Language.Extensions.SectionDirective.Register</span></span>](/dotnet/api/microsoft.aspnetcore.razor.language.extensions.sectiondirective.register?view=aspnetcore-3.0&preserve-view=true)
- [<span data-ttu-id="1a8de-122">Microsoft.AspNetCore.Razor.Language.IRazorEngineBuilder</span><span class="sxs-lookup"><span data-stu-id="1a8de-122">Microsoft.AspNetCore.Razor.Language.IRazorEngineBuilder</span></span>](/dotnet/api/microsoft.aspnetcore.razor.language.irazorenginebuilder?view=aspnetcore-3.0&preserve-view=true)

<!--

## Category

ASP.NET Core

## Affected APIs

- `Overload:Microsoft.AspNetCore.Mvc.Razor.Extensions.InjectDirective.Register`
- `Overload:Microsoft.AspNetCore.Mvc.Razor.Extensions.ModelDirective.Register`
- `Overload:Microsoft.AspNetCore.Mvc.Razor.Extensions.PageDirective.Register`
- `Overload:Microsoft.AspNetCore.Razor.Language.Extensions.FunctionsDirective.Register`
- `Overload:Microsoft.AspNetCore.Razor.Language.Extensions.InheritsDirective.Register`
- `Overload:Microsoft.AspNetCore.Razor.Language.Extensions.SectionDirective.Register`
- `T:Microsoft.AspNetCore.Razor.Language.IRazorEngineBuilder`

-->
