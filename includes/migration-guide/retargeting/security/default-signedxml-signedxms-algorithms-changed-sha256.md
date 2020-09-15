---
ms.openlocfilehash: e2ae329d027d605e6331afe422e550990fab1042
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614813"
---
### <a name="default-signedxml-and-signedxms-algorithms-changed-to-sha256"></a><span data-ttu-id="221ae-101">Los algoritmos SignedXML y SignedXMS predeterminados se han cambiado a SHA256</span><span class="sxs-lookup"><span data-stu-id="221ae-101">Default SignedXML and SignedXMS algorithms changed to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="221ae-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="221ae-102">Details</span></span>

<span data-ttu-id="221ae-103">En .NET Framework 4.7 y versiones anteriores, SignedXML y SignedCMS usaban SHA1 de forma predeterminada para algunas operaciones. A partir de .NET Framework 4.7.1, SHA256 está habilitado de forma predeterminada para estas operaciones.</span><span class="sxs-lookup"><span data-stu-id="221ae-103">In the .NET Framework 4.7 and earlier, SignedXML and SignedCMS default to SHA1 for some operations.Starting with the .NET Framework 4.7.1, SHA256 is enabled by default for these operations.</span></span> <span data-ttu-id="221ae-104">Este cambio es necesario porque SHA1 ya no se considera seguro.</span><span class="sxs-lookup"><span data-stu-id="221ae-104">This change is necessary because SHA1 is no longer considered to be secure.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="221ae-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="221ae-105">Suggestion</span></span>

<span data-ttu-id="221ae-106">Hay dos valores de modificador de contexto nuevos para controlar si se usa SHA1 (no seguro) o SHA256 de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="221ae-106">There are two new context switch values to control whether SHA1 (insecure) or SHA256 is used by default:</span></span>

- <span data-ttu-id="221ae-107">Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms</span><span class="sxs-lookup"><span data-stu-id="221ae-107">Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms</span></span>
- <span data-ttu-id="221ae-108">Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms. Para las aplicaciones destinadas a .NET Framework 4.7.1 y versiones posteriores, si no se quiere usar SHA256, se puede restaurar el valor predeterminado a SHA1 si se agrega el conmutador de configuración siguiente a la sección [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="221ae-108">Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms For applications that target the .NET Framework 4.7.1 and later versions, if the use of SHA256 is undesirable, you can restore the default to SHA1 by adding the following configuration switch to the [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=true;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=true" />
```

<span data-ttu-id="221ae-109">Para las aplicaciones destinadas a .NET Framework 4.7 y versiones posteriores, se puede permitir este cambio si se agrega el conmutador de configuración siguiente a la sección [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="221ae-109">For applications that target the .NET Framework 4.7 and earlier versions, you can opt into this change by adding the following configuration switch to the [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=false;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=false" />
```

| <span data-ttu-id="221ae-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="221ae-110">Name</span></span>    | <span data-ttu-id="221ae-111">Valor</span><span class="sxs-lookup"><span data-stu-id="221ae-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="221ae-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="221ae-112">Scope</span></span>   | <span data-ttu-id="221ae-113">Secundaria</span><span class="sxs-lookup"><span data-stu-id="221ae-113">Minor</span></span>       |
| <span data-ttu-id="221ae-114">Versión</span><span class="sxs-lookup"><span data-stu-id="221ae-114">Version</span></span> | <span data-ttu-id="221ae-115">4.7.1</span><span class="sxs-lookup"><span data-stu-id="221ae-115">4.7.1</span></span>       |
| <span data-ttu-id="221ae-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="221ae-116">Type</span></span>    | <span data-ttu-id="221ae-117">Redestinación</span><span class="sxs-lookup"><span data-stu-id="221ae-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="221ae-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="221ae-118">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Pkcs.CmsSigner?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.Reference?displayProperty=nameWithType>
