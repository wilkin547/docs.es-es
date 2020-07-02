---
ms.openlocfilehash: 0024b2a53444319788b8cdd312d537f994070b5e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614761"
---
### <a name="sslstream-supports-tls-alerts"></a><span data-ttu-id="4e7c3-101">SslStream es compatible con las alertas de TLS</span><span class="sxs-lookup"><span data-stu-id="4e7c3-101">SslStream supports TLS Alerts</span></span>

#### <a name="details"></a><span data-ttu-id="4e7c3-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="4e7c3-102">Details</span></span>

<span data-ttu-id="4e7c3-103">Después de un error en el protocolo de enlace TLS, la primera operación de lectura y escritura de E/S iniciará una excepción <xref:System.IO.IOException?displayProperty=fullName> con una excepción <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> interna.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-103">After a failed TLS handshake, an <xref:System.IO.IOException?displayProperty=fullName> with an inner <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> exception will be thrown by the first I/O Read/Write operation.</span></span> <span data-ttu-id="4e7c3-104">El código <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=fullName> de <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> puede asignarse a la alerta de TLS de la parte remota con los [códigos de error de Schannel para las alertas de TLS y SSL](https://docs.microsoft.com/windows/desktop/SecAuthN/schannel-error-codes-for-tls-and-ssl-alerts).Para obtener más información, vea [RFC 2246: alertas de error, sección 7.2.2](https://tools.ietf.org/html/rfc2246#section-7.2.2).</span><span class="sxs-lookup"><span data-stu-id="4e7c3-104">The <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=fullName> code for the <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> can be mapped to the TLS Alert from the remote party using the [Schannel error codes for TLS and SSL alerts](https://docs.microsoft.com/windows/desktop/SecAuthN/schannel-error-codes-for-tls-and-ssl-alerts).For more information, see [RFC 2246: Section 7.2.2 Error alerts](https://tools.ietf.org/html/rfc2246#section-7.2.2).</span></span> <br/><span data-ttu-id="4e7c3-105">El comportamiento de .NET Framework 4.6.2 y versiones anteriores es que el canal de transporte (normalmente la conexión TCP) agotará el tiempo de espera durante la operación de escritura o lectura después de un error en el protocolo de enlace en la otra parte e inmediatamente después de rechazar la conexión.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-105">The behavior in .NET Framework 4.6.2 and earlier is that the transport channel (usually TCP connection) will timeout during either Write or Read if the other party failed the handshake and immediately afterwards rejected the connection.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4e7c3-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="4e7c3-106">Suggestion</span></span>

<span data-ttu-id="4e7c3-107">Las aplicaciones que llaman a las API de E/S de red como <xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)> deben controlar <xref:System.IO.IOException> o <xref:System.TimeoutException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-107">Applications calling network I/O APIs such as <xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)> should handle <xref:System.IO.IOException> or <xref:System.TimeoutException?displayProperty=fullName>.</span></span><br/><span data-ttu-id="4e7c3-108">La característica de alertas de TLS está habilitada de forma predeterminada a partir de .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-108">The TLS Alerts feature is enabled by default starting with .NET Framework 4.7.</span></span> <span data-ttu-id="4e7c3-109">Las aplicaciones destinadas a versiones de .NET Framework de la 4.0 a la 4.6.2 que se ejecuten en un sistema con .NET Framework 4.7 o una versión posterior tendrán la función deshabilitada para mantener la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-109">Applications targeting versions of the .NET Framework from 4.0 through 4.6.2 running on a .NET Framework 4.7 or higher system will have the feature disabled to preserve compatibility.</span></span> <br/><span data-ttu-id="4e7c3-110">La API de configuración siguiente está disponible para habilitar o deshabilitar la característica para las aplicaciones de .NET Framework 4.6 y versiones posteriores que se ejecuten en .NET Framework 4.7 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-110">The following configuration API is available to enable or disable the feature for .NET Framework 4.6 and later applications running on .NET Framework 4.7 or later.</span></span>

- <span data-ttu-id="4e7c3-111">Mediante programación:   Debe ser lo primero que haga la aplicación dado que ServicePointManager solo se inicializará una vez:</span><span class="sxs-lookup"><span data-stu-id="4e7c3-111">Programmatically:   Must be the very first thing the application does since ServicePointManager will initialize only once:</span></span>

    ```csharp
    AppContext.SetSwitch("TestSwitch.LocalAppContext.DisableCaching", true);

    // Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2.
    AppContext.SetSwitch("Switch.System.Net.DontEnableTlsAlerts", true);
    ```

- <span data-ttu-id="4e7c3-112">AppConfig:</span><span class="sxs-lookup"><span data-stu-id="4e7c3-112">AppConfig:</span></span>

    ```xml
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Net.DontEnableTlsAlerts=true"/>
      <!-- Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2. -->
    </runtime>
    ```

- <span data-ttu-id="4e7c3-113">Clave del Registro (global de equipo):   Establezca el valor en `false` para habilitar la característica en .NET Framework 4.6 - 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-113">Registry key (machine global):   Set the Value to `false` to enable the feature in .NET Framework 4.6 - 4.6.2.</span></span>

    ```ini
    Key: HKLM\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\AppContext\Switch.System.Net.DontEnableTlsAlerts
    - Type: String
    - Value: "true"
    ```

| <span data-ttu-id="4e7c3-114">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="4e7c3-114">Name</span></span>    | <span data-ttu-id="4e7c3-115">Valor</span><span class="sxs-lookup"><span data-stu-id="4e7c3-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4e7c3-116">Ámbito</span><span class="sxs-lookup"><span data-stu-id="4e7c3-116">Scope</span></span>   | <span data-ttu-id="4e7c3-117">Borde</span><span class="sxs-lookup"><span data-stu-id="4e7c3-117">Edge</span></span>        |
| <span data-ttu-id="4e7c3-118">Versión</span><span class="sxs-lookup"><span data-stu-id="4e7c3-118">Version</span></span> | <span data-ttu-id="4e7c3-119">4.7</span><span class="sxs-lookup"><span data-stu-id="4e7c3-119">4.7</span></span>         |
| <span data-ttu-id="4e7c3-120">Tipo</span><span class="sxs-lookup"><span data-stu-id="4e7c3-120">Type</span></span>    | <span data-ttu-id="4e7c3-121">Redestinación</span><span class="sxs-lookup"><span data-stu-id="4e7c3-121">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="4e7c3-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="4e7c3-122">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.WebRequest?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Http?displayProperty=nameWithType>
