---
ms.openlocfilehash: 36a9db601f7637185bf48dfcbe2233b4489fcdcf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614656"
---
### <a name="aescryptoserviceprovider-decryptor-provides-a-reusable-transform"></a><span data-ttu-id="e88f3-101">El descifrador AesCryptoServiceProvider proporciona una transformación reutilizable</span><span class="sxs-lookup"><span data-stu-id="e88f3-101">AesCryptoServiceProvider decryptor provides a reusable transform</span></span>

#### <a name="details"></a><span data-ttu-id="e88f3-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="e88f3-102">Details</span></span>

<span data-ttu-id="e88f3-103">A partir de las aplicaciones que tienen como destino .NET Framework 4.6.2, el descifrador <xref:System.Security.Cryptography.AesCryptoServiceProvider> ofrece una transformación reutilizable.</span><span class="sxs-lookup"><span data-stu-id="e88f3-103">Starting with apps that target the .NET Framework 4.6.2, the <xref:System.Security.Cryptography.AesCryptoServiceProvider> decryptor provides a reusable transform.</span></span> <span data-ttu-id="e88f3-104">Después de llamar a <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>, la transformación se reinicializa y se puede reutilizar.</span><span class="sxs-lookup"><span data-stu-id="e88f3-104">After a call to <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>, the transform is reinitialized and can be reused.</span></span> <span data-ttu-id="e88f3-105">Para las aplicaciones que tienen como destino versiones anteriores de .NET Framework, intentar volver a usar el descifrador mediante una llamada a <xref:System.Security.Cryptography.CryptoAPITransform.TransformBlock(System.Byte[],System.Int32,System.Int32,System.Byte[],System.Int32)?displayProperty=fullName> después de llamar a <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> inicia una excepción <xref:System.Security.Cryptography.CryptographicException> o genera datos dañados.</span><span class="sxs-lookup"><span data-stu-id="e88f3-105">For apps that target earlier versions of the .NET Framework, attempting to reuse the decryptor by calling <xref:System.Security.Cryptography.CryptoAPITransform.TransformBlock(System.Byte[],System.Int32,System.Int32,System.Byte[],System.Int32)?displayProperty=fullName> after a call to <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> throws a <xref:System.Security.Cryptography.CryptographicException> or produces corrupted data.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e88f3-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="e88f3-106">Suggestion</span></span>

<span data-ttu-id="e88f3-107">El impacto de este cambio debería ser mínimo, dado que es el comportamiento esperado. Las aplicaciones que dependen del comportamiento anterior pueden rechazar su uso si se agrega el ajuste de configuración siguiente a la sección `<runtime>` del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="e88f3-107">The impact of this change should be minimal, since this is the expected behavior.Applications that depend on the previous behavior can opt out of it using it by adding the following configuration setting to the `<runtime>` section of the application's configuration file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=true"/>
</runtime>
```

<span data-ttu-id="e88f3-108">Además, las aplicaciones que tienen como destino una versión anterior de .NET Framework pero que se ejecutan en una versión de .NET Framework a partir de la 4.6.2 pueden incluirse en este comportamiento si se agrega el ajuste de configuración siguiente a la sección `<runtime>` del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="e88f3-108">In addition, applications that target a previous version of the .NET Framework but are running under a version of the .NET Framework starting with .NET Framework 4.6.2 can opt in to it by adding the following configuration setting to the `<runtime>` section of the application's configuration file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=false"/>
</runtime>
```

| <span data-ttu-id="e88f3-109">Nombre</span><span class="sxs-lookup"><span data-stu-id="e88f3-109">Name</span></span>    | <span data-ttu-id="e88f3-110">Valor</span><span class="sxs-lookup"><span data-stu-id="e88f3-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e88f3-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="e88f3-111">Scope</span></span>   | <span data-ttu-id="e88f3-112">Secundaria</span><span class="sxs-lookup"><span data-stu-id="e88f3-112">Minor</span></span>       |
| <span data-ttu-id="e88f3-113">Versión</span><span class="sxs-lookup"><span data-stu-id="e88f3-113">Version</span></span> | <span data-ttu-id="e88f3-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="e88f3-114">4.6.2</span></span>       |
| <span data-ttu-id="e88f3-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="e88f3-115">Type</span></span>    | <span data-ttu-id="e88f3-116">Redestinación</span><span class="sxs-lookup"><span data-stu-id="e88f3-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="e88f3-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="e88f3-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AesCryptoServiceProvider.CreateDecryptor?displayProperty=nameWithType>
