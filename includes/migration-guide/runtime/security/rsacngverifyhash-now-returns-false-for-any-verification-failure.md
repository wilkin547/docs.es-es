---
ms.openlocfilehash: acf4e8df2cef3d9ec5d123a14cc7bfcd6f1bfb8b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236085"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="6859a-101">RSACng.VerifyHash ahora devuelve False para los errores de comprobación</span><span class="sxs-lookup"><span data-stu-id="6859a-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

|   |   |
|---|---|
|<span data-ttu-id="6859a-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="6859a-102">Details</span></span>|<span data-ttu-id="6859a-103">A partir de .NET Framework 4.6.2, este método devuelve <strong>False</strong> si la propia firma tiene un formato incorrecto.</span><span class="sxs-lookup"><span data-stu-id="6859a-103">Starting with the .NET Framework 4.6.2, this method returns <strong>False</strong> if the signature itself is badly formatted.</span></span> <span data-ttu-id="6859a-104">Ahora devuelve false para los errores de comprobación. En .NET Framework 4.6 y 4.6.1, el método inicia una excepción <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> si la propia firma tiene el formato incorrecto.</span><span class="sxs-lookup"><span data-stu-id="6859a-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> if the signature itself is badly formatted.</span></span>|
|<span data-ttu-id="6859a-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="6859a-105">Suggestion</span></span>|<span data-ttu-id="6859a-106">Se debe ejecutar el código cuya ejecución dependa del control de <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> en lugar de ejecutarse si se produce un error en la validación y el método devuelve <strong>False</strong>.</span><span class="sxs-lookup"><span data-stu-id="6859a-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> should instead execute if validation fails and the method returns <strong>False</strong>.</span></span>|
|<span data-ttu-id="6859a-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="6859a-107">Scope</span></span>|<span data-ttu-id="6859a-108">Secundaria</span><span class="sxs-lookup"><span data-stu-id="6859a-108">Minor</span></span>|
|<span data-ttu-id="6859a-109">Versión</span><span class="sxs-lookup"><span data-stu-id="6859a-109">Version</span></span>|<span data-ttu-id="6859a-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="6859a-110">4.6.2</span></span>|
|<span data-ttu-id="6859a-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="6859a-111">Type</span></span>|<span data-ttu-id="6859a-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="6859a-112">Runtime</span></span>|
|<span data-ttu-id="6859a-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6859a-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
