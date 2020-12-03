---
title: 'Cambio importante: HttpSys: Deshabilitación predeterminada de la renegociación del certificado de cliente'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado HttpSys: Deshabilitación predeterminada de la renegociación del certificado de cliente'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 796989e1a21e3cb206d081e4fe8f79630121dc84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760099"
---
# <a name="httpsys-client-certificate-renegotiation-disabled-by-default"></a><span data-ttu-id="7bc15-103">HttpSys: Deshabilitación predeterminada de la renegociación del certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="7bc15-103">HttpSys: Client certificate renegotiation disabled by default</span></span>

<span data-ttu-id="7bc15-104">La opción de renegociar una conexión y solicitar un certificado de cliente se ha deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7bc15-104">The option to renegotiate a connection and request a client certificate has been disabled by default.</span></span> <span data-ttu-id="7bc15-105">Para obtener información, vea el tema [dotnet/aspnetcore#23181](https://github.com/dotnet/aspnetcore/issues/23181).</span><span class="sxs-lookup"><span data-stu-id="7bc15-105">For discussion, see issue [dotnet/aspnetcore#23181](https://github.com/dotnet/aspnetcore/issues/23181).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="7bc15-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="7bc15-106">Version introduced</span></span>

<span data-ttu-id="7bc15-107">ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="7bc15-107">ASP.NET Core 5.0</span></span>

## <a name="old-behavior"></a><span data-ttu-id="7bc15-108">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="7bc15-108">Old behavior</span></span>

<span data-ttu-id="7bc15-109">La conexión se puede volver a negociar para solicitar un certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="7bc15-109">The connection can be renegotiated to request a client certificate.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="7bc15-110">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="7bc15-110">New behavior</span></span>

<span data-ttu-id="7bc15-111">Los certificados de cliente solo se pueden solicitar durante el protocolo de enlace de la conexión inicial.</span><span class="sxs-lookup"><span data-stu-id="7bc15-111">Client certificates can only be requested during the initial connection handshake.</span></span> <span data-ttu-id="7bc15-112">Para obtener más información, vea la solicitud de incorporación de cambios [dotnet/aspnetcore#23162](https://github.com/dotnet/aspnetcore/pull/23162).</span><span class="sxs-lookup"><span data-stu-id="7bc15-112">For more information, see pull request [dotnet/aspnetcore#23162](https://github.com/dotnet/aspnetcore/pull/23162).</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="7bc15-113">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="7bc15-113">Reason for change</span></span>

<span data-ttu-id="7bc15-114">La renegociación causaba una serie de problemas de rendimiento e interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="7bc15-114">Renegotiation caused a number of performance and deadlock issues.</span></span> <span data-ttu-id="7bc15-115">Tampoco se admite en HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="7bc15-115">It's also not supported in HTTP/2.</span></span> <span data-ttu-id="7bc15-116">Para obtener información adicional sobre el momento en que se introdujo la opción para controlar este comportamiento en ASP.NET Core 3.1, vea el problema [dotnet/aspnetcore#14806](https://github.com/dotnet/aspnetcore/issues/14806).</span><span class="sxs-lookup"><span data-stu-id="7bc15-116">For additional context from when the option to control this behavior was introduced in ASP.NET Core 3.1, see issue [dotnet/aspnetcore#14806](https://github.com/dotnet/aspnetcore/issues/14806).</span></span>

## <a name="recommended-action"></a><span data-ttu-id="7bc15-117">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="7bc15-117">Recommended action</span></span>

<span data-ttu-id="7bc15-118">Las aplicaciones que requieren certificados de cliente deben usar *netsh.exe* para establecer la opción `clientcertnegotiation` en `enabled`.</span><span class="sxs-lookup"><span data-stu-id="7bc15-118">Apps that require client certificates should use *netsh.exe* to set the `clientcertnegotiation` option to `enabled`.</span></span> <span data-ttu-id="7bc15-119">Para más información, vea [Comandos netsh http](/windows-server/networking/technologies/netsh/netsh-http).</span><span class="sxs-lookup"><span data-stu-id="7bc15-119">For more information, see [netsh http commands](/windows-server/networking/technologies/netsh/netsh-http).</span></span>

<span data-ttu-id="7bc15-120">Si quiere que los certificados de cliente estén habilitados solo para algunas partes de la aplicación, consulte las instrucciones en [Certificados de cliente opcionales](/aspnet/core/security/authentication/certauth?view=aspnetcore-3.1#optional-client-certificates).</span><span class="sxs-lookup"><span data-stu-id="7bc15-120">If you want client certificates enabled for only some parts of your app, see the guidance at [Optional client certificates](/aspnet/core/security/authentication/certauth?view=aspnetcore-3.1#optional-client-certificates).</span></span>

<span data-ttu-id="7bc15-121">Si necesita el comportamiento anterior de renegociación, establezca `HttpSysOptions.ClientCertificateMethod` en el valor anterior `ClientCertificateMethod.AllowRenegotiate`,</span><span class="sxs-lookup"><span data-stu-id="7bc15-121">If you need the old renegotiate behavior, set `HttpSysOptions.ClientCertificateMethod` to the old value `ClientCertificateMethod.AllowRenegotiate`.</span></span> <span data-ttu-id="7bc15-122">si bien esto no es recomendable por los motivos que se describen anteriormente y en la guía vinculada.</span><span class="sxs-lookup"><span data-stu-id="7bc15-122">This isn't recommended for the reasons outlined above and in the linked guidance.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="7bc15-123">API afectadas</span><span class="sxs-lookup"><span data-stu-id="7bc15-123">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate`
- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync`
- `Overload:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod`

-->
