---
ms.openlocfilehash: a4476fbff572c004632153e5a98812c241efca57
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032125"
---
### <a name="openssl-versions-on-macos"></a><span data-ttu-id="604f1-101">Versiones de OpenSSL en macOS</span><span class="sxs-lookup"><span data-stu-id="604f1-101">OpenSSL versions on macOS</span></span>

<span data-ttu-id="604f1-102">Ahora, los runtime de .NET Core 3.0 y versiones posteriores en macOS prefieren las versiones de OpenSSL 1.1.x a las versiones de OpenSSL 1.0.x en los tipos <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl> y <xref:System.Security.Cryptography.SafeEvpPKeyHandle>.</span><span class="sxs-lookup"><span data-stu-id="604f1-102">The .NET Core 3.0 and later runtimes on macOS now prefer OpenSSL 1.1.x versions to OpenSSL 1.0.x versions for the <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl>, and <xref:System.Security.Cryptography.SafeEvpPKeyHandle> types.</span></span>

<span data-ttu-id="604f1-103">Ahora, el runtime de .NET Core 2.1 es compatible con las versiones de OpenSSL 1.1.x, pero siguen siendo preferibles las versiones de OpenSSL 1.0.x.</span><span class="sxs-lookup"><span data-stu-id="604f1-103">The .NET Core 2.1 runtime now supports OpenSSL 1.1.x versions, but still prefers OpenSSL 1.0.x versions.</span></span>

#### <a name="change-description"></a><span data-ttu-id="604f1-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="604f1-104">Change description</span></span>

<span data-ttu-id="604f1-105">Antes, el runtime de .NET Core usaba versiones de OpenSSL 1.0.x en macOS para en los tipos que interactúan con OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="604f1-105">Previously, the .NET Core runtime used OpenSSL 1.0.x versions on macOS for types that interact with OpenSSL.</span></span> <span data-ttu-id="604f1-106">La versión más reciente de OpenSSL 1.0.x, OpenSSL 1.0.2, ya no se admite.</span><span class="sxs-lookup"><span data-stu-id="604f1-106">The most recent OpenSSL 1.0.x version, OpenSSL 1.0.2, is now out of support.</span></span> <span data-ttu-id="604f1-107">Para mantener los tipos que usan OpenSSL en versiones compatibles de OpenSSL, los runtime de .NET Core 3.0 y versiones posteriores usan ahora las versiones más recientes de OpenSSL en macOS.</span><span class="sxs-lookup"><span data-stu-id="604f1-107">To keep types that use OpenSSL on supported versions of OpenSSL, the .NET Core 3.0 and later runtimes now use newer versions of OpenSSL on macOS.</span></span>

<span data-ttu-id="604f1-108">Con este cambio, el comportamiento de los runtime de .NET Core en macOS es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="604f1-108">With this change, the behavior for the .NET Core runtimes on macOS is as follows:</span></span>

- <span data-ttu-id="604f1-109">Los runtime de .NET Core 3.0 y versiones posteriores usan OpenSSL 1.1.x (si está disponible) y revierten a OpenSSL 1.0.x solo si no hay disponible ninguna versión 1.1.x.</span><span class="sxs-lookup"><span data-stu-id="604f1-109">The .NET Core 3.0 and later version runtimes use OpenSSL 1.1.x, if available, and fall back to OpenSSL 1.0.x only if there's no 1.1.x version available.</span></span>

  <span data-ttu-id="604f1-110">En el caso de los autores de llamada que usen los tipos de interoperabilidad de OpenSSL con P/Invoke personalizados, siga las instrucciones de los comentarios sobre <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="604f1-110">For callers that use the OpenSSL interop types with custom P/Invokes, follow the guidance in the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> remarks.</span></span> <span data-ttu-id="604f1-111">La aplicación se puede bloquear si no se comprueba el valor de <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion>.</span><span class="sxs-lookup"><span data-stu-id="604f1-111">Your app may crash if you don't check the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion> value.</span></span>

- <span data-ttu-id="604f1-112">Los runtime de .NET Core 2.1 usan OpenSSL 1.0.x (si está disponible) y revierten a OpenSSL 1.1.x si no hay disponible ninguna versión 1.0.x.</span><span class="sxs-lookup"><span data-stu-id="604f1-112">The .NET Core 2.1 runtime uses OpenSSL 1.0.x, if available, and falls back to OpenSSL 1.1.x if there's no 1.0.x version available.</span></span>

  <span data-ttu-id="604f1-113">El runtime 2.1 prefiere la versión anterior de OpenSSL porque la propiedad <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> no existe en .NET Core 2.1, por lo que la versión de OpenSSL no se puede determinar de forma confiable en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="604f1-113">The 2.1 runtime prefers the earlier version of OpenSSL because the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> property does not exist in .NET Core 2.1, so the OpenSSL version cannot be reliably determined at run time.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="604f1-114">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="604f1-114">Version introduced</span></span>

- <span data-ttu-id="604f1-115">.NET Core 2.1.16</span><span class="sxs-lookup"><span data-stu-id="604f1-115">.NET Core 2.1.16</span></span>
- <span data-ttu-id="604f1-116">.NET Core 3.0.3</span><span class="sxs-lookup"><span data-stu-id="604f1-116">.NET Core 3.0.3</span></span>
- <span data-ttu-id="604f1-117">.NET Core 3.1.2</span><span class="sxs-lookup"><span data-stu-id="604f1-117">.NET Core 3.1.2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="604f1-118">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="604f1-118">Recommended action</span></span>

- <span data-ttu-id="604f1-119">Desinstale la versión 1.0.2 de OpenSSL si ya no la necesita.</span><span class="sxs-lookup"><span data-stu-id="604f1-119">Uninstall OpenSSL version 1.0.2 if it's no longer needed.</span></span>

- <span data-ttu-id="604f1-120">Instale OpenSSL 1.1.x si usa los tipos <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl> o <xref:System.Security.Cryptography.SafeEvpPKeyHandle>.</span><span class="sxs-lookup"><span data-stu-id="604f1-120">Install OpenSSL 1.1.x if you use the <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl>, or <xref:System.Security.Cryptography.SafeEvpPKeyHandle> types.</span></span>

- <span data-ttu-id="604f1-121">Si usa los tipos de interoperabilidad de OpenSSL con P/Invoke personalizados, siga las instrucciones de los comentarios sobre <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="604f1-121">If you use the OpenSSL interop types with custom P/Invokes, follow the guidance in the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> remarks.</span></span>

#### <a name="category"></a><span data-ttu-id="604f1-122">Categoría</span><span class="sxs-lookup"><span data-stu-id="604f1-122">Category</span></span>

<span data-ttu-id="604f1-123">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="604f1-123">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="604f1-124">API afectadas</span><span class="sxs-lookup"><span data-stu-id="604f1-124">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AesCcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.AesGcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.SafeEvpPKeyHandle?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.AesCcm``
- `T:System.Security.Cryptography.AesGcm`
- `T:System.Security.Cryptography.DSAOpenSsl`
- `T:System.Security.Cryptography.ECDiffieHellmanOpenSsl`
- `T:System.Security.Cryptography.ECDsaOpenSsl`
- `T:System.Security.Cryptography.RSAOpenSsl`
- `T:System.Security.Cryptography.SafeEvpPKeyHandle`

-->
