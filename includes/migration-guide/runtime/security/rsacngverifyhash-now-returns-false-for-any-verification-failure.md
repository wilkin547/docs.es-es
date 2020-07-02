---
ms.openlocfilehash: fa5cf2280cdd9535962568a6272d047d261eeba5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621381"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="0c3e6-101">RSACng.VerifyHash ahora devuelve False para los errores de comprobación</span><span class="sxs-lookup"><span data-stu-id="0c3e6-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

#### <a name="details"></a><span data-ttu-id="0c3e6-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="0c3e6-102">Details</span></span>

<span data-ttu-id="0c3e6-103">A partir de .NET Framework 4.6.2, este método devuelve **False** si la propia firma tiene un formato incorrecto.</span><span class="sxs-lookup"><span data-stu-id="0c3e6-103">Starting with the .NET Framework 4.6.2, this method returns **False** if the signature itself is badly formatted.</span></span> <span data-ttu-id="0c3e6-104">Ahora devuelve false para los errores de comprobación. En .NET Framework 4.6 y 4.6.1, el método inicia una excepción <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> si la propia firma tiene el formato incorrecto.</span><span class="sxs-lookup"><span data-stu-id="0c3e6-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> if the signature itself is badly formatted.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0c3e6-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="0c3e6-105">Suggestion</span></span>

<span data-ttu-id="0c3e6-106">Se debe ejecutar el código cuya ejecución dependa del control de <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> en lugar de ejecutarse si se produce un error en la validación y el método devuelve **False**.</span><span class="sxs-lookup"><span data-stu-id="0c3e6-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> should instead execute if validation fails and the method returns **False**.</span></span>

| <span data-ttu-id="0c3e6-107">Nombre</span><span class="sxs-lookup"><span data-stu-id="0c3e6-107">Name</span></span>    | <span data-ttu-id="0c3e6-108">Valor</span><span class="sxs-lookup"><span data-stu-id="0c3e6-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0c3e6-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="0c3e6-109">Scope</span></span>   |<span data-ttu-id="0c3e6-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="0c3e6-110">Minor</span></span>|
|<span data-ttu-id="0c3e6-111">Versión</span><span class="sxs-lookup"><span data-stu-id="0c3e6-111">Version</span></span>|<span data-ttu-id="0c3e6-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="0c3e6-112">4.6.2</span></span>|
|<span data-ttu-id="0c3e6-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="0c3e6-113">Type</span></span>|<span data-ttu-id="0c3e6-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="0c3e6-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0c3e6-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="0c3e6-115">Affected APIs</span></span>

-<xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
