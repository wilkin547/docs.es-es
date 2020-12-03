---
title: 'Cambio importante: Middleware: El middleware del controlador de excepciones produce una excepción original si no se encuentra el controlador'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Middleware: El middleware del controlador de excepciones produce una excepción original si no se encuentra el controlador'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 8801d3e6950d66fd9f24e051fd8729c50eb0b282
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760252"
---
# <a name="middleware-exception-handler-middleware-throws-original-exception-if-handler-not-found"></a><span data-ttu-id="c8aaf-103">Middleware: El middleware del controlador de excepciones produce una excepción original si no se encuentra el controlador</span><span class="sxs-lookup"><span data-stu-id="c8aaf-103">Middleware: Exception Handler Middleware throws original exception if handler not found</span></span>

<span data-ttu-id="c8aaf-104">En las versiones anteriores a ASP.NET Core 5.0, el [middleware del controlador de excepciones](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) ejecuta el controlador de excepciones configurado cuando se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="c8aaf-104">Before ASP.NET Core 5.0, the [Exception Handler Middleware](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) executes the configured exception handler when an exception has occurred.</span></span> <span data-ttu-id="c8aaf-105">Si no se encuentra el controlador de excepciones configurado mediante <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath>, se genera una respuesta HTTP 404.</span><span class="sxs-lookup"><span data-stu-id="c8aaf-105">If the exception handler, configured via <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath>, can't be found, an HTTP 404 response is produced.</span></span> <span data-ttu-id="c8aaf-106">La respuesta es engañosa porque:</span><span class="sxs-lookup"><span data-stu-id="c8aaf-106">The response is misleading in that it:</span></span>

* <span data-ttu-id="c8aaf-107">Parece un error del usuario.</span><span class="sxs-lookup"><span data-stu-id="c8aaf-107">Seems to be a user error.</span></span>
* <span data-ttu-id="c8aaf-108">Oculta el hecho de que se ha producido una excepción en el servidor.</span><span class="sxs-lookup"><span data-stu-id="c8aaf-108">Obscures the fact that an exception occurred on the server.</span></span>

<span data-ttu-id="c8aaf-109">Para solucionar este error engañoso en ASP.NET Core 5.0, el middleware del controlador de excepciones (`ExceptionHandlerMiddleware`) produce la excepción original si no se encuentra el controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="c8aaf-109">To address the misleading error in ASP.NET Core 5.0, the `ExceptionHandlerMiddleware` throws the original exception if the exception handler can't be found.</span></span> <span data-ttu-id="c8aaf-110">Como resultado, el servidor genera una respuesta HTTP 500.</span><span class="sxs-lookup"><span data-stu-id="c8aaf-110">As a result, an HTTP 500 response is produced by the server.</span></span> <span data-ttu-id="c8aaf-111">La respuesta será más fácil de examinar en los registros del servidor en el momento de depurar el error que se ha producido.</span><span class="sxs-lookup"><span data-stu-id="c8aaf-111">The response will be easier to examine in the server logs when debugging the error that occurred.</span></span>

<span data-ttu-id="c8aaf-112">Para obtener información, vea la incidencia de GitHub [dotnet/aspnetcore#25288](https://github.com/dotnet/aspnetcore/issues/25288).</span><span class="sxs-lookup"><span data-stu-id="c8aaf-112">For discussion, see GitHub issue [dotnet/aspnetcore#25288](https://github.com/dotnet/aspnetcore/issues/25288).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="c8aaf-113">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="c8aaf-113">Version introduced</span></span>

<span data-ttu-id="c8aaf-114">5.0 RC 1</span><span class="sxs-lookup"><span data-stu-id="c8aaf-114">5.0 RC 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="c8aaf-115">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="c8aaf-115">Old behavior</span></span>

<span data-ttu-id="c8aaf-116">El middleware del controlador de excepciones produce una respuesta HTTP 404 si no se encuentra el controlador de excepciones configurado.</span><span class="sxs-lookup"><span data-stu-id="c8aaf-116">The Exception Handler Middleware produces an HTTP 404 response if the configured exception handler can't be found.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="c8aaf-117">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="c8aaf-117">New behavior</span></span>

<span data-ttu-id="c8aaf-118">El middleware del controlador de excepciones produce la excepción original si no se encuentra el controlador de excepciones configurado.</span><span class="sxs-lookup"><span data-stu-id="c8aaf-118">The Exception Handler Middleware throws the original exception if the configured exception handler can't be found.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="c8aaf-119">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="c8aaf-119">Reason for change</span></span>

<span data-ttu-id="c8aaf-120">El error HTTP 404 no indica claramente que se ha producido una excepción en el servidor.</span><span class="sxs-lookup"><span data-stu-id="c8aaf-120">The HTTP 404 error doesn't make it obvious that an exception occurred on the server.</span></span> <span data-ttu-id="c8aaf-121">Este cambio produce un error HTTP 500 para que sea obvio que:</span><span class="sxs-lookup"><span data-stu-id="c8aaf-121">This change produces an HTTP 500 error to make it obvious that:</span></span>

* <span data-ttu-id="c8aaf-122">El problema no se debe a un error del usuario.</span><span class="sxs-lookup"><span data-stu-id="c8aaf-122">The problem isn't caused by a user error.</span></span>
* <span data-ttu-id="c8aaf-123">Se ha encontrado una excepción en el servidor.</span><span class="sxs-lookup"><span data-stu-id="c8aaf-123">An exception was encountered on the server.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="c8aaf-124">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="c8aaf-124">Recommended action</span></span>

<span data-ttu-id="c8aaf-125">No hay cambios en la API.</span><span class="sxs-lookup"><span data-stu-id="c8aaf-125">There are no API changes.</span></span> <span data-ttu-id="c8aaf-126">Todas las aplicaciones existentes se seguirán compilando y ejecutando.</span><span class="sxs-lookup"><span data-stu-id="c8aaf-126">All existing apps will continue to compile and run.</span></span> <span data-ttu-id="c8aaf-127">El servidor controla la excepción generada.</span><span class="sxs-lookup"><span data-stu-id="c8aaf-127">The exception thrown is handled by the server.</span></span> <span data-ttu-id="c8aaf-128">Por ejemplo, [Kestrel](/aspnet/core/fundamentals/servers/kestrel) o [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys) convierten la excepción en una respuesta de error HTTP 500.</span><span class="sxs-lookup"><span data-stu-id="c8aaf-128">For example, the exception is converted to an HTTP 500 error response by [Kestrel](/aspnet/core/fundamentals/servers/kestrel) or [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="c8aaf-129">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c8aaf-129">Affected APIs</span></span>

<span data-ttu-id="c8aaf-130">None</span><span class="sxs-lookup"><span data-stu-id="c8aaf-130">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
