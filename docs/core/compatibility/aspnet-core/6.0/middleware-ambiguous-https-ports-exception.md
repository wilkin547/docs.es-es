---
title: 'Cambio importante: Middleware: El middleware de redireccionamiento de HTTPS inicia una excepción en puertos HTTPS ambiguos'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 6.0 titulado Middleware: El middleware de redireccionamiento de HTTPS inicia una excepción en puertos HTTPS ambiguos.'
author: scottaddie
ms.author: scaddie
ms.date: 02/04/2021
ms.openlocfilehash: 1f49e0df7eaa2eecd83643c9596e745109a340b7
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488258"
---
# <a name="middleware-https-redirection-middleware-throws-exception-on-ambiguous-https-ports"></a><span data-ttu-id="5eba6-103">Middleware: El middleware de redireccionamiento de HTTPS inicia una excepción en puertos HTTPS ambiguos</span><span class="sxs-lookup"><span data-stu-id="5eba6-103">Middleware: HTTPS Redirection Middleware throws exception on ambiguous HTTPS ports</span></span>

<span data-ttu-id="5eba6-104">En ASP.NET Core 6.0, el [middleware de redireccionamiento de HTTPS](xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection%2A) inicia una excepción de tipo <xref:System.InvalidOperationException> cuando encuentra varios puertos HTTPS en la configuración del servidor.</span><span class="sxs-lookup"><span data-stu-id="5eba6-104">In ASP.NET Core 6.0, the [HTTPS Redirection Middleware](xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection%2A) throws an exception of type <xref:System.InvalidOperationException> when it finds multiple HTTPS ports in the server configuration.</span></span> <span data-ttu-id="5eba6-105">El mensaje de la excepción contiene el texto "No se puede determinar el puerto https de IServerAddressesFeature, pero se han encontrado varios valores.</span><span class="sxs-lookup"><span data-stu-id="5eba6-105">The exception's message contains the text "Cannot determine the https port from IServerAddressesFeature, multiple values were found.</span></span> <span data-ttu-id="5eba6-106">Establezca el puerto deseado explícitamente en HttpsRedirectionOptions.HttpsPort".</span><span class="sxs-lookup"><span data-stu-id="5eba6-106">Set the desired port explicitly on HttpsRedirectionOptions.HttpsPort."</span></span>

