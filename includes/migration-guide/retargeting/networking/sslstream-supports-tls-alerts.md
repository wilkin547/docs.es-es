---
ms.openlocfilehash: 0024b2a53444319788b8cdd312d537f994070b5e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614761"
---
### <a name="sslstream-supports-tls-alerts"></a>SslStream es compatible con las alertas de TLS

#### <a name="details"></a>Detalles

Después de un error en el protocolo de enlace TLS, la primera operación de lectura y escritura de E/S iniciará una excepción <xref:System.IO.IOException?displayProperty=fullName> con una excepción <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> interna. El código <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=fullName> de <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> puede asignarse a la alerta de TLS de la parte remota con los [códigos de error de Schannel para las alertas de TLS y SSL](https://docs.microsoft.com/windows/desktop/SecAuthN/schannel-error-codes-for-tls-and-ssl-alerts).Para obtener más información, vea [RFC 2246: alertas de error, sección 7.2.2](https://tools.ietf.org/html/rfc2246#section-7.2.2). <br/>El comportamiento de .NET Framework 4.6.2 y versiones anteriores es que el canal de transporte (normalmente la conexión TCP) agotará el tiempo de espera durante la operación de escritura o lectura después de un error en el protocolo de enlace en la otra parte e inmediatamente después de rechazar la conexión.

#### <a name="suggestion"></a>Sugerencia

Las aplicaciones que llaman a las API de E/S de red como <xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)> deben controlar <xref:System.IO.IOException> o <xref:System.TimeoutException?displayProperty=fullName>.<br/>La característica de alertas de TLS está habilitada de forma predeterminada a partir de .NET Framework 4.7. Las aplicaciones destinadas a versiones de .NET Framework de la 4.0 a la 4.6.2 que se ejecuten en un sistema con .NET Framework 4.7 o una versión posterior tendrán la función deshabilitada para mantener la compatibilidad. <br/>La API de configuración siguiente está disponible para habilitar o deshabilitar la característica para las aplicaciones de .NET Framework 4.6 y versiones posteriores que se ejecuten en .NET Framework 4.7 o versiones posteriores.

- Mediante programación:   Debe ser lo primero que haga la aplicación dado que ServicePointManager solo se inicializará una vez:

    ```csharp
    AppContext.SetSwitch("TestSwitch.LocalAppContext.DisableCaching", true);

    // Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2.
    AppContext.SetSwitch("Switch.System.Net.DontEnableTlsAlerts", true);
    ```

- AppConfig:

    ```xml
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Net.DontEnableTlsAlerts=true"/>
      <!-- Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2. -->
    </runtime>
    ```

- Clave del Registro (global de equipo):   Establezca el valor en `false` para habilitar la característica en .NET Framework 4.6 - 4.6.2.

    ```ini
    Key: HKLM\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\AppContext\Switch.System.Net.DontEnableTlsAlerts
    - Type: String
    - Value: "true"
    ```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.7         |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.WebRequest?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Http?displayProperty=nameWithType>
