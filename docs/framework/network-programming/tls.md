---
title: Recomendaciones de seguridad de capa de transporte (TLS) con .NET Framework
description: Describe los procedimientos recomendados mediante seguridad de capa de transporte (TLS) con .NET Framework
ms.date: 03/15/2018
ms.prod: .net-framework
ms.topic: article
helpviewer_keywords:
- sending data, Internet security
- protocols, Internet security
- Network security
- network resources, Internet security
- receiving data, Internet security
- authentication [.NET Framework], Internet security
- Internet, security
- security [.NET Framework], Internet
- permissions [.NET Framework], Internet
author: blowdart
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64829eee5b21a44acb18cbec9b901d77d49cab90
ms.sourcegitcommit: 32172ca05d5dcce7ef3d327b9c8639c736e0fe2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2018
---
# <a name="transport-layer-security-tls-best-practices-with-the-net-framework"></a>Recomendaciones de seguridad de capa de transporte (TLS) con .NET Framework

El protocolo de seguridad de capa de transporte (TLS) es un estándar del sector diseñado para ayudar a proteger la privacidad de la información que se comunican a través de Internet. [TLS 1.2](https://tools.ietf.org/html/rfc5246) es el estándar de lanzamiento más reciente y proporciona mejoras de seguridad con respecto a versiones anteriores. TLS 1.2 finalmente se sustituirán por [1.3 TLS](https://tools.ietf.org/html/draft-ietf-tls-tls13-22). Este artículo presenta recomendaciones para proteger las aplicaciones de .NET Framework que utilizan el protocolo TLS.

Para asegurarse de que las aplicaciones de .NET Framework sean seguras, la versión TLS debe **no** estar codificado de forma rígida. Aplicaciones de .NET framework deben usar la versión TLS que admite el sistema operativo (SO).

Este documento está dirigido a los desarrolladores que están:

- Directamente mediante el <xref:System.Net> API (por ejemplo, <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> y <xref:System.Net.Security.SslStream?displayProperty=nameWithType>).
- Directamente con los clientes de WCF y servicios mediante la <xref:System.ServiceModel?displayProperty=nameWithType> espacio de nombres.
- Usar [servicios en la nube](https://azure.microsoft.com/services/cloud-services/) roles Web y de trabajo para hospedar y ejecutar la aplicación. Consulte la [servicios en la nube](#azure-cloud-services) sección.

Se recomienda:

- Tener como destino .NET Framework 4.7 o versiones posteriores en sus aplicaciones. .NET Framework de destino 4.7.1 o versiones posteriores en las aplicaciones WCF.
- No especifique la versión TLS. Configurar el código para permitir que el sistema operativo decida en la versión TLS.
- Realizar una auditoría completa del código para comprobar que no está especificando una versión TLS o SSL.

Cuando la aplicación permite que el sistema operativo elegir la versión TLS:

- Automáticamente aprovecha de nuevos protocolos agregado en el futuro, por ejemplo, TLS 1.3.
- El sistema operativo bloquea los protocolos que se detectan para que no sea segura.

La sección [auditar el código y realizar cambios de código](#audit-your-code-and-make-code-changes) cubre la auditoría y actualizar el código.

En este artículo se explica cómo habilitar el mayor nivel de seguridad disponible para la versión de .NET Framework que tiene como destino de la aplicación y se ejecuta en. Cuando una aplicación establece explícitamente un protocolo de seguridad y la versión, participar en cualquier otra alternativa y participar en el comportamiento predeterminado de .NET Framework y el sistema operativo. Si desea que la aplicación para poder negociar una conexión TLS 1.2, se establece explícitamente en una versión anterior de TLS impide que una conexión de TLS 1.2.

Si no se pueden evitar codificar una versión del protocolo, recomendamos encarecidamente que especifique TLS 1.2. Para obtener instrucciones sobre cómo identificar y quitar dependencias de TLS 1.0, descargue el [para resolver el problema de TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266) notas del producto.

WCF admite TLS 1.0, 1.1 y 1.2 como el valor predeterminado en .NET Framework 4.7. A partir de .NET Framework 4.7.1, valores predeterminados WCF para el sistema operativo configuran versión. Si una aplicación se configura explícitamente con `SslProtocols.None`, WCF usa la configuración predeterminada del sistema operativo cuando se usa el transporte de NetTcp.

Puede formular alguna pregunta sobre este documento, en el problema de GitHub [recomendaciones de seguridad de capa de transporte (TLS) con .NET Framework](https://github.com/dotnet/docs/issues/4675).

## <a name="audit-your-code-and-make-code-changes"></a>El código de auditoría y realizar cambios de código

Para las aplicaciones ASP.NET, inspeccionar la `<system.web><httpRuntime targetFramework>` elemento de _web.config_ para comprobar que está utilizando la versión deseada de .NET Framework.

Para Windows Forms y otras aplicaciones, consulte [Cómo: elegir como destino una versión de .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).

Use las siguientes secciones para comprobar que no está utilizando una versión específica de TLS o SSL.

## <a name="if-your-app-targets-net-framework-47-or-later-versions"></a>Si la aplicación tiene como destino .NET Framework 4.7 o versiones posteriores

Las secciones siguientes muestran cómo comprobar que no está utilizando una versión específica de TLS o SSL.

### <a name="for-http-networking"></a>Para las redes de HTTP

<xref:System.Net.ServicePointManager>, usando 4.7 de .NET Framework y versiones posteriores, tiene como valor predeterminado para el sistema operativo elegir el mejor protocolo de seguridad y la versión. Para obtener la mejor opción de sistema operativo de forma predeterminada, si es posible, no establezca un valor para el <xref:System.Net.ServicePointManager.SecurityProtocol> propiedad. En caso contrario, establezca esta propiedad en <xref:System.Net.SecurityProtocolType.SystemDefault>.

El resto de este artículo no es relevante cuando el destino es .NET Framework 4.7 o versiones posteriores para las redes de HTTP.

### <a name="for-tcp-sockets-networking"></a>Para los sockets TCP a redes

<xref:System.Net.Security.SslStream>, usando 4.7 de .NET Framework y versiones posteriores, tiene como valor predeterminado para el sistema operativo elegir el mejor protocolo de seguridad y la versión. Para obtener la mejor opción de sistema operativo de forma predeterminada, si es posible, no use las sobrecargas del método de <xref:System.Net.Security.SslStream> que tome un explícita <xref:System.Security.Authentication.SslProtocols> parámetro. De lo contrario, pase <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>. Se recomienda que no use <xref:System.Security.Authentication.SslProtocols.Default>; cuando `SslProtocols.Default` fuerza el uso de SSL 3.0 /TLS 1.0 y evitar TLS 1.2.

No establezca un valor para el <xref:System.Net.ServicePointManager.SecurityProtocol> propiedad (para las redes de HTTP).

No use las sobrecargas del método de <xref:System.Net.Security.SslStream> que tome un explícita <xref:System.Security.Authentication.SslProtocols> parámetro (para redes de sockets TCP). Al cambiar el destino de la aplicación para .NET Framework 4.7 o versiones posteriores, que podrá siguiendo las prácticas recomendadas.

El resto de este tema no es relevante cuando como destino .NET Framework 4.7 o versiones posteriores para TCP sockets de red.

<a name="wcf-tcp-cert"></a>

### <a name="for-wcf-tcp-transport-using-transport-security-with-certificate-credentials"></a>Para TCP de WCF de transporte mediante la seguridad de transporte con credenciales de certificado

WCF usa la misma pila de red que el resto de .NET Framework.

Si desea usar 4.7.1, WCF está configurado para permitir que el sistema operativo elegir el mejor protocolo de seguridad de forma predeterminada a menos que se configure explícitamente:

- En el archivo de configuración de la aplicación.
- **O**, en la aplicación en el código fuente.

De forma predeterminada, 4.7 de .NET Framework y versiones posteriores se configura para usar TLS 1.2 y permite las conexiones que usan TLS 1.1 o TLS 1.0. Configurar WCF para permitir que el sistema operativo elegir el mejor protocolo de seguridad mediante la configuración de su enlace para usar <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>. Esto se puede establecer en <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols>. `SslProtocols.None` puede tener acceso desde <xref:System.ServiceModel.NetTcpSecurity.Transport>. `NetTcpSecurity.Transport` puede tener acceso desde <xref:System.ServiceModel.NetTcpBinding.Security>.

Si usa un enlace personalizado:

- Configurar WCF para permitir que el sistema operativo elegir el mejor protocolo de seguridad estableciendo <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols> usar <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>.
- **O** configurar el protocolo utilizado con la ruta de acceso de configuración `system.serviceModel/bindings/customBinding/binding/sslStreamSecurity:sslProtocols`.

Si le **no** mediante un enlace personalizado **y** está configurando el enlace de WCF mediante configuración, establezca el protocolo utilizado con la ruta de acceso de configuración `system.serviceModel/bindings/netTcpBinding/binding/security/transport:sslProtocols`.

### <a name="for-wcf-message-security-with-certificate-credentials"></a>Para la seguridad de mensaje de WCF con credenciales de certificado

4.7 de .NET framework y versiones posteriores de forma predeterminada usa el protocolo especificado en el <xref:System.Net.ServicePointManager.SecurityProtocol> propiedad. Cuando el [AppContextSwitch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) `Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols` se establece en `true`, WCF elige el mejor protocolo hasta TLS 1.0.

## <a name="if-your-app-targets-a-net-framework-version-earlier-than-47"></a>Si la aplicación tiene como destino una versión de .NET Framework anteriores a 4.7

Auditar el código para comprobar que no se está estableciendo una versión específica de TLS o SSL mediante las siguientes secciones:

### <a name="for-net-framework-46---462-and-not-wfc"></a>Para .NET Framework 4.6 - 4.6.2 y no de WFC

Establecer el `DontEnableSystemDefaultTlsVersions` `AppContext` cambie a `false`. Vea [configuración de seguridad a través de conmutadores AppContext](#configuring-security-via-appcontext-switches).

### <a name="for-wcf-using-net-framework-46---462-using-tcp-transport-security-with-certificate-credentials"></a>Para WCF mediante el uso de .NET Framework 4.6 - 4.6.2 con seguridad de transporte TCP con credenciales de certificado

Debe instalar las revisiones más recientes del sistema operativo. Vea [las actualizaciones de seguridad](#security-updates).

El marco de trabajo WCF elige automáticamente el protocolo más alto disponible hasta TLS 1.2 a menos que configure explícitamente una versión de protocolo. Para obtener más información, consulte la sección anterior [transporte TCP de WCF para usar seguridad de transporte con credenciales de certificado](#wcf-tcp-cert).

### <a name="for-net-framework-35---451-and-not-wcf"></a>Para .NET Framework 3.5 - 4.5.1 y no WCF

Se recomienda que actualizar la aplicación a .NET Framework 4.7 o versiones posteriores. Si no se puede actualizar, siga estos pasos. En algún momento en el futuro, la aplicación puede producir un error hasta que actualice a .NET Framework 4.7 o versiones posteriores.

Establecer el [SchUseStrongCrypto](#schusestrongcrypto) y [SystemDefaultTlsVersions](#systemdefaulttlsversions) las claves del registro en 1. Vea [configuración de seguridad a través del registro de Windows](#configuring-security-via-the-windows-registry). La versión 3.5 de .NET Framework admite la `SchUseStrongCrypto` marca solo cuando se pasa un valor explícito de TLS.

Si se ejecutan en .NET Framework 3.5, debe instalar una revisión activa para que TLS 1.2 pueden especificarse por el programa:

| [KB3154518](https://support.microsoft.com/kb/3154518) | Recursos humanos de acumulación de confiabilidad-1605 - compatibilidad con las versiones predeterminado del sistema TLS incluida en .NET Framework 3.5.1 en Windows 7 SP1 y Server 2008 R2 SP1 |
| --- | --- |
| [KB3154519](https://support.microsoft.com/kb/3154519) | Paquete acumulativo de actualizaciones de confiabilidad HR-1605 - compatibilidad con TLS predeterminado las versiones del sistema incluido en .NET Framework 3.5 en Windows Server 2012 |
| [KB3154520](https://support.microsoft.com/kb/3154520) | Paquete acumulativo de actualizaciones de confiabilidad HR-1605 - compatibilidad con las versiones predeterminado del sistema TLS incluida en .NET Framework 3.5 en Windows 8.1 y Windows Server 2012 R2 |
| [KB3156421](https://support.microsoft.com/kb/3156421) | Paquete acumulativo de revisiones de 1605 3154521 para .NET Framework 4.5.2 y 4.5.1 en Windows |

### <a name="for-wcf-using-net-framework-35---452-using-tcp-transport-security-with-certificate-credentials"></a>Para WCF mediante el uso de .NET Framework 3.5 - 4.5.2 con seguridad de transporte TCP con credenciales de certificado

Estas versiones de framework WCF están codificados para utilizar valores SSL 3.0 y TLS 1.0. No se puede cambiar estos valores. Debe actualizar y redestinar a .NET Framework 4.6 o versiones posteriores para usar TLS 1.1 y 1.2.

## <a name="if-your-app-targets-net-framework-35"></a>Si la aplicación tiene como destino .NET Framework 3.5

Si se debe establecer explícitamente un protocolo de seguridad en lugar de permitir la selección de sistema operativo y de .NET framework el protocolo de seguridad, agregue `SecurityProtocolTypeExtensions` y `SslProtocolsExtension` enumeraciones en el código. `SecurityProtocolTypeExtensions` y `SslProtocolsExtension` incluya valores para `Tls12`, `Tls11`y el `SystemDefault` valor. Vea [compatibilidad con TLS predeterminado las versiones del sistema incluido en .NET Framework 3.5 en Windows 8.1 y Windows Server 2012 R2](https://support.microsoft.com/help/3154520/support-for-tls-system-default-versions-included-in-the--net-framework).

<a name="configuring-security-via-appcontext-switches"></a>

## <a name="configuring-security-via-appcontext-switches-for-net-framework-46-or-later-versions"></a>Configuración de seguridad a través de AppContext se activa (para .NET Framework 4.6 o versiones posteriores)

El [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) conmutadores descritos en esta sección son relevantes si su aplicación tiene como destino, o se ejecuta en .NET Framework 4.6 o versiones posteriores. Si de forma predeterminada, o estableciendo explícitamente ellos, los conmutadores deben ser `false` si es posible. Si desea configurar la seguridad a través de uno o dos conmutadores, a continuación, no especifique un valor de protocolo de seguridad en el código; al hacerlo así invalidaría el/los conmutadores.

Los modificadores tienen el mismo efecto si se está realizando las redes HTTP (<xref:System.Net.ServicePointManager>) o redes de sockets TCP (<xref:System.Net.Security.SslStream>).

### <a name="switchsystemnetdontenableschusestrongcrypto"></a>Switch.System.Net.DontEnableSchUseStrongCrypto

Un valor de `false` para `Switch.System.Net.DontEnableSchUseStrongCrypto` hace que la aplicación para utilizar criptografía fuerte. Un valor de `false` para `DontEnableSchUseStrongCrypto` usa protocolos de red más seguros (TLS 1.2, TLS 1.1 y TLS 1.0) y protocolos que no son seguras se bloquea. Para obtener más información, consulte [marca el SCH_USE_STRONG_CRYPTO](#the-schusestrongcrypto-flag). Un valor de `true` deshabilita la criptografía fuerte para la aplicación.

Si la aplicación tiene como destino .NET Framework 4.6 o versiones posteriores, este modificador predeterminado `false`. Que es un valor predeterminado seguro, que se recomienda. Si la aplicación se ejecuta en .NET Framework 4.6, pero tiene como destino una versión anterior, el modificador predeterminado `true`. En ese caso, debe establecerse explícitamente lo `false`.

`DontEnableSchUseStrongCrypto` solo debe tener un valor de `true` si necesita conectarse a servicios heredados que no son compatibles con la criptografía segura y no se puede actualizar.

### <a name="switchsystemnetdontenablesystemdefaulttlsversions"></a>Switch.System.Net.DontEnableSystemDefaultTlsVersions

Un valor de `false` para `Switch.System.Net.DontEnableSystemDefaultTlsVersions` hace que la aplicación permitir que el sistema operativo elegir el protocolo. Un valor de `true` hace que la aplicación para utilizar protocolos detectados de .NET Framework.

Si la aplicación tiene como destino .NET Framework 4.7 o versiones posteriores, este modificador predeterminado `false`. Que es un valor predeterminado seguro que se recomienda. Si la aplicación se ejecuta en .NET Framework 4.7 o versiones posteriores, pero tiene como destino una versión anterior, el modificador predeterminado `true`. En ese caso, debe establecerse explícitamente lo `false`.

### <a name="switchsystemservicemodeldisableusingservicepointmanagersecurityprotocols"></a>Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols

Un valor de `false` para `Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols` hace que la aplicación para usar el valor definido en `ServicePointManager.SecurityProtocols` de seguridad de mensajes mediante credenciales de certificado. Un valor de `true` usa el protocolo más alto disponible hasta TLS 1.0

Para las aplicaciones destinadas a .NET Framework 4.7 y versiones posteriores, el valor predeterminado es `false`. Para las aplicaciones dirigidas a .NET Framework 4.6.2 y versiones anteriores, el valor predeterminado es `true`.

### <a name="switchsystemservicemodeldontenablesystemdefaulttlsversions"></a>Switch.System.ServiceModel.DontEnableSystemDefaultTlsVersions

Un valor de `false` para `Switch.System.ServiceModel.DontEnableSystemDefaultTlsVersions` establece la configuración predeterminada para permitir que el sistema operativo elegir el protocolo. Un valor de `true` establece el valor predeterminado para el protocolo más alto disponible hasta TLS 1.2.

Para las aplicaciones destinadas a .NET Framework 4.7.1 y versiones posteriores, el valor predeterminado es `false`. Para las aplicaciones dirigidas a .NET Framework 4,7 y versiones anterior, el valor predeterminado es `true`.

Para obtener más información acerca de los protocolos TLS, consulte [mitigación: protocolos TLS](../migration-guide/mitigation-tls-protocols.md). Para obtener más información acerca de `AppContext` conmutadores, consulte [ `<AppContextSwitchOverrides> Element` ](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

## <a name="configuring-security-via-the-windows-registry"></a>Configuración de seguridad a través del registro de Windows

Si se establecen una o ambas `AppContext` modificadores no son una opción, puede controlar los protocolos de seguridad que usa su aplicación con las claves de registro de Windows se describe en esta sección. No puede utilizar uno o ambos el `AppContext` se activa si la aplicación tiene como destino una versión de .NET Framework anteriores a 4.6 o no se puede editar el archivo de configuración. Si desea configurar la seguridad con el registro, a continuación, no especifique un valor de protocolo de seguridad en el código; al hacerlo así invalidaría el registro.

Los nombres de las claves del registro son similares a los nombres de los correspondientes `AppContext` activa pero sin un `DontEnable` antepone al nombre. Por ejemplo, el `AppContext` cambiar `DontEnableSchUseStrongCrypto` se llama a la clave del registro [SchUseStrongCrypto](#schusestrongcrypto).

Estas claves están disponibles en todas las versiones de .NET Framework para el que hay una revisión de seguridad recientes. Vea [las actualizaciones de seguridad](#security-updates).

Todas las claves del registro que se describe a continuación tienen el mismo efecto si se está realizando las redes HTTP (<xref:System.Net.ServicePointManager>) o redes de sockets TCP (<xref:System.Net.Security.SslStream>).

### <a name="schusestrongcrypto"></a>SchUseStrongCrypto

El `HKEY_LOCAL_MACHINE\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\<VERSION>: SchUseStrongCrypto` clave del registro tiene un valor de tipo DWORD. Un valor de 1 hace que la aplicación para utilizar criptografía fuerte. La criptografía fuerte usa protocolos de red más seguros (TLS 1.2, TLS 1.1 y TLS 1.0) y protocolos que no son seguras bloquea. Un valor de 0 deshabilita la criptografía fuerte. Para obtener más información, consulte [marca el SCH_USE_STRONG_CRYPTO](#the-schusestrongcrypto-flag).

Si la aplicación tiene como destino .NET Framework 4.6 o versiones posteriores, el valor predeterminado de esta clave es un valor de 1. Que es un valor predeterminado seguro que se recomienda. Si la aplicación se ejecuta en .NET Framework 4.6, pero tiene como destino una versión anterior, la clave de valor predeterminado es 0. En ese caso, debe establecer explícitamente su valor en 1.

Esta clave sólo debe tener un valor de 0 si se necesita para conectarse a servicios heredados que no son compatibles con la criptografía segura y no se puede actualizar.

### <a name="systemdefaulttlsversions"></a>SystemDefaultTlsVersions

El `HKEY_LOCAL_MACHINE\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\<VERSION>: SystemDefaultTlsVersions` clave del registro tiene un valor de tipo DWORD. Un valor de 1 hace que la aplicación permitir que el sistema operativo elegir el protocolo. Un valor de 0 hace que la aplicación para utilizar protocolos detectados de .NET Framework.

`<VERSION>` debe ser v4.0.30319 (para .NET Framework 4 y versiones posteriores) o v2.0.50727 (para .NET Framework 3.5).

Si la aplicación tiene como destino .NET Framework 4.7 o versiones posteriores, el valor predeterminado de esta clave es un valor de 1. Que es un valor predeterminado seguro que se recomienda. Si la aplicación se ejecuta en .NET Framework 4.7 o versiones posteriores, pero tiene como destino una versión anterior, el valor predeterminado de la clave es 0. En ese caso, debe establecer explícitamente su valor en 1.

Para obtener más información, consulte [acumulativa 10 versión 1511 de actualización para Windows y Windows Server 2016 Technical Preview 4: 10 de mayo de 2016](https://support.microsoft.com/help/3156421/cumulative-update-for-windows-10-version-1511-and-windows-server-2016).

Para obtener más información con .NET framework 3.5.1, consulte [compatibilidad con TLS predeterminado las versiones del sistema incluido en .NET Framework 3.5.1 en Windows 7 SP1 y Server 2008 R2 SP1](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the--net-framework).

La siguiente _. REG_ archivo establece las claves del registro y sus variantes con sus valores más seguros:

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\v2.0.50727]
"SystemDefaultTlsVersions"=dword:00000001
"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\v4.0.30319]
"SystemDefaultTlsVersions"=dword:00000001
"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]
"SystemDefaultTlsVersions"=dword:00000001
"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]
"SystemDefaultTlsVersions"=dword:00000001
"SchUseStrongCrypto"=dword:00000001
```

## <a name="configuring-schannel-protocols-in-the-windows-registry"></a>Configurar protocolos de Schannel en el registro de Windows

Puede utilizar el registro de control más preciso sobre los protocolos que se negocia la aplicación cliente o del servidor. Las redes de la aplicación pasa a través de Schannel (que es otro nombre para [canal seguro](https://msdn.microsoft.com/library/windows/desktop/aa380123). Mediante la configuración de `Schannel`, puede configurar el comportamiento de la aplicación.

Comience con la `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols` clave del registro. Bajo esa clave se pueden crear todas las subclaves en el conjunto de `SSL 2.0`, `SSL 3.0`, `TLS 1.0`, `TLS 1.1`, y `TLS 1.2`. En cada una de las subclaves, puede crear subclaves `Client` o `Server`. En `Client` y `Server`, puede crear valores DWORD `DisabledByDefault` (0 o 1) y `Enabled` (0 ó 0xFFFFFFFF).

## <a name="the-schusestrongcrypto-flag"></a>La marca SCH_USE_STRONG_CRYPTO

Cuando está habilitada (de forma predeterminada, por un `AppContext` cambia, o por el registro de Windows), .NET Framework usa el `SCH_USE_STRONG_CRYPTO` marca cuando la aplicación solicita un protocolo de seguridad TLS. El `SCH_USE_STRONG_CRYPTO` puede estar habilitada la marca de forma predeterminada, con el `AppContext` cambia, o con el registro. El sistema operativo pasa la marca a `Schannel`para indicarle que se va a deshabilitar algoritmos criptográficos conocidos, cifrado conjuntos y las versiones de protocolo TLS/SSL pueden habilitarse en caso contrario, para mejorar la interoperabilidad. Para obtener más información, consulte:

- [Canal seguro](https://msdn.microsoft.com/library/windows/desktop/aa380123)
- [Estructura SCHANNEL_CRED](https://msdn.microsoft.com/library/windows/desktop/aa379810)

El `SCH_USE_STRONG_CRYPTO` marca también se pasa a `Schannel` cuando se utilizan explícitamente la `Tls` (TLS 1.0), `Tls11`, o `Tls12` enumerar valores de <xref:System.Net.SecurityProtocolType> o <xref:System.Security.Authentication.SslProtocols>.

## <a name="security-updates"></a>Actualizaciones de seguridad

Los procedimientos recomendados en este artículo dependen de las actualizaciones de seguridad recientes que se va a instalar. Estas actualizaciones incluyen la capacidad de usar avanzadas .NET Framework 4.7 y las características más adelante. Actualizaciones de seguridad recientes son importantes si la aplicación se ejecuta en .NET Framework 4.7 y versiones posteriores (incluso si tiene como destino una versión anterior).

Para actualizar .NET Framework para permitir que el sistema operativo elegir la mejor versión de TLS para usar, debe instalar al menos:

- El [vista previa de agosto de 2017 de .NET Framework del paquete acumulativo de actualizaciones de calidad](https://blogs.msdn.microsoft.com/dotnet/2017/08/16/net-framework-august-2017-preview-of-quality-rollup).
- **O** el [septiembre de 2017 seguridad de .NET Framework y el paquete acumulativo de actualizaciones de calidad](https://blogs.msdn.microsoft.com/dotnet/2017/09/12/net-framework-september-2017-security-and-quality-rollup).

Vea también:

- [Dependencias y versiones de .NET framework](../migration-guide/versions-and-dependencies.md)
- [Cómo: determinar qué versiones de .NET Framework están instaladas](../migration-guide/how-to-determine-which-versions-are-installed.md).

## <a name="support-for-tls-12"></a>Compatibilidad con TLS 1.2

Para que la aplicación en la negociación de TLS 1.2, el sistema operativo y la versión de .NET Framework, ambas deben admitir TLS 1.2.

**Requisitos del sistema operativo para admitir TLS 1.2**

Para habilitar o volver a habilitar TLS 1.2 o TLS 1.1 en un sistema que es compatible con ellos, consulte [configuración del registro de seguridad de capa de transporte (TLS)](/windows-server/security/tls/tls-registry-settings).

| **OS** | **Soporte de TLS 1.2** |
| --- | --- |
| Windows 10</br>Windows Server 2016 | Admite y habilita de forma predeterminada. |
| Windows 8.1</br>Windows Server 2012 R2 | Admite y habilita de forma predeterminada. |
| Windows 8.0</br>Windows Server 2012 | Admite y habilita de forma predeterminada. |
| Windows 7 SP1</br>Windows Server 2008 R2 SP1 | Admite, pero no está habilitada de forma predeterminada. Consulte la [configuración del registro de seguridad de capa de transporte (TLS)](/windows-server/security/tls/tls-registry-settings) página web para obtener más información sobre cómo habilitar TLS 1.2. |
| Windows Server 2008 | Compatibilidad con TLS 1.2 y TLS 1.1 requiere una actualización. Vea [actualización para agregar compatibilidad con TLS 1.1 y 1.2 de TLS en Windows Server 2008 SP2](https://support.microsoft.com/help/4019276/update-to-add-support-for-tls-1-1-and-tls-1-2-in-windows-server-2008-s). |
| Windows Vista | No se admite. |

Para obtener información acerca de qué TLS/SSL protocolos están habilitados de forma predeterminada en cada versión de Windows, vea [protocolos en TLS/SSL (Schannel SSP)](https://msdn.microsoft.com/library/windows/desktop/mt808159).

**Requisitos para la compatibilidad con TLS 1.2 con .NET Framework 3.5**

Esta tabla muestra la actualización de sistema operativo que debe admitir TLS 1.2 con .NET Framework 3.5. Se recomienda que aplicar todas las actualizaciones del sistema operativo.

| **OS** | **Actualización mínima necesaria para admitir TLS 1.2 con .NET Framework 3.5** |
| --- | --- |
| Windows 10</br>Windows Server 2016 | [La actualización acumulativa para Windows 10 versión 1511 y Windows Server 2016 Technical Preview 4: 10 de mayo de 2016](https://support.microsoft.com/help/3156421/cumulative-update-for-windows-10-version-1511-and-windows-server-2016) |
| Windows 8.1</br>Windows Server 2012 R2 | [Compatibilidad con TLS predeterminado las versiones del sistema incluido en .NET Framework 3.5 en Windows 8.1 y Windows Server 2012 R2](https://support.microsoft.com/help/3154520/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows 8.0</br>Windows Server 2012 | [Compatibilidad con TLS predeterminado las versiones del sistema incluido en .NET Framework 3.5 en Windows Server 2012](https://support.microsoft.com/help/3154519/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows 7 SP1</br>Windows Server 2008 R2 SP1 | [Compatibilidad con TLS predeterminado las versiones del sistema incluido en .NET Framework 3.5.1 en Windows 7 SP1 y Server 2008 R2 SP1](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows Server 2008 | [Compatibilidad con TLS predeterminado las versiones del sistema incluido en .NET Framework 2.0 SP2 en Windows Vista SP2 y Server 2008 SP2](https://support.microsoft.com/help/3154517/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows Vista | No compatibles |

## <a name="azure-cloud-services"></a>Servicios de nube de Azure

Si utilizas [servicios en la nube](https://azure.microsoft.com/services/cloud-services/) roles Web y de trabajo para hospedar y ejecutar la aplicación, hay algunas consideraciones que debe tener en cuenta al soporte técnico de TLS 1.2.

### <a name="net-framework-47-is-not-installed-on-azure-guest-os-by-default"></a>4.7 de .NET framework no está instalado en el SO invitado de Azure de forma predeterminada

La última versión instalada en la versión más reciente de Azure de la familia de SO invitado 5 (Windows Server 2016) es 4.6.2. Para ver qué versiones de .NET Framework están instaladas en cada sistema operativo invitado de Azure, consulte la [versiones del SO invitado de Azure y la matriz de compatibilidad SDK](https://docs.microsoft.com/azure/cloud-services/cloud-services-guestos-update-matrix).

Si la aplicación tiene como destino una versión de .NET Framework que no está disponible en la versión de SO invitado de Azure, debe instalarlo usted mismo. Vea [instale .NET en los Roles de servicio de nube de Azure](https://docs.microsoft.com/azure/cloud-services/cloud-services-dotnet-install-dotnet). Si la instalación de framework requiere un reinicio, los roles de servicio también podrían reiniciarse antes de entrar en el estado listo.

### <a name="azure-guest-os-registry-settings"></a>Configuración de registro de SO invitado de Azure

El sistema operativo invitado de Azure de la imagen para [servicios en la nube](https://azure.microsoft.com/services/cloud-services/) ya tiene la `SchUseStrongCrypto` clave del registro se establece en un valor de 1. Para obtener más información, consulte [SchUseStrongCrypto](#schusestrongcrypto).

Establecer el [SystemDefaultTlsVersions](#systemdefaulttlsversions) clave del registro en 1. Vea [configuración de seguridad a través del registro de Windows](#configuring-security-via-the-windows-registry).
