---
ms.openlocfilehash: 07ab65de16b72bd0844a39e4b35235c5f043f3ec
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117214"
---
### <a name="minimum-size-for-rsaopenssl-key-generation-has-increased"></a><span data-ttu-id="f307a-101">Ha aumentado el tamaño mínimo de la generación de claves RSAOpenSsl</span><span class="sxs-lookup"><span data-stu-id="f307a-101">Minimum size for RSAOpenSsl key generation has increased</span></span>

<span data-ttu-id="f307a-102">El tamaño mínimo para generar nuevas claves RSA en Linux ha aumentado de 384 bits a 512 bits.</span><span class="sxs-lookup"><span data-stu-id="f307a-102">The minimum size for generating new RSA keys on Linux has increased from 384-bit to 512-bit.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f307a-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="f307a-103">Change description</span></span>

<span data-ttu-id="f307a-104">A partir de .NET Core 3.0, el tamaño mínimo de clave permitido que la propiedad `LegalKeySizes` notifica en instancias de RSA desde <System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>, <System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType> y <System.Security.Cryptography.RSACryptoServicePlatform.%23ctor%2A?displayProperty=nameWithType> en Linux ha aumentado de 384 a 512.</span><span class="sxs-lookup"><span data-stu-id="f307a-104">Starting with .NET Core 3.0, the minimum legal key size reported by the `LegalKeySizes` property on RSA instances from <System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>, <System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType>, and <System.Security.Cryptography.RSACryptoServicePlatform.%23ctor%2A?displayProperty=nameWithType> on Linux has increased from 384 to 512.</span></span>

<span data-ttu-id="f307a-105">Por consiguiente, .NET Core 2.2 y versiones anteriores, una llamada de método como `RSA.Create(384)` se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="f307a-105">As a result, in .NET Core 2.2 and earlier versions, a method call such as `RSA.Create(384)` succeeds.</span></span> <span data-ttu-id="f307a-106">En .NET Core 3.0 y versiones posteriores, la llamada de método `RSA.Create(384)` produce una excepción que indica que el tamaño es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="f307a-106">In .NET Core 3.0 and later versions, the method call `RSA.Create(384)` throws an exception indicating the size is too small.</span></span>

<span data-ttu-id="f307a-107">Estos cambios se realizaron porque OpenSSL, que realiza las operaciones criptográficas en Linux, ha aumentado su mínimo entre las versiones 1.0.2 y 1.1.0.</span><span class="sxs-lookup"><span data-stu-id="f307a-107">This changes was made because OpenSSL, which performs the cryptographic operations on Linux, raised its minimum between versions 1.0.2 and 1.1.0.</span></span>  <span data-ttu-id="f307a-108">.NET Core 3.0 prefiere OpenSSL 1.1. x a 1.0. x, y la versión mínima notificada se elevó para reflejar esta nueva limitación de dependencia más alta.</span><span class="sxs-lookup"><span data-stu-id="f307a-108">.NET Core 3.0 prefers OpenSSL 1.1.x to 1.0.x, and the minimum reported version was raised to reflect this new higher dependency limitation.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f307a-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f307a-109">Version introduced</span></span>

<span data-ttu-id="f307a-110">3.0</span><span class="sxs-lookup"><span data-stu-id="f307a-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f307a-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="f307a-111">Recommended action</span></span>

<span data-ttu-id="f307a-112">Si llama a cualquiera de las API afectadas, asegúrese de que el tamaño de las claves generadas no sea inferior al mínimo del proveedor.</span><span class="sxs-lookup"><span data-stu-id="f307a-112">If you call any of the affected APIs, ensure that the size of any generated keys is not less than the provider minimum.</span></span>

> [!NOTE]
> <span data-ttu-id="f307a-113">El RSA de 384 bits ya se considera inseguro (al igual que el RSA de 512 bits).</span><span class="sxs-lookup"><span data-stu-id="f307a-113">384-bit RSA is already considered insecure (as is 512-bit RSA).</span></span> <span data-ttu-id="f307a-114">Las recomendaciones modernas, como [NIST Special Publication 800-57 Part 1 Revision 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf), sugieren 2048 bits como tamaño mínimo para las claves recién generadas.</span><span class="sxs-lookup"><span data-stu-id="f307a-114">Modern recommendations, such as [NIST Special Publication 800-57 Part 1 Revision 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf), suggest 2048-bit as the minimum size for newly generated keys.</span></span>

#### <a name="category"></a><span data-ttu-id="f307a-115">Categoría</span><span class="sxs-lookup"><span data-stu-id="f307a-115">Category</span></span>

<span data-ttu-id="f307a-116">Criptografía</span><span class="sxs-lookup"><span data-stu-id="f307a-116">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f307a-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f307a-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A?displayProperty=nameWithType>

<!--
### Affected APIs

- `P:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes`
- `Overload:System.Security.Cryptography.RSA.Create`
- `Overload:System.Security.Cryptography.RSAOpenSsl.#ctor`
- `Overload:System.Security.Cryptography.RSACryptoServiceProvider.#ctor`


-->
