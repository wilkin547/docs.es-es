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
# <a name="middleware-https-redirection-middleware-throws-exception-on-ambiguous-https-ports"></a>Middleware: El middleware de redireccionamiento de HTTPS inicia una excepción en puertos HTTPS ambiguos

En ASP.NET Core 6.0, el [middleware de redireccionamiento de HTTPS](xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection%2A) inicia una excepción de tipo <xref:System.InvalidOperationException> cuando encuentra varios puertos HTTPS en la configuración del servidor. El mensaje de la excepción contiene el texto "No se puede determinar el puerto https de IServerAddressesFeature, pero se han encontrado varios valores. Establezca el puerto deseado explícitamente en HttpsRedirectionOptions.HttpsPort".

Para obtener información, vea la incidencia de GitHub [n.º 29222 (dotnet/aspnetcore)](https://github.com/dotnet/aspnetcore/issues/29222).

## <a name="version-introduced"></a>Versión introducida

6.0

## <a name="old-behavior"></a>Comportamiento anterior

Cuando el middleware de redireccionamiento de HTTPS no se configura explícitamente con un puerto, busca <xref:Microsoft.AspNetCore.Hosting.Server.Features.IServerAddressesFeature> durante la primera solicitud para determinar el puerto HTTPS al que debe realizar el redireccionamiento.

Si no hay puertos HTTPS o hay varios distintos, no queda claro cuál se debe usar. El middleware registra una advertencia y se deshabilita a sí mismo. Las solicitudes HTTP se procesan con normalidad.

## <a name="new-behavior"></a>Comportamiento nuevo

Cuando el middleware de redireccionamiento de HTTPS no se configura explícitamente con un puerto, busca `IServerAddressesFeature` durante la primera solicitud para determinar el puerto HTTPS al que debe realizar el redireccionamiento.

Si no hay ningún puerto HTTPS, el middleware sigue registrando una advertencia y se deshabilita a sí mismo. Las solicitudes HTTP se procesan con normalidad. Este comportamiento admite lo siguiente:

* Escenarios de desarrollo sin HTTPS.
* Escenarios hospedados en los que se termina TLS antes de llegar al servidor.

Si hay varios puertos distintos, no queda claro cuál se debe usar. El middleware inicia una excepción y se produce un error en la solicitud HTTP.

## <a name="reason-for-change"></a>Motivo del cambio

Este cambio impide la entrega de datos potencialmente confidenciales mediante conexiones HTTP sin cifrar en aquellos casos en los que se sabe que HTTPS está disponible.

## <a name="recommended-action"></a>Acción recomendada

Para habilitar el redireccionamiento HTTPS cuando el servidor tiene varios puertos HTTPS distintos, debe especificar un puerto en la configuración. Para obtener más información, vea [Configuración de puertos](/aspnet/core/security/enforcing-ssl?view=aspnetcore-5.0&preserve-view=true#port-configuration).

Si no necesita el middleware de redireccionamiento de HTTPS en la aplicación, quite `UseHttpsRedirection` de *Startup.cs*.

Si tiene que seleccionar el puerto HTTPS correcto de forma dinámica, proporcione comentarios en la incidencia de GitHub [n.º 21291 (dotnet/aspnetcore)](https://github.com/dotnet/aspnetcore/issues/21291).

## <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection%2A?displayProperty=nameWithType>

<!--

## Category

ASP.NET Core

## Affected APIs

`Overload:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection`

-->
