---
ms.openlocfilehash: 26e521a86b504824f035ad5d40e4a04d2ea26abc
ms.sourcegitcommit: 6d4ee46871deb9ea1e45bb5f3784474e240bbc26
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2020
ms.locfileid: "90022977"
---
### <a name="middleware-exception-handler-middleware-throws-original-exception-if-handler-not-found"></a><span data-ttu-id="a6a04-101">Middleware: El middleware del controlador de excepciones produce una excepción original si no se encuentra el controlador</span><span class="sxs-lookup"><span data-stu-id="a6a04-101">Middleware: Exception Handler Middleware throws original exception if handler not found</span></span>

<span data-ttu-id="a6a04-102">En las versiones anteriores a ASP.NET Core 5.0, el [middleware del controlador de excepciones](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) ejecuta el controlador de excepciones configurado cuando se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="a6a04-102">Before ASP.NET Core 5.0, the [Exception Handler Middleware](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) executes the configured exception handler when an exception has occurred.</span></span> <span data-ttu-id="a6a04-103">Si no se encuentra el controlador de excepciones configurado mediante <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath>, se genera una respuesta HTTP 404.</span><span class="sxs-lookup"><span data-stu-id="a6a04-103">If the exception handler, configured via <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath>, can't be found, an HTTP 404 response is produced.</span></span> <span data-ttu-id="a6a04-104">La respuesta es engañosa porque:</span><span class="sxs-lookup"><span data-stu-id="a6a04-104">The response is misleading in that it:</span></span>

* <span data-ttu-id="a6a04-105">Parece un error del usuario.</span><span class="sxs-lookup"><span data-stu-id="a6a04-105">Seems to be a user error.</span></span>
* <span data-ttu-id="a6a04-106">Oculta el hecho de que se ha producido una excepción en el servidor.</span><span class="sxs-lookup"><span data-stu-id="a6a04-106">Obscures the fact that an exception occurred on the server.</span></span>

<span data-ttu-id="a6a04-107">Para solucionar este error engañoso en ASP.NET Core 5.0, el middleware del controlador de excepciones (`ExceptionHandlerMiddleware`) produce la excepción original si no se encuentra el controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="a6a04-107">To address the misleading error in ASP.NET Core 5.0, the `ExceptionHandlerMiddleware` throws the original exception if the exception handler can't be found.</span></span> <span data-ttu-id="a6a04-108">Como resultado, el servidor genera una respuesta HTTP 500.</span><span class="sxs-lookup"><span data-stu-id="a6a04-108">As a result, an HTTP 500 response is produced by the server.</span></span> <span data-ttu-id="a6a04-109">La respuesta será más fácil de examinar en los registros del servidor en el momento de depurar el error que se ha producido.</span><span class="sxs-lookup"><span data-stu-id="a6a04-109">The response will be easier to examine in the server logs when debugging the error that occurred.</span></span>

<span data-ttu-id="a6a04-110">Para obtener información, vea la incidencia de GitHub [dotnet/aspnetcore#25288](https://github.com/dotnet/aspnetcore/issues/25288).</span><span class="sxs-lookup"><span data-stu-id="a6a04-110">For discussion, see GitHub issue [dotnet/aspnetcore#25288](https://github.com/dotnet/aspnetcore/issues/25288).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a6a04-111">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="a6a04-111">Version introduced</span></span>

<span data-ttu-id="a6a04-112">5.0 RC 1</span><span class="sxs-lookup"><span data-stu-id="a6a04-112">5.0 RC 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="a6a04-113">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="a6a04-113">Old behavior</span></span>

<span data-ttu-id="a6a04-114">El middleware del controlador de excepciones produce una respuesta HTTP 404 si no se encuentra el controlador de excepciones configurado.</span><span class="sxs-lookup"><span data-stu-id="a6a04-114">The Exception Handler Middleware produces an HTTP 404 response if the configured exception handler can't be found.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="a6a04-115">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="a6a04-115">New behavior</span></span>

<span data-ttu-id="a6a04-116">El middleware del controlador de excepciones produce la excepción original si no se encuentra el controlador de excepciones configurado.</span><span class="sxs-lookup"><span data-stu-id="a6a04-116">The Exception Handler Middleware throws the original exception if the configured exception handler can't be found.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a6a04-117">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="a6a04-117">Reason for change</span></span>

<span data-ttu-id="a6a04-118">El error HTTP 404 no indica claramente que se ha producido una excepción en el servidor.</span><span class="sxs-lookup"><span data-stu-id="a6a04-118">The HTTP 404 error doesn't make it obvious that an exception occurred on the server.</span></span> <span data-ttu-id="a6a04-119">Este cambio produce un error HTTP 500 para que sea obvio que:</span><span class="sxs-lookup"><span data-stu-id="a6a04-119">This change produces an HTTP 500 error to make it obvious that:</span></span>

* <span data-ttu-id="a6a04-120">El problema no se debe a un error del usuario.</span><span class="sxs-lookup"><span data-stu-id="a6a04-120">The problem isn't caused by a user error.</span></span>
* <span data-ttu-id="a6a04-121">Se ha encontrado una excepción en el servidor.</span><span class="sxs-lookup"><span data-stu-id="a6a04-121">An exception was encountered on the server.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a6a04-122">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="a6a04-122">Recommended action</span></span>

<span data-ttu-id="a6a04-123">No hay cambios en la API.</span><span class="sxs-lookup"><span data-stu-id="a6a04-123">There are no API changes.</span></span> <span data-ttu-id="a6a04-124">Todas las aplicaciones existentes se seguirán compilando y ejecutando.</span><span class="sxs-lookup"><span data-stu-id="a6a04-124">All existing apps will continue to compile and run.</span></span> <span data-ttu-id="a6a04-125">El servidor controla la excepción generada.</span><span class="sxs-lookup"><span data-stu-id="a6a04-125">The exception thrown is handled by the server.</span></span> <span data-ttu-id="a6a04-126">Por ejemplo, [Kestrel](/aspnet/core/fundamentals/servers/kestrel) o [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys) convierten la excepción en una respuesta de error HTTP 500.</span><span class="sxs-lookup"><span data-stu-id="a6a04-126">For example, the exception is converted to an HTTP 500 error response by [Kestrel](/aspnet/core/fundamentals/servers/kestrel) or [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys).</span></span>

#### <a name="category"></a><span data-ttu-id="a6a04-127">Categoría</span><span class="sxs-lookup"><span data-stu-id="a6a04-127">Category</span></span>

<span data-ttu-id="a6a04-128">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a6a04-128">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a6a04-129">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a6a04-129">Affected APIs</span></span>

<span data-ttu-id="a6a04-130">None</span><span class="sxs-lookup"><span data-stu-id="a6a04-130">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
