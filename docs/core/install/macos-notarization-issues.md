---
title: Trabajo con la certificación de macOS Catalina
description: Procedimiento para administrar los problemas de certificación con macOS al instalar el runtime de .NET Core, el SDK y las aplicaciones compiladas con .NET Core.
author: adegeo
ms.author: adegeo
ms.date: 02/14/2020
ms.openlocfilehash: 905a8b8a4a17836823b1c6574828acb08110d224
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2020
ms.locfileid: "86415953"
---
# <a name="macos-catalina-notarization-and-the-impact-on-net-core-downloads-and-projects"></a>Certificación de macOS Catalina y el impacto en las descargas y proyectos de .NET Core

A partir de macOS Catalina (versión 10.15), se debe conceder la certificación a todo el software creado después del 1 de junio de 2019 y que se distribuya con el identificador de desarrollador. Este requisito se aplica al runtime de .NET Core, al SDK de .NET Core y al software creado con .NET Core. En este artículo se describen los escenarios comunes con los que puede encontrarse con la certificación de .NET Core y macOS.

## <a name="installing-net-core"></a>Instalación de .NET Core

Desde el 18 de febrero de 2020, se ha concedido la certificación a los instaladores de las versiones 3.1, 3.0 y 2.1 de .NET Core (tanto el runtime como el SDK). A las versiones publicadas anteriores no se les ha concedido la certificación. Puede instalar manualmente una versión de .NET Core sin certificación si descarga primero el instalador y, después, usa el comando `sudo installer`. Para obtener más información, vea [Descarga e instalación manual de macOS](sdk.md?pivots=os-macos#download-and-manually-install).

A partir de las versiones siguientes, los instaladores de .NET Core están certificados:

- Runtime de .NET Core
  - 2.1.16
  - 3.0.3
  - 3.1.2

- SDK de .NET Core
  - 2.1.512
  - 3.0.103
  - 3.1.102

## <a name="apphost-is-disabled-by-default"></a>appHost está deshabilitado de manera predeterminada

De forma predeterminada, las versiones sin certificación del SDK de .NET Core 3.0 y posteriores generan un ejecutable Mach-O nativo (conocido como **appHost**) cuando el proyecto se compila, se publica o se ejecuta. Este ejecutable es una forma cómoda de ejecutar la aplicación. De lo contrario, la aplicación se debe iniciar mediante la ejecución de `dotnet <filename.dll>`. Cuando appHost está habilitado, se invoca el comando `dotnet run` en el contexto de appHost. Para obtener más información, vea [Contexto de appHost](#context-of-the-apphost).

A partir de las versiones con certificación del SDK de .NET Core 3.0 y posteriores, el archivo ejecutable appHost no se genera de forma predeterminada. Puede activar la generación de appHost con el valor booleano [`UseAppHost`](../project-sdk/msbuild-props.md#useapphost) en el archivo del proyecto. También puede alternar appHost con el parámetro `-p:UseAppHost` en la línea de comandos para el comando `dotnet` específico que ejecute:

- Archivo del proyecto

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- Parámetro de línea de comandos

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

Siempre se crea un instancia de appHost al publicar la aplicación de manera [independiente](../deploying/index.md#publish-self-contained).

Para obtener más información sobre la configuración de `UseAppHost`, vea [Propiedades de MSBuild para Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).

### <a name="context-of-the-apphost"></a>Contexto de appHost

Cuando appHost está habilitado en el proyecto y se usa el comando `dotnet run` para ejecutar la aplicación, la aplicación se invoca en el contexto de appHost y no en el host predeterminado (que es el comando `dotnet`). Si appHost está deshabilitado en el proyecto, el comando `dotnet run` ejecuta la aplicación en el contexto del host predeterminado. Incluso si appHost está deshabilitado, la publicación de la aplicación como independiente genera un ejecutable appHost que los usuarios utilizan para ejecutar la aplicación. La ejecución de la aplicación con `dotnet <filename.dll>` invoca la aplicación con el host predeterminado, el entorno de ejecución compartido.

Cuando se invoca una aplicación que usa appHost, la partición de certificado a la que accede la aplicación es diferente del host predeterminado certificado. Si la aplicación tiene que acceder a los certificados instalados a través del host predeterminado, use el comando `dotnet run` para ejecutarla desde su archivo del proyecto, o bien use el comando `dotnet <filename.dll>` para iniciar la aplicación directamente.

En la sección [ASP.NET Core y macOS y los certificados](#aspnet-core-and-macos-and-certificates) se proporciona más información sobre este escenario.

## <a name="aspnet-core-and-macos-and-certificates"></a>ASP.NET Core y macOS y los certificados

.NET Core proporciona la capacidad de administrar certificados en la cadena de claves de macOS con la clase <xref:System.Security.Cryptography.X509Certificates>. El acceso a la cadena de claves de macOS usa la identidad de las aplicaciones como clave principal al decidir qué partición se debe tener en cuenta. Por ejemplo, las aplicaciones sin firmar almacenan secretos en la partición sin firmar, pero las aplicaciones con firma almacenan sus secretos en particiones a las que solo ellas pueden acceder. El origen de ejecución que invoca la aplicación decide qué partición se va a usar.

.NET Core proporciona tres orígenes de ejecución: [appHost](#apphost-is-disabled-by-default), host predeterminado (el comando `dotnet`) y un host personalizado. Cada modelo de ejecución puede tener identidades diferentes, con firma o sin firma, y tiene acceso a diferentes particiones dentro de la cadena de claves. Es posible que los certificados importados por un modo no sean accesibles desde otro. Por ejemplo, las versiones certificadas de .NET Core tienen un host predeterminado que está firmado. Los certificados se importan en una partición segura en función de su identidad. No se puede acceder a estos certificados desde un archivo appHost generado, ya que appHost no está firmado.

Otro ejemplo, de forma predeterminada, ASP.NET Core importa un certificado SSL predeterminado a través del host predeterminado. Las aplicaciones ASP.NET Core que usan appHost no tendrán acceso a este certificado y recibirán un error cuando .NET Core detecte que el certificado no es accesible. El mensaje de error proporciona instrucciones sobre cómo corregir este problema.

Si se requiere el uso compartido de certificados, macOS proporciona opciones de configuración con la utilidad `security`.

Para obtener más información sobre cómo solucionar problemas de certificados de ASP.NET Core, vea [Aplicación de HTTPS en ASP.NET Core](/aspnet/core/security/enforcing-ssl?view=aspnetcore-3.1&tabs=visual-studio#troubleshoot-certificate-problems).

## <a name="default-entitlements"></a>Derechos predeterminados

El host predeterminado de .NET Core (el comando `dotnet`) tiene un conjunto de derechos predeterminados. Estos derechos son necesarios para el funcionamiento correcto de .NET Core. Es posible que la aplicación necesite derechos adicionales, en cuyo caso tendrá que generar y usar un archivo [appHost](#apphost-is-disabled-by-default) y, después, agregar los derechos necesarios de forma local.

Conjunto predeterminado de derechos para .NET Core:

- `com.apple.security.cs.allow-jit`
- `com.apple.security.cs.allow-unsigned-executable-memory`
- `com.apple.security.cs.allow-dyld-environment-variables`
- `com.apple.security.cs.disable-library-validation`

## <a name="notarize-a-net-core-app"></a>Certificación de una aplicación de .NET Core

Si quiere que la aplicación se ejecute en macOS Catalina (versión 10.15) o superior, le interesará certificarla. El archivo appHost que envíe con la aplicación para la certificación se debe usar con al menos los mismos [derechos predeterminados](#default-entitlements) para .NET Core.

## <a name="next-steps"></a>Pasos siguientes

- [Dependencias y requisitos de .NET Core](dependencies.md).
- [Instalación del runtime y SDK de .NET Core](macos.md).
