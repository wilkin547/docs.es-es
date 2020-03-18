---
ms.openlocfilehash: eb3fa768a491f6c0ff4b15479beabd71b0670338
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937307"
---
### <a name="hosting-https-redirection-enabled-for-iis-out-of-process-apps"></a>Hospedaje: redireccionamiento de HTTPS habilitado para aplicaciones fuera de proceso de IIS

La versión 13.0.19218.0 del [módulo ASP.NET Core (ANCM)](/aspnet/core/host-and-deploy/aspnet-core-module) para el hospedaje a través de IIS fuera de proceso habilita una característica de redireccionamiento de HTTPS existente para aplicaciones ASP.NET Core 3.0 y 2.2.

Para obtener información, vea [dotnet/AspNetCore#15243](https://github.com/dotnet/AspNetCore/issues/15243).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

La plantilla de proyecto de ASP.NET Core 2.1 incorporó por primera vez compatibilidad con métodos de middleware de HTTPS como <xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection%2A> y <xref:Microsoft.AspNetCore.Builder.HstsBuilderExtensions.UseHsts%2A>. La habilitación del redireccionamiento de HTTPS exigía la adición de configuración, ya que las aplicaciones en desarrollo no usan el puerto predeterminado 443. La [seguridad de transporte estricta de HTTP (HSTS)](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html) solo está activa si la solicitud ya usa HTTPS. Localhost se omite de forma predeterminada.

#### <a name="new-behavior"></a>Comportamiento nuevo

En ASP.NET Core 3.0, el escenario de HTTPS de IIS se ha [mejorado](https://github.com/dotnet/AspNetCore/pull/4685). Con la mejora, una aplicación puede detectar los puertos HTTPS del servidor y hacer que `UseHttpsRedirection` funcione de forma predeterminada. El componente en proceso ha logrado la detección de puertos con la característica `IServerAddresses`, que solo afecta a las aplicaciones ASP.NET Core 3.0, dado que a la biblioteca en proceso se le asigna la versión del marco de trabajo. El componente fuera de proceso ha cambiado para agregar automáticamente la variable de entorno `ASPNETCORE_HTTPS_PORT`. Este cambio afecta a las aplicaciones ASP.NET Core 2.2 y 3.0, ya que el componente fuera de proceso se comparte de forma global. Las aplicaciones ASP.NET Core 2.1 no se ven afectadas porque usan una versión anterior de ANCM de forma predeterminada.

El comportamiento anterior se modificó en ASP.NET Core 3.0.1 y 3.1.0 (versión preliminar 3) a fin de invertir los cambios de comportamiento en ASP.NET Core 2.x. Estos cambios solo afectan a aplicaciones fuera de proceso de IIS.

Como se ha explicado anteriormente, la instalación de ASP.NET Core 3.0.0 tenía el efecto secundario de activar también el middleware de `UseHttpsRedirection` en las aplicaciones ASP.NET Core 2.x. Se ha realizado un cambio en ANCM en ASP.NET Core 3.0.1 y 3.1.0 (versión preliminar 3) que consiste en que su instalación ya no tiene este efecto en las aplicaciones ASP.NET Core 2.x. La variable de entorno `ASPNETCORE_HTTPS_PORT` que ANCM rellenaba en ASP.NET Core 3.0.0 se ha cambiado a `ASPNETCORE_ANCM_HTTPS_PORT` en ASP.NET Core 3.0.1 y 3.1.0 (versión preliminar 3). `UseHttpsRedirection` también se ha actualizado en estas versiones para comprender las variables antiguas y nuevas. ASP.NET Core 2.x no se va a actualizar. Por eso, revierte al comportamiento anterior de estar deshabilitado de forma predeterminada.

#### <a name="reason-for-change"></a>Motivo del cambio

Funcionalidad mejorada de ASP.NET Core 3.0.

#### <a name="recommended-action"></a>Acción recomendada

No es necesario hacer nada si se quiere que todos los clientes usen HTTPS. Para permitir que algunos clientes empleen HTTP, siga uno de los pasos siguientes:

* Quite las llamadas a `UseHttpsRedirection` y `UseHsts` del método `Startup.Configure` del proyecto y vuelva a implementar la aplicación.
* En el archivo *web.config*, establezca la variable de entorno `ASPNETCORE_HTTPS_PORT` en una cadena vacía. Este cambio puede producirse directamente en el servidor sin volver a implementar la aplicación. Por ejemplo:

    ```xml
    <aspNetCore processPath="dotnet" arguments=".\WebApplication3.dll" stdoutLogEnabled="false" stdoutLogFile="\\?\%home%\LogFiles\stdout" >
        <environmentVariables>
        <environmentVariable name="ASPNETCORE_HTTPS_PORT" value="" />
        </environmentVariables>
    </aspNetCore>
    ```

`UseHttpsRedirection` todavía se puede:

* Activar de forma manual en ASP.NET Core 2.x al establecer la variable de entorno `ASPNETCORE_HTTPS_PORT` en el número de puerto correcto (443 en la mayoría de los escenarios de producción).
* Desactivar en ASP.NET Core 3.x al definir `ASPNETCORE_ANCM_HTTPS_PORT` con un valor de cadena vacía. Este valor se establece de la misma manera que en el ejemplo de `ASPNETCORE_HTTPS_PORT` anterior.

Los equipos que ejecutan aplicaciones ASP.NET Core 3.0.0 deben instalar el runtime de ASP.NET Core 3.0.1 antes de instalar el ANCM de ASP.NET Core 3.1.0 (versión preliminar 3). De este modo se garantiza que `UseHttpsRedirection` siga funcionando según lo previsto para las aplicaciones ASP.NET Core 3.0.

En Azure App Service, ANCM se implementa conforme a una programación independiente del runtime debido a su naturaleza global. ANCM se implementó en Azure con estos cambios tras la implementación de ASP.NET Core 3.0.1 y 3.1.0.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection(Microsoft.AspNetCore.Builder.IApplicationBuilder)?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`M:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection(Microsoft.AspNetCore.Builder.IApplicationBuilder)`

-->
