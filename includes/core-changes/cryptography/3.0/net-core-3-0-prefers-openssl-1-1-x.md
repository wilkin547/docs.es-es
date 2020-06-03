---
ms.openlocfilehash: 877f9d99b660c4af843e4d8d525219c1df6c99a9
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721070"
---
### <a name="net-core-30-prefers-openssl-11x-to-openssl-10x"></a><span data-ttu-id="f28e1-101">.NET Core 3.0 prefiere OpenSSL 1.1.x a OpenSSL 1.0.x</span><span class="sxs-lookup"><span data-stu-id="f28e1-101">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>

<span data-ttu-id="f28e1-102">.NET Core para Linux, que funciona en varias distribuciones de Linux, puede admitir OpenSSL 1.0.x y OpenSSL 1.1.x.</span><span class="sxs-lookup"><span data-stu-id="f28e1-102">.NET Core for Linux, which works across multiple Linux distributions, can support both OpenSSL 1.0.x and OpenSSL 1.1.x.</span></span>  <span data-ttu-id="f28e1-103">.NET Core 2.1 y .NET Core 2.2 buscan 1.0.x primero y luego recurren a 1.1.x; .NET Core 3.0 busca 1.1.x primero.</span><span class="sxs-lookup"><span data-stu-id="f28e1-103">.NET Core 2.1 and .NET Core 2.2 look for 1.0.x first, then fall back to 1.1.x; .NET Core 3.0 looks for 1.1.x first.</span></span> <span data-ttu-id="f28e1-104">Este cambio se realizó para agregar compatibilidad con nuevos estándares criptográficos.</span><span class="sxs-lookup"><span data-stu-id="f28e1-104">This change was made to add support for new cryptographic standards.</span></span>

<span data-ttu-id="f28e1-105">Este cambio puede afectar a las bibliotecas o aplicaciones que llevan a cabo la interoperabilidad de la plataforma con los tipos de interoperabilidad específicos de OpenSSL en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f28e1-105">This change may impact libraries or applications that do platform interop with the OpenSSL-specific interop types in .NET Core.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f28e1-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="f28e1-106">Change description</span></span>

<span data-ttu-id="f28e1-107">En .NET Core 2.2 y versiones anteriores, el runtime prefiere cargar OpenSSL 1.0.x a 1.1.x.</span><span class="sxs-lookup"><span data-stu-id="f28e1-107">In .NET Core 2.2 and earlier versions, the runtime prefers loading OpenSSL 1.0.x over 1.1.x.</span></span> <span data-ttu-id="f28e1-108">Esto significa que los tipos <xref:System.IntPtr> y <xref:System.Runtime.InteropServices.SafeHandle> para la interoperabilidad con OpenSSL se usan, por orden de preferencia, con libcrypto.so.1.0.0 / libcrypto.so.1.0 / libcrypto.so.10.</span><span class="sxs-lookup"><span data-stu-id="f28e1-108">This means that the <xref:System.IntPtr> and <xref:System.Runtime.InteropServices.SafeHandle> types for interop with OpenSSL are used with libcrypto.so.1.0.0 / libcrypto.so.1.0 / libcrypto.so.10 by preference.</span></span>

<span data-ttu-id="f28e1-109">A partir de .NET Core 3.0, el runtime prefiere cargar OpenSSL 1.1.x a OpenSSL 1.0.x, por lo que los tipos <xref:System.IntPtr> y <xref:System.Runtime.InteropServices.SafeHandle> para la interoperabilidad con OpenSSL se usan, por orden de preferencia, con libcrypto.so.1.1 / libcrypto.so.11 / libcrypto.so.1.1.0 / libcrypto.so.1.1.1.</span><span class="sxs-lookup"><span data-stu-id="f28e1-109">Starting with .NET Core 3.0, the runtime prefers loading OpenSSL 1.1.x over OpenSSL 1.0.x, so the <xref:System.IntPtr> and <xref:System.Runtime.InteropServices.SafeHandle> types for interop with OpenSSL are used with libcrypto.so.1.1 / libcrypto.so.11 / libcrypto.so.1.1.0 / libcrypto.so.1.1.1 by preference.</span></span> <span data-ttu-id="f28e1-110">Por consiguiente, las bibliotecas y aplicaciones que interactúan directamente con OpenSSL pueden tener punteros incompatibles con los valores expuestos en .NET Core cuando se actualiza desde .NET Core 2.1 o.NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="f28e1-110">As a result, libraries and applications that interoperate with OpenSSL directly may have incompatible pointers with the .NET Core-exposed values when upgrading from .NET Core 2.1 or .NET Core 2.2.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f28e1-111">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f28e1-111">Version introduced</span></span>

<span data-ttu-id="f28e1-112">3.0</span><span class="sxs-lookup"><span data-stu-id="f28e1-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f28e1-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="f28e1-113">Recommended action</span></span>

<span data-ttu-id="f28e1-114">Las bibliotecas y aplicaciones que realizan operaciones directas con OpenSSL deben tener cuidado de asegurarse de que usan la misma versión de OpenSSL que el runtime de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f28e1-114">Libraries and applications that do direct operations with OpenSSL need to be careful to ensure they are using the same version of OpenSSL as the .NET Core runtime.</span></span>

<span data-ttu-id="f28e1-115">Todas las bibliotecas o aplicaciones que usan los valores <xref:System.IntPtr> o <xref:System.Runtime.InteropServices.SafeHandle> de los tipos criptográficos de .NET Core directamente con OpenSSL deben comparar la versión de la biblioteca que usan con la nueva propiedad <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> para asegurarse de que los punteros son compatible.</span><span class="sxs-lookup"><span data-stu-id="f28e1-115">All libraries or applications that use <xref:System.IntPtr> or <xref:System.Runtime.InteropServices.SafeHandle> values from the .NET Core cryptographic types directly with OpenSSL should compare the version of the library they use with the new <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> property to ensure the pointers are compatible.</span></span>

#### <a name="category"></a><span data-ttu-id="f28e1-116">Categoría</span><span class="sxs-lookup"><span data-stu-id="f28e1-116">Category</span></span>

<span data-ttu-id="f28e1-117">Criptografía</span><span class="sxs-lookup"><span data-stu-id="f28e1-117">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f28e1-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f28e1-118">Affected APIs</span></span>

- <xref:System.Security.Cryptography.SafeEvpPKeyHandle.%23ctor%2A>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor(System.IntPtr)>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)>
- <xref:System.Security.Cryptography.RSAOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSAOpenSsl.%23ctor(System.IntPtr)>
- <xref:System.Security.Cryptography.DSAOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)>
- <xref:System.Security.Cryptography.DSAOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.%23ctor(System.IntPtr)>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.%23ctor(System.IntPtr)>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Handle?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Security.Cryptography.SafeEvpPKeyHandle.#ctor`
- `M:System.Security.Cryptography.RSAOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.RSAOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.RSAOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.DSAOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.DSAOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.DSAOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.ECDsaOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.ECDsaOpenSsl.#ctor(System.Security.CryptographySafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.ECDsaOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.DuplicateKeyHandle`
- `P:System.Security.Cryptography.X509Certificates.X509Certificate.Handle`

-->