<span data-ttu-id="5eba6-107">Para obtener información, vea la incidencia de GitHub [n.º 29222 (dotnet/aspnetcore)](https://github.com/dotnet/aspnetcore/issues/29222).</span><span class="sxs-lookup"><span data-stu-id="5eba6-107">For discussion, see GitHub issue [dotnet/aspnetcore#29222](https://github.com/dotnet/aspnetcore/issues/29222).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="5eba6-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="5eba6-108">Version introduced</span></span>

<span data-ttu-id="5eba6-109">6.0</span><span class="sxs-lookup"><span data-stu-id="5eba6-109">6.0</span></span>

## <a name="old-behavior"></a><span data-ttu-id="5eba6-110">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="5eba6-110">Old behavior</span></span>

<span data-ttu-id="5eba6-111">Cuando el middleware de redireccionamiento de HTTPS no se configura explícitamente con un puerto, busca <xref:Microsoft.AspNetCore.Hosting.Server.Features.IServerAddressesFeature> durante la primera solicitud para determinar el puerto HTTPS al que debe realizar el redireccionamiento.</span><span class="sxs-lookup"><span data-stu-id="5eba6-111">When the HTTPS Redirection Middleware isn't explicitly configured with a port, it searches <xref:Microsoft.AspNetCore.Hosting.Server.Features.IServerAddressesFeature> during the first request to determine the HTTPS port to which it should redirect.</span></span>

<span data-ttu-id="5eba6-112">Si no hay puertos HTTPS o hay varios distintos, no queda claro cuál se debe usar.</span><span class="sxs-lookup"><span data-stu-id="5eba6-112">If there are no HTTPS ports or multiple distinct ports, it's unclear which port should be used.</span></span> <span data-ttu-id="5eba6-113">El middleware registra una advertencia y se deshabilita a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="5eba6-113">The middleware logs a warning and disables itself.</span></span> <span data-ttu-id="5eba6-114">Las solicitudes HTTP se procesan con normalidad.</span><span class="sxs-lookup"><span data-stu-id="5eba6-114">HTTP requests are processed normally.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="5eba6-115">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="5eba6-115">New behavior</span></span>

<span data-ttu-id="5eba6-116">Cuando el middleware de redireccionamiento de HTTPS no se configura explícitamente con un puerto, busca `IServerAddressesFeature` durante la primera solicitud para determinar el puerto HTTPS al que debe realizar el redireccionamiento.</span><span class="sxs-lookup"><span data-stu-id="5eba6-116">When the HTTPS Redirection Middleware isn't explicitly configured with a port, it searches `IServerAddressesFeature` during the first request to determine the HTTPS port to which it should redirect.</span></span>

<span data-ttu-id="5eba6-117">Si no hay ningún puerto HTTPS, el middleware sigue registrando una advertencia y se deshabilita a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="5eba6-117">If there are no HTTPS ports, the middleware still logs a warning and disables itself.</span></span> <span data-ttu-id="5eba6-118">Las solicitudes HTTP se procesan con normalidad.</span><span class="sxs-lookup"><span data-stu-id="5eba6-118">HTTP requests are processed normally.</span></span> <span data-ttu-id="5eba6-119">Este comportamiento admite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5eba6-119">This behavior supports:</span></span>

* <span data-ttu-id="5eba6-120">Escenarios de desarrollo sin HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5eba6-120">Development scenarios without HTTPS.</span></span>
* <span data-ttu-id="5eba6-121">Escenarios hospedados en los que se termina TLS antes de llegar al servidor.</span><span class="sxs-lookup"><span data-stu-id="5eba6-121">Hosted scenarios in which TLS is terminated before reaching the server.</span></span>

<span data-ttu-id="5eba6-122">Si hay varios puertos distintos, no queda claro cuál se debe usar.</span><span class="sxs-lookup"><span data-stu-id="5eba6-122">If there are multiple distinct ports, it's unclear which port should be used.</span></span> <span data-ttu-id="5eba6-123">El middleware inicia una excepción y se produce un error en la solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="5eba6-123">The middleware throws an exception and fails the HTTP request.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="5eba6-124">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="5eba6-124">Reason for change</span></span>

<span data-ttu-id="5eba6-125">Este cambio impide la entrega de datos potencialmente confidenciales mediante conexiones HTTP sin cifrar en aquellos casos en los que se sabe que HTTPS está disponible.</span><span class="sxs-lookup"><span data-stu-id="5eba6-125">This change prevents potentially sensitive data from being served over unencrypted HTTP connections when HTTPS is known to be available.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="5eba6-126">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="5eba6-126">Recommended action</span></span>

<span data-ttu-id="5eba6-127">Para habilitar el redireccionamiento HTTPS cuando el servidor tiene varios puertos HTTPS distintos, debe especificar un puerto en la configuración.</span><span class="sxs-lookup"><span data-stu-id="5eba6-127">To enable HTTPS redirection when the server has multiple distinct HTTPS ports, you must specify one port in the configuration.</span></span> <span data-ttu-id="5eba6-128">Para obtener más información, vea [Configuración de puertos](/aspnet/core/security/enforcing-ssl?view=aspnetcore-5.0&preserve-view=true#port-configuration).</span><span class="sxs-lookup"><span data-stu-id="5eba6-128">For more information, see [Port configuration](/aspnet/core/security/enforcing-ssl?view=aspnetcore-5.0&preserve-view=true#port-configuration).</span></span>

<span data-ttu-id="5eba6-129">Si no necesita el middleware de redireccionamiento de HTTPS en la aplicación, quite `UseHttpsRedirection` de *Startup.cs*.</span><span class="sxs-lookup"><span data-stu-id="5eba6-129">If you don't need the HTTPS Redirection Middleware in your app, remove `UseHttpsRedirection` from *Startup.cs*.</span></span>

<span data-ttu-id="5eba6-130">Si tiene que seleccionar el puerto HTTPS correcto de forma dinámica, proporcione comentarios en la incidencia de GitHub [n.º 21291 (dotnet/aspnetcore)](https://github.com/dotnet/aspnetcore/issues/21291).</span><span class="sxs-lookup"><span data-stu-id="5eba6-130">If you need to select the correct HTTPS port dynamically, provide feedback in GitHub issue [dotnet/aspnetcore#21291](https://github.com/dotnet/aspnetcore/issues/21291).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="5eba6-131">API afectadas</span><span class="sxs-lookup"><span data-stu-id="5eba6-131">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection%2A?displayProperty=nameWithType>

<!--

## Category

ASP.NET Core

## Affected APIs

`Overload:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection`

-->
