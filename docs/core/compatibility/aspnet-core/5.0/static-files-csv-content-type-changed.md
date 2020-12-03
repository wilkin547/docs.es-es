---
title: 'Cambio importante: Archivos estáticos: tipo de contenido CSV cambiado a compatible con los estándares'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Archivos estáticos: tipo de contenido CSV cambiado a compatible con los estándares'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c94a0cf213970d20559b7c061d8be220b43961e0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760278"
---
# <a name="static-files-csv-content-type-changed-to-standards-compliant"></a><span data-ttu-id="00f0d-103">Archivos estáticos: tipo de contenido CSV cambiado a compatible con los estándares</span><span class="sxs-lookup"><span data-stu-id="00f0d-103">Static files: CSV content type changed to standards-compliant</span></span>

<span data-ttu-id="00f0d-104">En ASP.NET Core 5.0, el valor de encabezado de respuesta `Content-Type` predeterminado que usa el [Middleware de archivo estático](/aspnet/core/fundamentals/static-files) para archivos *.csv* ha cambiado al valor `text/csv` compatible con los estándares.</span><span class="sxs-lookup"><span data-stu-id="00f0d-104">In ASP.NET Core 5.0, the default `Content-Type` response header value that the [Static File Middleware](/aspnet/core/fundamentals/static-files) uses for *.csv* files has changed to the standards-compliant value `text/csv`.</span></span>

<span data-ttu-id="00f0d-105">Para obtener información sobre esta incidencia, vea [dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385).</span><span class="sxs-lookup"><span data-stu-id="00f0d-105">For discussion on this issue, see [dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="00f0d-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="00f0d-106">Version introduced</span></span>

<span data-ttu-id="00f0d-107">5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="00f0d-107">5.0 Preview 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="00f0d-108">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="00f0d-108">Old behavior</span></span>

<span data-ttu-id="00f0d-109">Se usó el valor de encabezado `Content-Type` `application/octet-stream`.</span><span class="sxs-lookup"><span data-stu-id="00f0d-109">The `Content-Type` header value `application/octet-stream` was used.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="00f0d-110">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="00f0d-110">New behavior</span></span>

<span data-ttu-id="00f0d-111">Se usa el valor de encabezado `Content-Type` `text/csv`.</span><span class="sxs-lookup"><span data-stu-id="00f0d-111">The `Content-Type` header value `text/csv` is used.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="00f0d-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="00f0d-112">Reason for change</span></span>

<span data-ttu-id="00f0d-113">Cumplimiento con el estándar [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1).</span><span class="sxs-lookup"><span data-stu-id="00f0d-113">Compliance with the [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1) standard.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="00f0d-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="00f0d-114">Recommended action</span></span>

<span data-ttu-id="00f0d-115">Si este cambio afecta a la aplicación, se puede personalizar la extensión del archivo a una asignación de tipo MIME.</span><span class="sxs-lookup"><span data-stu-id="00f0d-115">If this change impacts your app, you can customize the file extension-to-MIME type mapping.</span></span> <span data-ttu-id="00f0d-116">Para revertir al tipo MIME `application/octet-stream`, modifique la llamada de método <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> en `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="00f0d-116">To revert to the `application/octet-stream` MIME type, modify the <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> method call in `Startup.Configure`.</span></span> <span data-ttu-id="00f0d-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="00f0d-117">For example:</span></span>

```csharp
var provider = new FileExtensionContentTypeProvider();
provider.Mappings[".csv"] = MediaTypeNames.Application.Octet;

app.UseStaticFiles(new StaticFileOptions
{
    ContentTypeProvider = provider
});
```

<span data-ttu-id="00f0d-118">Para obtener más información sobre la personalización de la asignación, vea [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).</span><span class="sxs-lookup"><span data-stu-id="00f0d-118">For more information on customizing the mapping, see [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="00f0d-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="00f0d-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider`

-->
