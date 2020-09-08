---
ms.openlocfilehash: b7b16e39fa5df9732fa769f2bcd3696dff3b2a49
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497065"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="d1720-101">RSACng.VerifyHash ahora devuelve False para los errores de comprobación</span><span class="sxs-lookup"><span data-stu-id="d1720-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

#### <a name="details"></a><span data-ttu-id="d1720-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="d1720-102">Details</span></span>

<span data-ttu-id="d1720-103">A partir de .NET Framework 4.6.2, este método devuelve **False** si la propia firma tiene un formato incorrecto.</span><span class="sxs-lookup"><span data-stu-id="d1720-103">Starting with the .NET Framework 4.6.2, this method returns **False** if the signature itself is badly formatted.</span></span> <span data-ttu-id="d1720-104">Ahora devuelve false para los errores de comprobación. En .NET Framework 4.6 y 4.6.1, el método inicia una excepción <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> si la propia firma tiene el formato incorrecto.</span><span class="sxs-lookup"><span data-stu-id="d1720-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> if the signature itself is badly formatted.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d1720-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="d1720-105">Suggestion</span></span>

<span data-ttu-id="d1720-106">Se debe ejecutar el código cuya ejecución dependa del control de <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> en lugar de ejecutarse si se produce un error en la validación y el método devuelve **False**.</span><span class="sxs-lookup"><span data-stu-id="d1720-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> should instead execute if validation fails and the method returns **False**.</span></span>

| <span data-ttu-id="d1720-107">Nombre</span><span class="sxs-lookup"><span data-stu-id="d1720-107">Name</span></span>    | <span data-ttu-id="d1720-108">Valor</span><span class="sxs-lookup"><span data-stu-id="d1720-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d1720-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="d1720-109">Scope</span></span>   |<span data-ttu-id="d1720-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="d1720-110">Minor</span></span>|
|<span data-ttu-id="d1720-111">Versión</span><span class="sxs-lookup"><span data-stu-id="d1720-111">Version</span></span>|<span data-ttu-id="d1720-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="d1720-112">4.6.2</span></span>|
|<span data-ttu-id="d1720-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="d1720-113">Type</span></span>|<span data-ttu-id="d1720-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="d1720-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d1720-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d1720-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)`

-->
