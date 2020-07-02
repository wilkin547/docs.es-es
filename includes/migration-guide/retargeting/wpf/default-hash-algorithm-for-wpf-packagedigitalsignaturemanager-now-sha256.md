---
ms.openlocfilehash: d3e0a61601f60a389b662f6f74934b6e6dc6e663
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614914"
---
### <a name="the-default-hash-algorithm-for-wpf-packagedigitalsignaturemanager-is-now-sha256"></a><span data-ttu-id="31ede-101">El algoritmo hash predeterminado para PackageDigitalSignatureManager de WPF ahora es SHA256</span><span class="sxs-lookup"><span data-stu-id="31ede-101">The default hash algorithm for WPF PackageDigitalSignatureManager is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="31ede-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="31ede-102">Details</span></span>

<span data-ttu-id="31ede-103">`System.IO.Packaging.PackageDigitalSignatureManager` proporciona funcionalidad para las firmas digitales en relación con los paquetes de WPF.</span><span class="sxs-lookup"><span data-stu-id="31ede-103">The `System.IO.Packaging.PackageDigitalSignatureManager` provides functionality for digital signatures in relation to WPF packages.</span></span>  <span data-ttu-id="31ede-104">En .NET Framework 4.7 y versiones anteriores, el algoritmo predeterminado (<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>) que se usaba para firmar los elementos de un paquete era SHA1.</span><span class="sxs-lookup"><span data-stu-id="31ede-104">In the .NET Framework 4.7 and earlier versions, the default algorithm (<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>) used for signing parts of a package was SHA1.</span></span>  <span data-ttu-id="31ede-105">Por motivos de seguridad recientes con SHA1, este valor predeterminado se ha cambiado a SHA256 a partir de .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="31ede-105">Due to recent security concerns with SHA1, this default has been changed to SHA256 starting with the .NET Framework 4.7.1.</span></span>  <span data-ttu-id="31ede-106">Este cambio afecta a todas las firmas de paquetes, incluidos los documentos XPS.</span><span class="sxs-lookup"><span data-stu-id="31ede-106">This change affects all package signing, including XPS documents.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="31ede-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="31ede-107">Suggestion</span></span>

<span data-ttu-id="31ede-108">Un desarrollador que quiera usar este cambio mientras selecciona como destino una versión de la plataforma inferior a .NET Framework 4.7.1 o un desarrollador que requiera la funcionalidad anterior mientras selecciona como destino .NET Framework 4.7.1 o una versión posterior pueden establecer de manera apropiada la marca de AppContext siguiente.</span><span class="sxs-lookup"><span data-stu-id="31ede-108">A developer who wants to utilize this change while targeting a framework version below .NET Framework 4.7.1 or a developer who requires the previous functionality while targeting .NET Framework 4.7.1 or greater can set the following AppContext flag appropriately.</span></span>  <span data-ttu-id="31ede-109">Un valor de true dará como resultado el uso de SHA1 como el algoritmo predeterminado; false hará que se use SHA256.</span><span class="sxs-lookup"><span data-stu-id="31ede-109">A value of true will result in SHA1 being used as the default algorithm; false results in SHA256.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.UseSha1AsDefaultHashAlgorithmForDigitalSignatures=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="31ede-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="31ede-110">Name</span></span>    | <span data-ttu-id="31ede-111">Valor</span><span class="sxs-lookup"><span data-stu-id="31ede-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="31ede-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="31ede-112">Scope</span></span>   | <span data-ttu-id="31ede-113">Borde</span><span class="sxs-lookup"><span data-stu-id="31ede-113">Edge</span></span>        |
| <span data-ttu-id="31ede-114">Versión</span><span class="sxs-lookup"><span data-stu-id="31ede-114">Version</span></span> | <span data-ttu-id="31ede-115">4.7.1</span><span class="sxs-lookup"><span data-stu-id="31ede-115">4.7.1</span></span>       |
| <span data-ttu-id="31ede-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="31ede-116">Type</span></span>    | <span data-ttu-id="31ede-117">Redestinación</span><span class="sxs-lookup"><span data-stu-id="31ede-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="31ede-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="31ede-118">Affected APIs</span></span>

- <xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>
