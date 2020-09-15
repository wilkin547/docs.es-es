---
ms.openlocfilehash: c996dafcf65b1fd428be908be346de603ead6e0b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615756"
---
### <a name="certificate-eku-oid-validation"></a><span data-ttu-id="ccb27-101">Validación de OID de EKU de certificado</span><span class="sxs-lookup"><span data-stu-id="ccb27-101">Certificate EKU OID validation</span></span>

#### <a name="details"></a><span data-ttu-id="ccb27-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="ccb27-102">Details</span></span>

<span data-ttu-id="ccb27-103">A partir de .NET Framework 4.6, las clases <xref:System.Net.Security.SslStream> o <xref:System.Net.ServicePointManager> realizan la validación de identificador de objetos (OID) de uso mejorado de clave (EKU).</span><span class="sxs-lookup"><span data-stu-id="ccb27-103">Starting with .NET Framework 4.6, the <xref:System.Net.Security.SslStream> or <xref:System.Net.ServicePointManager> classes perform enhanced key use (EKU) object identifier (OID) validation.</span></span> <span data-ttu-id="ccb27-104">Una extensión de uso mejorado de clave (EKU) es una colección de identificadores de objetos (OID) que indica las aplicaciones que usan la clave.</span><span class="sxs-lookup"><span data-stu-id="ccb27-104">An enhanced key usage (EKU) extension is a collection of object identifiers (OIDs) that indicate the applications that use the key.</span></span> <span data-ttu-id="ccb27-105">En la validación de OID de EKU se usan devoluciones de llamada de certificado remoto para asegurarse de que el certificado remoto tiene los OID correctos para el propósito previsto.</span><span class="sxs-lookup"><span data-stu-id="ccb27-105">EKU OID validation uses remote certificate callbacks to ensure that the remote certificate has the correct OIDs for the intended purpose.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ccb27-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="ccb27-106">Suggestion</span></span>

<span data-ttu-id="ccb27-107">Si no quiere este cambio, puede deshabilitar la validación de OID de EKU del certificado mediante la adición del modificador siguiente a [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) a la [\`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="ccb27-107">If this change is undesirable, you can disable certificate EKU OID validation by adding the following switch to the [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) in the [\`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) of your app configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontCheckCertificateEKUs=true" />
</runtime>
```

> [!IMPORTANT]
> <span data-ttu-id="ccb27-108">Este valor solamente se proporciona por motivos de compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="ccb27-108">This setting is provided for backward compatibility only.</span></span> <span data-ttu-id="ccb27-109">Pero no se recomienda su uso.</span><span class="sxs-lookup"><span data-stu-id="ccb27-109">Its use is otherwise not recommended.</span></span>

| <span data-ttu-id="ccb27-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="ccb27-110">Name</span></span>    | <span data-ttu-id="ccb27-111">Valor</span><span class="sxs-lookup"><span data-stu-id="ccb27-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ccb27-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="ccb27-112">Scope</span></span>   | <span data-ttu-id="ccb27-113">Secundaria</span><span class="sxs-lookup"><span data-stu-id="ccb27-113">Minor</span></span>       |
| <span data-ttu-id="ccb27-114">Versión</span><span class="sxs-lookup"><span data-stu-id="ccb27-114">Version</span></span> | <span data-ttu-id="ccb27-115">4.6</span><span class="sxs-lookup"><span data-stu-id="ccb27-115">4.6</span></span>         |
| <span data-ttu-id="ccb27-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="ccb27-116">Type</span></span>    | <span data-ttu-id="ccb27-117">Redestinación</span><span class="sxs-lookup"><span data-stu-id="ccb27-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="ccb27-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="ccb27-118">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.ServicePointManager?displayProperty=nameWithType>
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
