---
title: 'Cambio importante: Blazor: propiedad WebEventDescriptor.EventArgsType reemplazada'
description: Obtenga información sobre el cambio importante en ASP.NET Core 6.0 en el que la propiedad WebEventDescriptor.EventArgsType se reemplaza por la propiedad EventName.
author: scottaddie
ms.author: scaddie
ms.date: 02/24/2021
no-loc:
- Blazor
ms.openlocfilehash: 6df086ed234c0071ede83e9fe9d1710f011a2039
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102260019"
---
# <a name="blazor-no-loc-textwebeventdescriptoreventargstype-property-replaced"></a><span data-ttu-id="0fde4-103">Blazor: propiedad :::no-loc text="WebEventDescriptor.EventArgsType"::: reemplazada</span><span class="sxs-lookup"><span data-stu-id="0fde4-103">Blazor: :::no-loc text="WebEventDescriptor.EventArgsType"::: property replaced</span></span>

<span data-ttu-id="0fde4-104">La clase <xref:Microsoft.AspNetCore.Components.RenderTree.WebEventDescriptor> forma parte del protocolo interno de Blazor para comunicar eventos de JavaScript en .NET.</span><span class="sxs-lookup"><span data-stu-id="0fde4-104">The <xref:Microsoft.AspNetCore.Components.RenderTree.WebEventDescriptor> class is part of Blazor's internal protocol for communicating events from JavaScript into .NET.</span></span> <span data-ttu-id="0fde4-105">El código de la aplicación no suele usar esta clase, pero, en su lugar, sí la utilizan los autores de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="0fde4-105">This class isn't typically used by app code, but rather by platform authors.</span></span>

<span data-ttu-id="0fde4-106">A partir de ASP.NET Core 6.0, la propiedad <xref:Microsoft.AspNetCore.Components.RenderTree.WebEventDescriptor.EventArgsType%2A> de `WebEventDescriptor` se reemplaza por una nueva propiedad `EventName`.</span><span class="sxs-lookup"><span data-stu-id="0fde4-106">Starting in ASP.NET Core 6.0, the <xref:Microsoft.AspNetCore.Components.RenderTree.WebEventDescriptor.EventArgsType%2A> property on `WebEventDescriptor` is being replaced by a new `EventName` property.</span></span> <span data-ttu-id="0fde4-107">Es poco probable que este cambio afecte al código de la aplicación, ya que se trata de un detalle de implementación de plataforma de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="0fde4-107">This change is unlikely to affect any app code, as it's a low-level platform implementation detail.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="0fde4-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="0fde4-108">Version introduced</span></span>

<span data-ttu-id="0fde4-109">6.0</span><span class="sxs-lookup"><span data-stu-id="0fde4-109">6.0</span></span>

## <a name="old-behavior"></a><span data-ttu-id="0fde4-110">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="0fde4-110">Old behavior</span></span>

<span data-ttu-id="0fde4-111">En ASP.NET Core 5.0 y versiones anteriores, la propiedad `EventArgsType` describe un nombre de categoría no estándar específico de Blazor para grupos de tipos de eventos DOM.</span><span class="sxs-lookup"><span data-stu-id="0fde4-111">In ASP.NET Core 5.0 and earlier, the property `EventArgsType` describes a nonstandard, Blazor-specific category name for groups of DOM event types.</span></span> <span data-ttu-id="0fde4-112">Por ejemplo, los eventos `click` y `mousedown` se asignan a un valor `EventArgsType` de `mouse`.</span><span class="sxs-lookup"><span data-stu-id="0fde4-112">For example, the `click` and `mousedown` events were both mapped to an `EventArgsType` value of `mouse`.</span></span> <span data-ttu-id="0fde4-113">De forma similar, los eventos `cut`, `copy` y `paste` se asignan a un valor `EventArgsType` de `clipboard`.</span><span class="sxs-lookup"><span data-stu-id="0fde4-113">Similarly, `cut`, `copy`, and `paste` events are mapped to an `EventArgsType` value of `clipboard`.</span></span> <span data-ttu-id="0fde4-114">Estos nombres de categoría se usan para determinar el tipo de .NET que se va a usar para deserializar los datos de los argumentos de eventos entrantes.</span><span class="sxs-lookup"><span data-stu-id="0fde4-114">These category names are used to determine the .NET type to use for deserializing the incoming event arguments data.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="0fde4-115">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="0fde4-115">New behavior</span></span>

