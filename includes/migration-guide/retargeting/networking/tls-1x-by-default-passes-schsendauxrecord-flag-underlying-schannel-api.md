---
ms.openlocfilehash: 207dba9327cfd6debd15c5573697f8950b6c2c95
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86218240"
---
### <a name="tls-1x-by-default-passes-the-sch_send_aux_record-flag-to-the-underlying-schannel-api"></a><span data-ttu-id="8152a-101">De forma predeterminada, TLS 1.x pasa la marca SCH_SEND_AUX_RECORD a la API SCHANNEL subyacente.</span><span class="sxs-lookup"><span data-stu-id="8152a-101">TLS 1.x by default passes the SCH_SEND_AUX_RECORD flag to the underlying SCHANNEL API</span></span>

#### <a name="details"></a><span data-ttu-id="8152a-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="8152a-102">Details</span></span>

<span data-ttu-id="8152a-103">Cuando se usa TLS 1.x, .NET Framework se basa en la API SCHANNEL de Windows subyacente.</span><span class="sxs-lookup"><span data-stu-id="8152a-103">When using TLS 1.x, the .NET Framework relies on the underlying Windows SCHANNEL API.</span></span> <span data-ttu-id="8152a-104">A partir de .NET Framework 4.6, de forma predeterminada se pasa la marca [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) a SCHANNEL.</span><span class="sxs-lookup"><span data-stu-id="8152a-104">Starting with .NET Framework 4.6, the [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) flag is passed by default to SCHANNEL.</span></span> <span data-ttu-id="8152a-105">Esto hace que SCHANNEL divida los datos que se van a cifrar en dos registros independientes, el primero de un solo byte y el segundo con <em>n</em>-1 bytes. En raras ocasiones, esto interrumpe la comunicación entre los clientes y los servidores existentes que dan por hecho que los datos residen en un único registro.</span><span class="sxs-lookup"><span data-stu-id="8152a-105">This causes SCHANNEL to split data to be encrypted into two separate records, the first as a single byte and the second as <em>n</em>-1 bytes.In rare cases, this breaks communication between clients and existing servers that make the assumption that the data resides in a single record.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8152a-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="8152a-106">Suggestion</span></span>

<span data-ttu-id="8152a-107">Si este cambio interrumpe la comunicación con un servidor existente, puede deshabilitar el envío de la marca [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) y restaurar el comportamiento anterior de no dividir los datos en registros independientes si agrega el modificador siguiente al elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) en la sección [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="8152a-107">If this change breaks communication with an existing server, you can disable sending the [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) flag and restore the previous behavior of not splitting data into separate records by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchSendAuxRecord=true" />
</runtime>
```

> [!IMPORTANT]
> <span data-ttu-id="8152a-108">Este valor solamente se proporciona por motivos de compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="8152a-108">This setting is provided for backward compatibility only.</span></span> <span data-ttu-id="8152a-109">Pero no se recomienda su uso.</span><span class="sxs-lookup"><span data-stu-id="8152a-109">Its use is otherwise not recommended.</span></span>

| <span data-ttu-id="8152a-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="8152a-110">Name</span></span>    | <span data-ttu-id="8152a-111">Valor</span><span class="sxs-lookup"><span data-stu-id="8152a-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8152a-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="8152a-112">Scope</span></span>   | <span data-ttu-id="8152a-113">Borde</span><span class="sxs-lookup"><span data-stu-id="8152a-113">Edge</span></span>        |
| <span data-ttu-id="8152a-114">Versión</span><span class="sxs-lookup"><span data-stu-id="8152a-114">Version</span></span> | <span data-ttu-id="8152a-115">4.6</span><span class="sxs-lookup"><span data-stu-id="8152a-115">4.6</span></span>         |
| <span data-ttu-id="8152a-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="8152a-116">Type</span></span>    | <span data-ttu-id="8152a-117">Redestinación</span><span class="sxs-lookup"><span data-stu-id="8152a-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="8152a-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="8152a-118">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.ServicePointManager?displayProperty=nameWithType>
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
