---
ms.openlocfilehash: 87dc93ece10eaedbfbabddb5f857d0bcd12e05c4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615762"
---
### <a name="only-tls-10-11-and-12-protocols-supported-in-systemnetservicepointmanager-and-systemnetsecuritysslstream"></a><span data-ttu-id="6fc3e-101">En System.Net.ServicePointManager y System.Net.Security.SslStream solo se admiten los protocolos TLS 1.0, 1.1 y 1.2</span><span class="sxs-lookup"><span data-stu-id="6fc3e-101">Only Tls 1.0, 1.1 and 1.2 protocols supported in System.Net.ServicePointManager and System.Net.Security.SslStream</span></span>

#### <a name="details"></a><span data-ttu-id="6fc3e-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="6fc3e-102">Details</span></span>

<span data-ttu-id="6fc3e-103">A partir de .NET Framework 4.6, las clases <xref:System.Net.ServicePointManager> y <xref:System.Net.Security.SslStream> solo pueden usar uno de los tres protocolos siguientes: Tls1.0, Tls1.1 o Tls1.2.</span><span class="sxs-lookup"><span data-stu-id="6fc3e-103">Starting with the .NET Framework 4.6, the <xref:System.Net.ServicePointManager> and <xref:System.Net.Security.SslStream> classes are only allowed to use one of the following three protocols: Tls1.0, Tls1.1, or Tls1.2.</span></span> <span data-ttu-id="6fc3e-104">No se admite el protocolo SSL 3.0 ni el cifrado RC4.</span><span class="sxs-lookup"><span data-stu-id="6fc3e-104">The SSL3.0 protocol and RC4 cipher are not supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6fc3e-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="6fc3e-105">Suggestion</span></span>

<span data-ttu-id="6fc3e-106">La mitigación recomendada consiste en actualizar la aplicación del lado servidor a Tls1.0, Tls1.1 o Tls1.2.</span><span class="sxs-lookup"><span data-stu-id="6fc3e-106">The recommended mitigation is to upgrade the sever-side app to Tls1.0, Tls1.1, or Tls1.2.</span></span> <span data-ttu-id="6fc3e-107">Si esto no es posible o si las aplicaciones cliente se interrumpen, se puede usar la clase <xref:System.AppContext?displayProperty=fullName> para descartar esta característica de cualquiera de estas dos maneras:</span><span class="sxs-lookup"><span data-stu-id="6fc3e-107">If this is not feasible, or if client apps are broken, the <xref:System.AppContext?displayProperty=fullName> class can be used to opt out of this feature in either of two ways:</span></span>

- <span data-ttu-id="6fc3e-108">Configurando mediante programación los modificadores de compatibilidad en la instancia <xref:System.AppContext?displayProperty=fullName>, como se explica [aquí](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</span><span class="sxs-lookup"><span data-stu-id="6fc3e-108">By programmatically setting compat switches on the <xref:System.AppContext?displayProperty=fullName>, as explained [here](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</span></span>
- <span data-ttu-id="6fc3e-109">Agregando la siguiente línea a la sección `<runtime>` del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="6fc3e-109">By adding the following line to the `<runtime>` section of the app.config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>
```

| <span data-ttu-id="6fc3e-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6fc3e-110">Name</span></span>    | <span data-ttu-id="6fc3e-111">Valor</span><span class="sxs-lookup"><span data-stu-id="6fc3e-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6fc3e-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="6fc3e-112">Scope</span></span>   | <span data-ttu-id="6fc3e-113">Secundaria</span><span class="sxs-lookup"><span data-stu-id="6fc3e-113">Minor</span></span>       |
| <span data-ttu-id="6fc3e-114">Versión</span><span class="sxs-lookup"><span data-stu-id="6fc3e-114">Version</span></span> | <span data-ttu-id="6fc3e-115">4.6</span><span class="sxs-lookup"><span data-stu-id="6fc3e-115">4.6</span></span>         |
| <span data-ttu-id="6fc3e-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="6fc3e-116">Type</span></span>    | <span data-ttu-id="6fc3e-117">Redestinación</span><span class="sxs-lookup"><span data-stu-id="6fc3e-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="6fc3e-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6fc3e-118">Affected APIs</span></span>

- <xref:System.Net.SecurityProtocolType.Ssl3?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.Ssl2?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.Ssl3?displayProperty=nameWithType>
