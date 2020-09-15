---
ms.openlocfilehash: 23e278d38d6904d8afe927e6b54c388d443e41f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616097"
---
### <a name="signedxmlgetpublickey-returns-rsacng-on-net462-or-lightup-without-retargeting-change"></a><span data-ttu-id="58c64-101">SignedXml.GetPublicKey devuelve RSACng en net462 (o Lightup) sin cambios de redestinación</span><span class="sxs-lookup"><span data-stu-id="58c64-101">SignedXml.GetPublicKey returns RSACng on net462 (or lightup) without retargeting change</span></span>

#### <a name="details"></a><span data-ttu-id="58c64-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="58c64-102">Details</span></span>

<span data-ttu-id="58c64-103">A partir de .NET Framework 4.6.2, se ha cambiado (sin peculiaridades) el tipo concreto del objeto devuelto por el método <xref:System.Security.Cryptography.Xml.SignedXml.GetPublicKey%2A?displayProperty=nameWithType> de una implementación de CryptoServiceProvider a una implementación de Cng.</span><span class="sxs-lookup"><span data-stu-id="58c64-103">Starting with the .NET Framework 4.6.2, the concrete type of the object returned by the <xref:System.Security.Cryptography.Xml.SignedXml.GetPublicKey%2A?displayProperty=nameWithType> method changed (without a quirk) from a CryptoServiceProvider implementation to a Cng implementation.</span></span> <span data-ttu-id="58c64-104">Esto se debe a que la implementación ha pasado de usar `certificate.PublicKey.Key` a usar la `certificate.GetAnyPublicKey` interna que reenvía a <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="58c64-104">This is because the implementation changed from using `certificate.PublicKey.Key` to using the internal `certificate.GetAnyPublicKey` which forwards to <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=nameWithType>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="58c64-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="58c64-105">Suggestion</span></span>

<span data-ttu-id="58c64-106">A partir de las aplicaciones que se ejecutan en .NET Framework 4.7.1, se puede usar la implementación de CryptoServiceProvider que se usa de forma predeterminada en .NET Framework 4.6.1 y versiones anteriores mediante la adición del conmutador siguiente a la sección [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="58c64-106">Starting with apps running on the .NET Framework 4.7.1, you can use the CryptoServiceProvider implementation used by default in the .NET Framework 4.6.1 and earlier versions by adding the following configuration switch to the [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.SignedXmlUseLegacyCertificatePrivateKey=true" />
```

| <span data-ttu-id="58c64-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="58c64-107">Name</span></span>    | <span data-ttu-id="58c64-108">Valor</span><span class="sxs-lookup"><span data-stu-id="58c64-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="58c64-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="58c64-109">Scope</span></span>   | <span data-ttu-id="58c64-110">Borde</span><span class="sxs-lookup"><span data-stu-id="58c64-110">Edge</span></span>        |
| <span data-ttu-id="58c64-111">Versión</span><span class="sxs-lookup"><span data-stu-id="58c64-111">Version</span></span> | <span data-ttu-id="58c64-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="58c64-112">4.6.2</span></span>       |
| <span data-ttu-id="58c64-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="58c64-113">Type</span></span>    | <span data-ttu-id="58c64-114">Redestinación</span><span class="sxs-lookup"><span data-stu-id="58c64-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="58c64-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="58c64-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignatureReturningKey(System.Security.Cryptography.AsymmetricAlgorithm@)?displayProperty=nameWithType>
