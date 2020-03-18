---
ms.openlocfilehash: 2fb980c8b75e25ba347c56ccc1c90f2959e83e21
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74567974"
---
### <a name="minimum-size-for-rsaopenssl-key-generation-has-increased"></a><span data-ttu-id="fdaf6-101">Ha aumentado el tamaño mínimo de la generación de claves RSAOpenSsl</span><span class="sxs-lookup"><span data-stu-id="fdaf6-101">Minimum size for RSAOpenSsl key generation has increased</span></span>

<span data-ttu-id="fdaf6-102">El tamaño mínimo para generar nuevas claves RSA en Linux ha aumentado de 384 bits a 512 bits.</span><span class="sxs-lookup"><span data-stu-id="fdaf6-102">The minimum size for generating new RSA keys on Linux has increased from 384-bit to 512-bit.</span></span>

#### <a name="change-description"></a><span data-ttu-id="fdaf6-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="fdaf6-103">Change description</span></span>

<span data-ttu-id="fdaf6-104">A partir de .NET Core 3.0, el tamaño mínimo de clave permitido que notifica la propiedad `LegalKeySizes` en instancias de RSA desde <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>, <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType> y <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A?displayProperty=nameWithType> en Linux ha aumentado de 384 a 512.</span><span class="sxs-lookup"><span data-stu-id="fdaf6-104">Starting with .NET Core 3.0, the minimum legal key size reported by the `LegalKeySizes` property on RSA instances from <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>, <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType>, and <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A?displayProperty=nameWithType> on Linux has increased from 384 to 512.</span></span>

<span data-ttu-id="fdaf6-105">Por consiguiente, .NET Core 2.2 y versiones anteriores, una llamada de método como `RSA.Create(384)` se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="fdaf6-105">As a result, in .NET Core 2.2 and earlier versions, a method call such as `RSA.Create(384)` succeeds.</span></span> <span data-ttu-id="fdaf6-106">En .NET Core 3.0 y versiones posteriores, la llamada de método `RSA.Create(384)` produce una excepción que indica que el tamaño es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="fdaf6-106">In .NET Core 3.0 and later versions, the method call `RSA.Create(384)` throws an exception indicating the size is too small.</span></span>

<span data-ttu-id="fdaf6-107">Este cambio se realizó porque OpenSSL, que realiza las operaciones criptográficas en Linux, ha aumentado su mínimo entre las versiones 1.0.2 y 1.1.0.</span><span class="sxs-lookup"><span data-stu-id="fdaf6-107">This change was made because OpenSSL, which performs the cryptographic operations on Linux, raised its minimum between versions 1.0.2 and 1.1.0.</span></span> <span data-ttu-id="fdaf6-108">.NET Core 3.0 prefiere OpenSSL 1.1. x a 1.0. x, y la versión mínima notificada se elevó para reflejar esta nueva limitación de dependencia más alta.</span><span class="sxs-lookup"><span data-stu-id="fdaf6-108">.NET Core 3.0 prefers OpenSSL 1.1.x to 1.0.x, and the minimum reported version was raised to reflect this new higher dependency limitation.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="fdaf6-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="fdaf6-109">Version introduced</span></span>

<span data-ttu-id="fdaf6-110">3.0</span><span class="sxs-lookup"><span data-stu-id="fdaf6-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="fdaf6-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="fdaf6-111">Recommended action</span></span>

<span data-ttu-id="fdaf6-112">Si llama a cualquiera de las API afectadas, asegúrese de que el tamaño de las claves generadas no sea inferior al mínimo del proveedor.</span><span class="sxs-lookup"><span data-stu-id="fdaf6-112">If you call any of the affected APIs, ensure that the size of any generated keys is not less than the provider minimum.</span></span>

> [!NOTE]
> <span data-ttu-id="fdaf6-113">El RSA de 384 bits ya se considera inseguro (al igual que el RSA de 512 bits).</span><span class="sxs-lookup"><span data-stu-id="fdaf6-113">384-bit RSA is already considered insecure (as is 512-bit RSA).</span></span> <span data-ttu-id="fdaf6-114">Las recomendaciones modernas, como [NIST Special Publication 800-57 Part 1 Revision 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf), sugieren 2048 bits como tamaño mínimo para las claves recién generadas.</span><span class="sxs-lookup"><span data-stu-id="fdaf6-114">Modern recommendations, such as [NIST Special Publication 800-57 Part 1 Revision 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf), suggest 2048-bit as the minimum size for newly generated keys.</span></span>

#### <a name="category"></a><span data-ttu-id="fdaf6-115">Categoría</span><span class="sxs-lookup"><span data-stu-id="fdaf6-115">Category</span></span>

<span data-ttu-id="fdaf6-116">Criptografía</span><span class="sxs-lookup"><span data-stu-id="fdaf6-116">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fdaf6-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="fdaf6-117">Affected APIs</span></span>

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