<span data-ttu-id="0fde4-116">A partir de ASP.NET Core 6.0, la nueva propiedad `EventName` solo especifica el nombre del evento original.</span><span class="sxs-lookup"><span data-stu-id="0fde4-116">Starting in ASP.NET Core 6.0, the new property `EventName` only specifies the original event's name.</span></span> <span data-ttu-id="0fde4-117">Por ejemplo, `click`, `mousedown`, `cut`, `copy` o `paste`.</span><span class="sxs-lookup"><span data-stu-id="0fde4-117">For example, `click`, `mousedown`, `cut`, `copy`, or `paste`.</span></span> <span data-ttu-id="0fde4-118">Ya no es necesario proporcionar un nombre de categoría específico de Blazor.</span><span class="sxs-lookup"><span data-stu-id="0fde4-118">There's no longer a need to supply a Blazor-specific category name.</span></span> <span data-ttu-id="0fde4-119">Por ese motivo, se quita la propiedad anterior `EventArgsType`.</span><span class="sxs-lookup"><span data-stu-id="0fde4-119">For that reason, the old property `EventArgsType` is removed.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="0fde4-120">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="0fde4-120">Reason for change</span></span>

<span data-ttu-id="0fde4-121">En la solicitud de incorporación de cambios [dotnet/aspnetcore#29993](https://github.com/dotnet/aspnetcore/pull/29993), se presentó la compatibilidad con las clases de argumentos de eventos personalizados.</span><span class="sxs-lookup"><span data-stu-id="0fde4-121">In pull request [dotnet/aspnetcore#29993](https://github.com/dotnet/aspnetcore/pull/29993), support for custom event arguments classes was introduced.</span></span> <span data-ttu-id="0fde4-122">Como parte de esta compatibilidad, el marco de trabajo ya no se basa en todos los eventos englobados dentro de conjunto predefinido de categorías.</span><span class="sxs-lookup"><span data-stu-id="0fde4-122">As part of this support, the framework no longer relies on all events fitting into a predefined set of categories.</span></span> <span data-ttu-id="0fde4-123">El marco de trabajo ahora solo necesita conocer el nombre de evento original.</span><span class="sxs-lookup"><span data-stu-id="0fde4-123">The framework now only needs to know the original event name.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="0fde4-124">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="0fde4-124">Recommended action</span></span>

<span data-ttu-id="0fde4-125">El código de la aplicación no debe verse afectado y no es necesario modificarlo.</span><span class="sxs-lookup"><span data-stu-id="0fde4-125">App code should be unaffected and doesn't need to change.</span></span>

<span data-ttu-id="0fde4-126">Si crea una plataforma de representación de Blazor personalizada, puede que tenga que actualizar el mecanismo para enviar eventos a `Renderer`.</span><span class="sxs-lookup"><span data-stu-id="0fde4-126">If building a custom Blazor rendering platform, you may need to update the mechanism for dispatching events into the `Renderer`.</span></span> <span data-ttu-id="0fde4-127">Reemplace cualquier regla codificada de forma rígida sobre las categorías de eventos con una lógica más sencilla que proporcione el nombre de evento sin formato original.</span><span class="sxs-lookup"><span data-stu-id="0fde4-127">Replace any hardcoded rules about event categories with simpler logic that supplies the original, raw event name.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="0fde4-128">API afectadas</span><span class="sxs-lookup"><span data-stu-id="0fde4-128">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Components.RenderTree.WebEventDescriptor.EventArgsType%2A?displayProperty=nameWithType>

<!--

## Category

ASP.NET Core

## Affected APIs

`P:Microsoft.AspNetCore.Components.RenderTree.WebEventDescriptor.EventArgsType`

-->
