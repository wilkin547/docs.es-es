---
title: Procedimientos recomendados sobre la seguridad de la capa de transporte (TLS) con .NET Framework
description: Describe los procedimientos recomendados al utilizar la seguridad de capa de transporte (TLS) con .NET Framework.
ms.date: 10/22/2018
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
ms.openlocfilehash: bae6bf6a1a5d87241b619bf024c099c48af6af43
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452687"
---
# <a name="transport-layer-security-tls-best-practices-with-the-net-framework"></a>Procedimientos recomendados sobre la seguridad de la capa de transporte (TLS) con .NET Framework

El protocolo de seguridad de capa de transporte (TLS) es un estándar del sector diseñado para ayudar a proteger la privacidad de la información que se comunica a través de Internet. [TLS 1.2](https://tools.ietf.org/html/rfc5246) es un estándar que proporciona mejoras de seguridad con respecto a versiones anteriores. TLS 1.2, finalmente, se reemplazará por el estándar más reciente publicado [TLS 1.3](https://tools.ietf.org/html/rfc8446) que es más rápido y ha mejorado la seguridad. En este artículo se presentan recomendaciones para proteger las aplicaciones de .NET Framework que utilizan el protocolo TLS.

Para garantizar que las aplicaciones de .NET Framework permanezcan seguras, la versión de TLS **no** debe estar codificada de forma rígida. Las aplicaciones de .NET Framework deben usar la versión TLS que admita el sistema operativo (SO).

Este documento está dirigido a los desarrolladores que:

- Utilizan directamente las API <xref:System.Net> (por ejemplo, <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> y <xref:System.Net.Security.SslStream?displayProperty=nameWithType>).
- Utilizan directamente clientes y servicios de WCF mediante el espacio de nombres <xref:System.ServiceModel?displayProperty=nameWithType>.
- Utilizan los roles web y de trabajo de [Azure Cloud Services](https://azure.microsoft.com/services/cloud-services/) para hospedar y ejecutar la aplicación. Consulte la sección [Azure Cloud Services](#azure-cloud-services).

Le recomendamos lo siguiente:

- Tenga como destino .NET Framework 4.7 o versiones posteriores en sus aplicaciones. Tenga como destino .NET Framework 4.7.1 o versiones posteriores en sus aplicaciones de WCF.
- No especifique la versión de TLS. Configure el código para permitir que el sistema operativo decida sobre la versión de TLS.
- Realice una exhaustiva revisión del código para comprobar que no está especificando una versión de TLS o SSL.

Cuando la aplicación permite que el sistema operativo elija la versión de TLS:

- Aprovecha automáticamente los nuevos protocolos que se agregarán en el futuro; por ejemplo, TLS 1.3.
- El sistema operativo bloquea los protocolos que se descubre que no son seguros.

La sección [Revisión del código y aplicación de cambios en el código](#audit-your-code-and-make-code-changes) trata la auditoría y la actualización de código.

En este artículo se explica cómo habilitar el mayor nivel de seguridad disponible para la versión de .NET Framework que tiene como destino la aplicación y en la que esta se ejecuta. Cuando una aplicación establece explícitamente un protocolo de seguridad y una versión, deja de recibir cualquier otra alternativa y se mantiene al margen del comportamiento predeterminado de .NET Framework y el sistema operativo. Si desea que la aplicación pueda negociar una conexión TLS 1.2, el establecimiento explícito de una versión de TLS anterior impide una conexión de TLS 1.2.

Si no puede evitar la codificación rígida de una versión del protocolo, le recomendamos encarecidamente que especifique TLS 1.2. Para obtener instrucciones sobre cómo identificar y quitar dependencias de TLS 1.0, descargue el documento [Solución del problema de TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266).

WCF admite TLS 1.0, 1.1 y 1.2 como valor predeterminado en .NET Framework 4.7. A partir de .NET Framework 4.7.1, WCF toma como valor predeterminado la versión configurada en el sistema operativo. Si una aplicación se configura explícitamente con `SslProtocols.None`, WCF utiliza los parámetros predeterminados del sistema operativo al utilizar el transporte NetTcp.

Puede formular preguntas sobre este documento en el tema de GitHub [Procedimientos recomendados sobre la seguridad de la capa de transporte (TLS) con .NET Framework](https://github.com/dotnet/docs/issues/4675).

## <a name="audit-your-code-and-make-code-changes"></a>Revisión del código y aplicación de cambios en el código

Para las aplicaciones ASP.NET, inspeccione el elemento `<system.web><httpRuntime targetFramework>` de _web.config_ para comprobar que está utilizando la versión deseada de .NET Framework.

Para Windows Forms y otras aplicaciones, consulte [Cómo: usar una versión de .NET Framework como destino](/visualstudio/ide/visual-studio-multi-targeting-overview).

Consulte las siguientes secciones para comprobar que no está utilizando una versión específica de TLS o SSL.

## <a name="if-your-app-targets-net-framework-47-or-later-versions"></a>Si la aplicación tiene como destino .NET Framework 4.7 o versiones posteriores

En las siguientes secciones se muestra cómo comprobar que no está utilizando una versión específica de TLS o SSL.

### <a name="for-http-networking"></a>Para las redes de HTTP

<xref:System.Net.ServicePointManager>, con .NET Framework 4.7 y versiones posteriores, usará el protocolo de seguridad predeterminado configurado en el sistema operativo. Para obtener la mejor opción de sistema operativo de forma predeterminada, si es posible, no establezca un valor para la propiedad <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>, que adopta como predeterminado <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType>.

Dado que el valor <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType> hace que <xref:System.Net.ServicePointManager> use el protocolo de seguridad predeterminado configurado por el sistema operativo, la aplicación puede ejecutarse de forma diferente en función del sistema operativo en el que se ejecuta. Por ejemplo, Windows 7 SP1 usa TLS 1.0, mientras que Windows 8 y Windows 10 usan TLS 1.2.

El resto de este artículo no es pertinente si se toma como destino la versión .NET Framework 4.7 o una posterior para las redes de HTTP.

### <a name="for-tcp-sockets-networking"></a>Para las redes de sockets de TCP

<xref:System.Net.Security.SslStream>, que usa .NET Framework 4.7 y versiones posteriores, elige el sistema operativo predeterminado teniendo en cuenta la mejor opción en cuanto a protocolo de seguridad y versión. Para obtener la mejor opción de sistema operativo predeterminado, si es posible, no use las sobrecargas del método de <xref:System.Net.Security.SslStream> que toman un parámetro <xref:System.Security.Authentication.SslProtocols> explícito. De lo contrario, pase <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>. Se recomienda no usar <xref:System.Security.Authentication.SslProtocols.Default>; el parámetro `SslProtocols.Default` fuerza el uso de SSL 3.0/TLS 1.0 y evita TLS 1.2.

No establezca un valor para la propiedad <xref:System.Net.ServicePointManager.SecurityProtocol> (para las redes de HTTP).

No use las sobrecargas del método de <xref:System.Net.Security.SslStream> que toman un parámetro <xref:System.Security.Authentication.SslProtocols> explícito (para redes de sockets TCP). Al cambiar el destino de la aplicación a .NET Framework 4.7 o versiones posteriores, estará siguiendo la recomendación de los procedimientos recomendados.

El resto de este tema no es pertinente si se toma como destino la versión .NET Framework 4.7 o una posterior para las redes de sockets TCP.

<a name="wcf-tcp-cert"></a>

### <a name="for-wcf-tcp-transport-using-transport-security-with-certificate-credentials"></a>Para transporte TCP de WCF que usa seguridad de transporte con credenciales de certificado

WCF usa la misma pila de redes que el resto de .NET Framework.

Si tiene como destino 4.7.1, WCF está configurado para permitir que el sistema operativo elija el mejor protocolo de seguridad de forma predeterminada a menos que se configure explícitamente:

- En el archivo de configuración de aplicación.
- **O bien**, en el código fuente de la aplicación.

De forma predeterminada, .NET Framework 4.7, así como las versiones posteriores, está configurado para usar TLS 1.2 y permite conexiones con TLS 1.1 o TLS 1.0. Configure WCF para permitir que el sistema operativo elija el mejor protocolo de seguridad mediante la configuración de su enlace para usar <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>. Se puede establecer en <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols>. Se puede tener acceso a `SslProtocols.None` desde <xref:System.ServiceModel.NetTcpSecurity.Transport>. Se puede tener acceso a `NetTcpSecurity.Transport` desde <xref:System.ServiceModel.NetTcpBinding.Security>.

Si usa un enlace personalizado:

- Configure WCF para permitir que el sistema operativo elija el mejor protocolo de seguridad configurando <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols> para que utilice <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>.
- **O bien** configure el protocolo utilizado con la ruta de acceso de configuración `system.serviceModel/bindings/customBinding/binding/sslStreamSecurity:sslProtocols`.

Si **no** utiliza un enlace personalizado **y** está estableciendo los ajustes del enlace de WCF con la configuración, determine el protocolo utilizado con la ruta de acceso de configuración `system.serviceModel/bindings/netTcpBinding/binding/security/transport:sslProtocols`.

### <a name="for-wcf-message-security-with-certificate-credentials"></a>Para la seguridad de mensaje de WCF con credenciales de certificado

.NET Framework 4.7, así como sus versiones posteriores, utiliza de forma predeterminada el protocolo especificado en la propiedad <xref:System.Net.ServicePointManager.SecurityProtocol>. Cuando `Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols` de [AppContextSwitch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) se establece en `true`, WCF elige el mejor protocolo hasta TLS 1.0.

## <a name="if-your-app-targets-a-net-framework-version-earlier-than-47"></a>Si la aplicación tiene como destino una versión de .NET Framework anterior a 4.7

Siga estas secciones para examinar el código a fin de comprobar que no está configurando una versión específica de TLS o SSL:

### <a name="for-net-framework-46---462-and-not-wcf"></a>Para .NET Framework 4.6 - 4.6.2 y no WFC

Establezca el conmutador `DontEnableSystemDefaultTlsVersions` `AppContext` en `false`. Vea [Configuring security via AppContext switches](#configuring-security-via-appcontext-switches) (Configuración de la seguridad mediante conmutadores AppContext).

### <a name="for-wcf-using-net-framework-46---462-using-tcp-transport-security-with-certificate-credentials"></a>Para WCF que usa .NET Framework 4.6 - 4.6.2 y seguridad de transporte TCP con credenciales de certificado

Debe instalar las revisiones más recientes del sistema operativo. Consulte [Actualizaciones de seguridad](#security-updates).

La plataforma de WCF elige automáticamente el protocolo más alto disponible hasta TLS 1.2, a menos que configure explícitamente una versión de protocolo. Para obtener más información, consulte la sección anterior [Para transporte TCP de WCF que usa seguridad de transporte con credenciales de certificado](#wcf-tcp-cert).

### <a name="for-net-framework-35---452-and-not-wcf"></a>Para .NET Framework 3.5 - 4.5.2 y no WCF

Se recomienda que actualice la aplicación a .NET Framework 4.7 o versiones posteriores. Si no puede actualizar, siga estos pasos. En algún momento en el futuro, la aplicación puede producir un error hasta que actualice a .NET Framework 4.7 o versiones posteriores.

Establezca las claves del Registro [SchUseStrongCrypto](#schusestrongcrypto) y [SystemDefaultTlsVersions](#systemdefaulttlsversions) en 1. Vea [Configuración de seguridad mediante el Registro de Windows](#configuring-security-via-the-windows-registry). La versión 3.5 de .NET Framework admite la marca `SchUseStrongCrypto` solo cuando se pasa un valor explícito de TLS.

Si está ejecutando en .NET Framework 3.5, debe instalar una revisión para que pueda especificarse TLS 1.2 por el programa:

| [KB3154518](https://support.microsoft.com/kb/3154518) | Paquete acumulativo de actualizaciones de confiabilidad HR-1605: compatibilidad para versiones predeterminadas del sistema TLS incluidas en .NET Framework 3.5.1 en Windows 7 SP1 y Server 2008 R2 SP1 |
| --- | --- |
| [KB3154519](https://support.microsoft.com/kb/3154519) | Paquete acumulativo de actualizaciones de confiabilidad HR-1605: compatibilidad para versiones predeterminadas del sistema TLS incluidas en .NET Framework 3.5 en Windows Server 2012 |
| [KB3154520](https://support.microsoft.com/kb/3154520) | Paquete acumulativo de actualizaciones de confiabilidad HR-1605: compatibilidad para versiones predeterminadas del sistema TLS incluidas en .NET Framework 3.5 en Windows 8.1 y Windows Server 2012 R2 |
| [KB3156421](https://support.microsoft.com/kb/3156421) | Paquete acumulativo de revisiones 1605 3154521 para .NET Framework 4.5.2 y 4.5.1 en Windows |

### <a name="for-wcf-using-net-framework-35---452-using-tcp-transport-security-with-certificate-credentials"></a>Para WCF que usa .NET Framework 3.5 - 4.5.2 y seguridad de transporte TCP con credenciales de certificado

Estas versiones de la plataforma WCF se han codificado de forma rígida para usar los valores SSL 3.0 y TLS 1.0. Estos valores no pueden modificarse. Debe actualizar y cambiar el destino a .NET Framework 4.6 o versiones posteriores para utilizar TLS 1.1 y 1.2.

## <a name="if-your-app-targets-net-framework-35"></a>Si la aplicación tiene como destino .NET Framework 3.5

Si se debe establecer explícitamente un protocolo de seguridad en lugar de permitir a .NET o el sistema operativo seleccionar el protocolo de seguridad, agregue las enumeraciones `SecurityProtocolTypeExtensions` y `SslProtocolsExtension` a su código. `SecurityProtocolTypeExtensions` y `SslProtocolsExtension` incluyen valores para el valor `Tls12`, `Tls11` y `SystemDefault`. Para obtener más información, consulte [Compatibilidad para las versiones predeterminadas del sistema TLS incluidas en .NET Framework 3.5 en Windows 8.1 y Windows Server 2012 R2](https://support.microsoft.com/help/3154520/support-for-tls-system-default-versions-included-in-the--net-framework).

<a name="configuring-security-via-appcontext-switches"></a>

## <a name="configuring-security-via-appcontext-switches-for-net-framework-46-or-later-versions"></a>Configuración de seguridad a través de conmutadores AppContext (para .NET Framework 4.6 o versiones posteriores)

Los conmutadores [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) descritos en esta sección son pertinentes si su aplicación tiene como destino .NET Framework 4.6 o versiones posteriores o se ejecuta en estas plataformas. Ya sea de forma predeterminada, o estableciéndolos de forma explícita, los conmutadores deberían ser `false` si fuera posible. Si desea configurar la seguridad a través de uno o los dos conmutadores, no especifique un valor de protocolo de seguridad en el código; de hacerlo, se reemplazarían los conmutadores.

Los conmutadores tienen el mismo efecto si utiliza redes de HTTP (<xref:System.Net.ServicePointManager>) o redes de sockets de TCP (<xref:System.Net.Security.SslStream>).

### <a name="switchsystemnetdontenableschusestrongcrypto"></a>Switch.System.Net.DontEnableSchUseStrongCrypto

Un valor de `false` para `Switch.System.Net.DontEnableSchUseStrongCrypto` hace que la aplicación utilice una criptografía robusta. Un valor de `false` para `DontEnableSchUseStrongCrypto` utiliza protocolos de red más seguros(TLS 1.2, TLS 1.1 y TLS 1.0) y bloquea los protocolos que no son seguros. Para obtener más información, consulte [La marca SCH_USE_STRONG_CRYPTO](#the-sch_use_strong_crypto-flag). Un valor de `true` deshabilita la criptografía robusta para la aplicación.

Si la aplicación tiene como destino .NET Framework 4.6 o versiones posteriores, el conmutador se establece de manera predeterminada en `false`. Este es un valor predeterminado seguro, así que lo recomendamos. Si la aplicación se ejecuta en .NET Framework 4.6, pero tiene como destino una versión anterior, el modificador se establece de manera predeterminada en `true`. En ese caso, debe establecerlo explícitamente en `false`.

`DontEnableSchUseStrongCrypto` solo debe tener un valor de `true` si necesita conectarse a servicios heredados que no son compatibles con la criptografía robusta y no se pueden actualizar.

### <a name="switchsystemnetdontenablesystemdefaulttlsversions"></a>Switch.System.Net.DontEnableSystemDefaultTlsVersions

Un valor de `false` para `Switch.System.Net.DontEnableSystemDefaultTlsVersions` hace que la aplicación permita que el sistema operativo elija el protocolo. Un valor de `true` hace que la aplicación utilice protocolos seleccionados por .NET Framework.

Si la aplicación tiene como destino .NET Framework 4.7 o versiones posteriores, el conmutador se establece de manera predeterminada en `false`. Este es un valor predeterminado seguro, así que lo recomendamos. Si la aplicación se ejecuta en .NET Framework 4.7 o versiones posteriores, pero tiene como destino una versión anterior, el modificador se establece de manera predeterminada en `true`. En ese caso, debe establecerlo explícitamente en `false`.

### <a name="switchsystemservicemodeldisableusingservicepointmanagersecurityprotocols"></a>Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols

Un valor de `false` para `Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols` hace que la aplicación utilice el valor definido en `ServicePointManager.SecurityProtocols` para la seguridad de los mensajes mediante credenciales de certificado. Un valor de `true` usa el protocolo más alto disponible, hasta TLS 1.0.

Para aplicaciones que tienen como destino .NET Framework 4.7 y versiones posteriores, este valor se establece de manera predeterminada en `false`. Para aplicaciones que tienen como destino .NET Framework 4.6.2 y versiones anteriores, este valor se establece de manera predeterminada en `true`.

### <a name="switchsystemservicemodeldontenablesystemdefaulttlsversions"></a>Switch.System.ServiceModel.DontEnableSystemDefaultTlsVersions

Un valor de `false` para `Switch.System.ServiceModel.DontEnableSystemDefaultTlsVersions` establece la configuración predeterminada para permitir que el sistema operativo elija el protocolo. Un valor de `true` establece como valor predeterminado el protocolo más alto disponible, hasta TLS 1.2.

Para aplicaciones que tienen como destino .NET Framework 4.7.1 y versiones posteriores, este valor se establece de manera predeterminada en `false`. Para aplicaciones que tienen como destino .NET Framework 4.7 y versiones anteriores, este valor se establece de manera predeterminada en `true`.

Para obtener más información sobre protocolos TLS, consulte [Mitigación: protocolos TLS](../migration-guide/mitigation-tls-protocols.md). Para obtener más información acerca de los conmutadores de `AppContext`, vea [`<AppContextSwitchOverrides> Element`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

## <a name="configuring-security-via-the-windows-registry"></a>Configuración de seguridad mediante el Registro de Windows

> [!WARNING]
> La configuración de las claves del Registro afecta a todas las aplicaciones del sistema. Use esta opción solo si tiene el control total de la máquina y puede controlar los cambios realizados en el registro.

Si la configuración de uno o los dos conmutadores de `AppContext` no es una opción, puede controlar los protocolos de seguridad que usa su aplicación con las claves del Registro de Windows que se describen en esta sección. Quizá no pueda utilizar uno de los conmutadores de `AppContext`, o los dos, si la aplicación se ejecuta en .NET Framework 4.5.2 o en versiones anteriores, o no puede editar el archivo de configuración. Si desea configurar la seguridad con el Registro, no especifique un valor de protocolo de seguridad en el código; de hacerlo, se reemplazará la configuración del Registro.

Los nombres de las claves del Registro son similares a los nombres de los conmutadores de `AppContext` correspondientes, pero sin `DontEnable` antepuesto al nombre. Por ejemplo, el conmutador de `AppContext``DontEnableSchUseStrongCrypto` es la clave del Registro llamada [SchUseStrongCrypto](#schusestrongcrypto).

Estas claves están disponibles en todas las versiones de .NET Framework para las que existe una revisión de seguridad reciente. Consulte [Actualizaciones de seguridad](#security-updates).

Todas las claves del Registro descritas a continuación tienen el mismo efecto si utiliza redes de HTTP (<xref:System.Net.ServicePointManager>) o redes de sockets de TCP (<xref:System.Net.Security.SslStream>).

### <a name="schusestrongcrypto"></a>SchUseStrongCrypto

La clave del Registro `HKEY_LOCAL_MACHINE\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\<VERSION>: SchUseStrongCrypto` tiene un valor de tipo DWORD. Un valor de 1 hace que la aplicación utilice una criptografía robusta. La criptografía robusta utiliza protocolos de red más seguros(TLS 1.2, TLS 1.1 y TLS 1.0) y bloquea los protocolos que no son seguros. Un valor de 0 deshabilita la criptografía robusta. Para obtener más información, consulte [La marca SCH_USE_STRONG_CRYPTO](#the-sch_use_strong_crypto-flag).

Si la aplicación tiene como destino .NET Framework 4.6 o versiones posteriores, la clave se establece de manera predeterminada en un valor de 1. Este es un valor predeterminado seguro, así que lo recomendamos. Si la aplicación se ejecuta en .NET Framework 4.6, pero tiene como destino una versión anterior, la clave se establece de manera predeterminada en 0. En ese caso, debe establecer su valor explícitamente en 1.

Esta clave solo debe tener un valor de 0 si necesita conectarse a servicios heredados que no son compatibles con la criptografía robusta y no se pueden actualizar.

### <a name="systemdefaulttlsversions"></a>SystemDefaultTlsVersions

La clave del Registro `HKEY_LOCAL_MACHINE\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\<VERSION>: SystemDefaultTlsVersions` tiene un valor de tipo DWORD. Un valor de 1 hace que la aplicación permita que el sistema operativo elija el protocolo. Un valor de 0 hace que la aplicación utilice protocolos seleccionados por .NET Framework.

`<VERSION>` debe ser v4.0.30319 (para .NET Framework 4 y versiones posteriores) o v2.0.50727 (para .NET Framework 3.5).

Si la aplicación tiene como destino .NET Framework 4.7 o versiones posteriores, la clave se establece de manera predeterminada en un valor de 1. Este es un valor predeterminado seguro, así que lo recomendamos. Si la aplicación se ejecuta en .NET Framework 4.7 o versiones posteriores, pero tiene como destino una versión anterior, la clave se establece de manera predeterminada en 0. En ese caso, debe establecer su valor explícitamente en 1.

Para obtener más información, consulte [Actualización acumulativa para Windows 10 versión 1511 y Windows Server 2016 Technical Preview 4: 10 de mayo de 2016](https://support.microsoft.com/help/3156421/cumulative-update-for-windows-10-version-1511-and-windows-server-2016).

Para obtener más información con .NET Framework 3.5.1, consulte [Compatibilidad para las versiones predeterminadas del sistema TLS incluidas en .NET Framework 3.5.1 en Windows 7 SP1 y Windows Server 2008 R2 SP1](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the--net-framework).

El siguiente archivo _. REG_ establece las claves del Registro y sus variantes en sus valores más seguros:

```text
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

## <a name="configuring-schannel-protocols-in-the-windows-registry"></a>Configuración de protocolos de Schannel en el Registro de Windows

Puede utilizar el registro para un control más preciso sobre los protocolos que negocia la aplicación servidor o cliente. Las redes de la aplicación pasan a través de Schannel (que es otro nombre para [canal seguro](/windows/desktop/SecAuthN/secure-channel)). Mediante la configuración de `Schannel`, puede configurar el comportamiento de la aplicación.

Inicie con la clave del Registro `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols`. Bajo esa clave, puede crear cualquier subclave en el conjunto `SSL 2.0`, `SSL 3.0`, `TLS 1.0`, `TLS 1.1` y `TLS 1.2`. En cada una de esas subclaves, puede crear subclaves `Client` o `Server`. En `Client` y `Server`, puede crear valores DWORD `DisabledByDefault` (0 o 1) y `Enabled` (0 o 0xFFFFFFFF).

## <a name="the-sch_use_strong_crypto-flag"></a>La marca SCH_USE_STRONG_CRYPTO

Cuando está habilitada (de forma predeterminada, por un conmutador `AppContext` o por el Registro de Windows), .NET Framework usa la marca `SCH_USE_STRONG_CRYPTO` cuando la aplicación solicita un protocolo de seguridad TLS. La marca `SCH_USE_STRONG_CRYPTO` puede estar habilitada de forma predeterminada, con el conmutador `AppContext` o con el Registro. El sistema operativo pasa la marca a `Schannel` para indicarle que deshabilite algoritmos criptográficos que se sabe que no son robustos, conjuntos de cifrado y versiones de protocolo TLS/SSL que pueden habilitarse en caso contrario para mejorar la interoperabilidad. Para obtener más información, consulte:

- [Canal seguro](/windows/desktop/SecAuthN/secure-channel)
- [Estructura de SCHANNEL_CRED](/windows/win32/api/schannel/ns-schannel-schannel_cred)

La marca `SCH_USE_STRONG_CRYPTO` también se pasa a `Schannel` cuando se utiliza explícitamente `Tls` (TLS 1.0), `Tls11` o valores enumerados `Tls12` de <xref:System.Net.SecurityProtocolType> y <xref:System.Security.Authentication.SslProtocols>.

## <a name="security-updates"></a>Actualizaciones de seguridad

Los procedimientos recomendados en este artículo dependen de las actualizaciones de seguridad recientes que se están instalando. Estas actualizaciones incluyen la posibilidad de utilizar las características avanzadas de .NET Framework 4.7 y versiones posteriores. Las actualizaciones de seguridad recientes son importantes si la aplicación se ejecuta en .NET Framework 4.7 y versiones posteriores (incluso si tienen como destino una versión anterior).

Para actualizar .NET Framework a fin de permitir que el sistema operativo elija la mejor versión de TLS para usar, debe instalar al menos:

- La [versión preliminar de .NET Framework de agosto de 2017 del paquete acumulativo de actualizaciones de calidad](https://devblogs.microsoft.com/dotnet/net-framework-august-2017-preview-of-quality-rollup/).
- **O** el [paquete acumulativo de actualizaciones de calidad y seguridad de .NET Framework de septiembre de 2017](https://devblogs.microsoft.com/dotnet/net-framework-september-2017-security-and-quality-rollup/).

Vea también:

- [Versiones y dependencias de .NET Framework](../migration-guide/versions-and-dependencies.md)
- [Cómo: Determinar qué versiones de .NET Framework están instaladas](../migration-guide/how-to-determine-which-versions-are-installed.md).

## <a name="support-for-tls-12"></a>Compatibilidad con TLS 1.2

Para que la aplicación pueda negociar con TLS 1.2, el sistema operativo y la versión de .NET Framework requieren compatibilidad con TLS 1.2.

**Requisitos del sistema operativo para admitir TLS 1.2**

Para habilitar o volver a habilitar TLS 1.2 o TLS 1.1 en un sistema que los admita, consulte [Configuración del registro de seguridad de la capa (TLS) de transporte](/windows-server/security/tls/tls-registry-settings).

| **SO** | **Compatibilidad con TLS 1.2** |
| --- | --- |
| Windows 10<br>Windows Server 2016 | Compatible, y habilitado de manera predeterminada. |
| Windows 8.1<br>Windows Server 2012 R2 | Compatible, y habilitado de manera predeterminada. |
| Windows 8.0<br>Windows Server 2012 | Compatible, y habilitado de manera predeterminada. |
| Windows 7 SP1<br>Windows Server 2008 R2 SP1 | Compatible, pero no habilitado de manera predeterminada. Consulte la página web [Configuración del registro de seguridad de la capa (TLS) de transporte](/windows-server/security/tls/tls-registry-settings) para obtener más información sobre cómo habilitar TLS 1.2. |
| Windows Server 2008 | La compatibilidad con TLS 1.2 y TLS 1.1 requiere una actualización. Vea [Actualización para agregar compatibilidad con TLS 1.1 y TLS 1.2 en Windows Server 2008 SP2](https://support.microsoft.com/help/4019276/update-to-add-support-for-tls-1-1-and-tls-1-2-in-windows-server-2008-s). |
| Windows Vista | No se admite. |

Para obtener información acerca de qué protocolos TLS/SSL protocolos están habilitados de forma predeterminada en cada versión de Windows, vea [Protocols in TLS/SSL (Schannel SSP)](/windows/desktop/SecAuthN/protocols-in-tls-ssl--schannel-ssp-) (Protocolos en TLS/SSL [SSP de Schannel]).

**Requisitos para admitir TLS 1.2 con .NET Framework 3.5**

En esta tabla se muestra la actualización del sistema operativo que necesitará para admitir TLS 1.2 con .NET Framework 3.5. Es recomendable que aplique todas las actualizaciones del sistema operativo.

| **SO** | **Actualización mínima necesaria para admitir TLS 1.2 con .NET Framework 3.5** |
| --- | --- |
| Windows 10<br>Windows Server 2016 | [Actualización acumulativa para Windows 10 versión 1511 y Windows Server 2016 Technical Preview 4: 10 de mayo de 2016](https://support.microsoft.com/help/3156421/cumulative-update-for-windows-10-version-1511-and-windows-server-2016) |
| Windows 8.1<br>Windows Server 2012 R2 | [Support for TLS System Default Versions included in .NET Framework 3.5 on Windows 8.1 and Windows Server 2012 R2](https://support.microsoft.com/help/3154520/support-for-tls-system-default-versions-included-in-the--net-framework) (Compatibilidad para las versiones predeterminadas del sistema TLS incluidas en .NET Framework 3.5 en Windows 8.1 y Windows Server 2012 R2) |
| Windows 8.0<br>Windows Server 2012 | [Support for TLS System Default Versions included in .NET Framework 3.5 on Windows 8.1 and Windows Server 2012 R2](https://support.microsoft.com/help/3154519/support-for-tls-system-default-versions-included-in-the--net-framework) (Compatibilidad para las versiones predeterminadas del sistema TLS incluidas en .NET Framework 3.5 en Windows 8.1 y Windows Server 2012 R2) |
| Windows 7 SP1<br>Windows Server 2008 R2 SP1 | [Support for TLS System Default Versions included in the .NET Framework 3.5.1 on Windows 7 SP1 and Server 2008 R2 SP1](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the--net-framework) (Compatibilidad para versiones predeterminadas del sistema TLS incluidas en .NET Framework 3.5.1 en Windows 7 SP1 y Server 2008 R2 SP1) |
| Windows Server 2008 | [Support for TLS System Default Versions included in the .NET Framework 2.0 SP2 on Windows Vista SP2 and Server 2008 SP2](https://support.microsoft.com/help/3154517/support-for-tls-system-default-versions-included-in-the--net-framework) (Compatibilidad para las versiones predeterminadas del sistema TLS incluidas en .NET Framework 2.0 SP2 en Windows Vista SP2 y Server 2008 SP2) |
| Windows Vista | No compatibles |

## <a name="azure-cloud-services"></a>Azure Cloud Services

Si utiliza los roles web y de trabajo de [Azure Cloud Services](https://azure.microsoft.com/services/cloud-services/) para hospedar y ejecutar la aplicación, tiene que tener en cuenta algunos aspectos en relación con la compatibilidad con TLS 1.2.

### <a name="net-framework-47-is-not-installed-on-azure-guest-os-by-default"></a>.NET Framework 4.7 no está instalado en el sistema operativo invitado de Azure de manera predeterminada.

La última versión instalada en la versión más reciente del lanzamiento de la familia 5 del sistema operativo invitado de Azure (Windows Server 2016) es 4.6.2. Para ver qué versiones de .NET Framework están instaladas en cada sistema operativo invitado de Azure, consulte [Matriz de compatibilidad del SDK y versiones del SO invitado de Azure](https://docs.microsoft.com/azure/cloud-services/cloud-services-guestos-update-matrix).

Si la aplicación tiene como destino una versión de .NET Framework que no está disponible en la versión de SO invitado de Azure, debe instalarla manualmente. Consulte [Instalación de .NET en roles de Azure Cloud Services](https://docs.microsoft.com/azure/cloud-services/cloud-services-dotnet-install-dotnet). Si la instalación de la plataforma requiere un reinicio, los roles del servicio podrían reiniciarse también antes de estar listos.

### <a name="azure-guest-os-registry-settings"></a>Configuración del Registro del sistema operativo invitado de Azure

La imagen de la familia 5 del sistema operativo invitado de Azure para [Azure Cloud Services](https://azure.microsoft.com/services/cloud-services/) ya tiene la clave del Registro `SchUseStrongCrypto` establecida en un valor de 1. Para obtener más información, consulte [SchUseStrongCrypto](#schusestrongcrypto).

Configure la clavel del Registro [SystemDefaultTlsVersions](#systemdefaulttlsversions) en 1. Vea [Configuración de seguridad mediante el Registro de Windows](#configuring-security-via-the-windows-registry).
