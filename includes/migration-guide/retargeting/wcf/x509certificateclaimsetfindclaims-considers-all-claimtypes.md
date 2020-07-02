---
ms.openlocfilehash: abef47c64a7cfd99c5b50bf2100401a2d5fcc5c3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614737"
---
### <a name="x509certificateclaimsetfindclaims-considers-all-claimtypes"></a><span data-ttu-id="2dfd4-101">X509CertificateClaimSet.FindClaims considera todos los argumentos claimType</span><span class="sxs-lookup"><span data-stu-id="2dfd4-101">X509CertificateClaimSet.FindClaims Considers All claimTypes</span></span>

#### <a name="details"></a><span data-ttu-id="2dfd4-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="2dfd4-102">Details</span></span>

<span data-ttu-id="2dfd4-103">En las aplicaciones destinadas a .NET Framework 4.6.1, si un conjunto de notificaciones X509 se inicializó desde un certificado con varias entradas DNS en su campo SAN, el método <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> trata de hacer coincidir el argumento claimType con todas las entradas DNS. En las aplicaciones destinadas a versiones anteriores de .NET Framework, el método <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> solo trata de hacer coincidir el argumento claimType con la última entrada DNS.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-103">In apps that target the .NET Framework 4.6.1, if an X509 claim set is initialized from a certificate that has multiple DNS entries in its SAN field, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> method attempts to match the claimType argument with all the DNS entries.For apps that target previous versions of the .NET Framework, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> method attempts to match the claimType argument only with the last DNS entry.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2dfd4-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="2dfd4-104">Suggestion</span></span>

<span data-ttu-id="2dfd4-105">Este cambio solo afecta a las aplicaciones que tengan como destino .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-105">This change only affects applications targeting the .NET Framework 4.6.1.</span></span> <span data-ttu-id="2dfd4-106">Este cambio puede deshabilitarse, o habilitarse si se establece como destino una versión anterior a la 4.6.1, con el modificador de compatibilidad [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation).</span><span class="sxs-lookup"><span data-stu-id="2dfd4-106">This change may be disabled (or enabled if targeting pre-4.6.1) with the [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation) compatibility switch.</span></span>

| <span data-ttu-id="2dfd4-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="2dfd4-107">Name</span></span>    | <span data-ttu-id="2dfd4-108">Valor</span><span class="sxs-lookup"><span data-stu-id="2dfd4-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2dfd4-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="2dfd4-109">Scope</span></span>   | <span data-ttu-id="2dfd4-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="2dfd4-110">Minor</span></span>       |
| <span data-ttu-id="2dfd4-111">Versión</span><span class="sxs-lookup"><span data-stu-id="2dfd4-111">Version</span></span> | <span data-ttu-id="2dfd4-112">4.6.1</span><span class="sxs-lookup"><span data-stu-id="2dfd4-112">4.6.1</span></span>       |
| <span data-ttu-id="2dfd4-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="2dfd4-113">Type</span></span>    | <span data-ttu-id="2dfd4-114">Redestinación</span><span class="sxs-lookup"><span data-stu-id="2dfd4-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="2dfd4-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="2dfd4-115">Affected APIs</span></span>

- <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=nameWithType>
