---
ms.openlocfilehash: fc315faef750d93d914104dd568078aa3fc430d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "72887838"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="1573f-101">RSACng.VerifyHash ahora devuelve False para los errores de comprobación</span><span class="sxs-lookup"><span data-stu-id="1573f-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

|   |   |
|---|---|
|<span data-ttu-id="1573f-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="1573f-102">Details</span></span>|<span data-ttu-id="1573f-103">A partir de .NET Framework 4.6.2, este método devuelve **False** si la propia firma tiene un formato incorrecto.</span><span class="sxs-lookup"><span data-stu-id="1573f-103">Starting with the .NET Framework 4.6.2, this method returns **False** if the signature itself is badly formatted.</span></span> <span data-ttu-id="1573f-104">Ahora devuelve false para los errores de comprobación. En .NET Framework 4.6 y 4.6.1, el método inicia una excepción <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> si la propia firma tiene el formato incorrecto.</span><span class="sxs-lookup"><span data-stu-id="1573f-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> if the signature itself is badly formatted.</span></span>|
|<span data-ttu-id="1573f-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="1573f-105">Suggestion</span></span>|<span data-ttu-id="1573f-106">Se debe ejecutar el código cuya ejecución dependa del control de <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> en lugar de ejecutarse si se produce un error en la validación y el método devuelve **False**.</span><span class="sxs-lookup"><span data-stu-id="1573f-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> should instead execute if validation fails and the method returns **False**.</span></span>|
|<span data-ttu-id="1573f-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="1573f-107">Scope</span></span>|<span data-ttu-id="1573f-108">Secundaria</span><span class="sxs-lookup"><span data-stu-id="1573f-108">Minor</span></span>|
|<span data-ttu-id="1573f-109">Versión</span><span class="sxs-lookup"><span data-stu-id="1573f-109">Version</span></span>|<span data-ttu-id="1573f-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="1573f-110">4.6.2</span></span>|
|<span data-ttu-id="1573f-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="1573f-111">Type</span></span>|<span data-ttu-id="1573f-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="1573f-112">Runtime</span></span>|
|<span data-ttu-id="1573f-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="1573f-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
