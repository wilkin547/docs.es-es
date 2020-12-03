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
# <a name="httpsys-client-certificate-renegotiation-disabled-by-default"></a>HttpSys: Deshabilitación predeterminada de la renegociación del certificado de cliente

La opción de renegociar una conexión y solicitar un certificado de cliente se ha deshabilitado de forma predeterminada. Para obtener información, vea el tema [dotnet/aspnetcore#23181](https://github.com/dotnet/aspnetcore/issues/23181).

## <a name="version-introduced"></a>Versión introducida

ASP.NET Core 5.0

## <a name="old-behavior"></a>Comportamiento anterior

La conexión se puede volver a negociar para solicitar un certificado de cliente.

## <a name="new-behavior"></a>Comportamiento nuevo

Los certificados de cliente solo se pueden solicitar durante el protocolo de enlace de la conexión inicial. Para obtener más información, vea la solicitud de incorporación de cambios [dotnet/aspnetcore#23162](https://github.com/dotnet/aspnetcore/pull/23162).

## <a name="reason-for-change"></a>Motivo del cambio

La renegociación causaba una serie de problemas de rendimiento e interbloqueo. Tampoco se admite en HTTP/2. Para obtener información adicional sobre el momento en que se introdujo la opción para controlar este comportamiento en ASP.NET Core 3.1, vea el problema [dotnet/aspnetcore#14806](https://github.com/dotnet/aspnetcore/issues/14806).

## <a name="recommended-action"></a>Acción recomendada

Las aplicaciones que requieren certificados de cliente deben usar *netsh.exe* para establecer la opción `clientcertnegotiation` en `enabled`. Para más información, vea [Comandos netsh http](/windows-server/networking/technologies/netsh/netsh-http).

Si quiere que los certificados de cliente estén habilitados solo para algunas partes de la aplicación, consulte las instrucciones en [Certificados de cliente opcionales](/aspnet/core/security/authentication/certauth?view=aspnetcore-3.1#optional-client-certificates).

Si necesita el comportamiento anterior de renegociación, establezca `HttpSysOptions.ClientCertificateMethod` en el valor anterior `ClientCertificateMethod.AllowRenegotiate`, si bien esto no es recomendable por los motivos que se describen anteriormente y en la guía vinculada.

## <a name="affected-apis"></a>API afectadas

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
