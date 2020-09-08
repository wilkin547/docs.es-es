---
ms.openlocfilehash: 4788f5b80306116e63ee56584d65b862ce0606ee
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496539"
---
### <a name="rsacng-and-dsacng-are-once-again-usable-in-partial-trust-scenarios"></a><span data-ttu-id="2889e-101">Se puede volver a usar RSACng y DSACng en escenarios de confianza parcial</span><span class="sxs-lookup"><span data-stu-id="2889e-101">RSACng and DSACng are once again usable in Partial Trust scenarios</span></span>

#### <a name="details"></a><span data-ttu-id="2889e-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="2889e-102">Details</span></span>

<span data-ttu-id="2889e-103">En algunos casos, CngLightup (que se usa en varias API de criptografía de nivel superior, como <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>) y <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> se basan en la plena confianza.</span><span class="sxs-lookup"><span data-stu-id="2889e-103">CngLightup (used in several higher-level crypto apis, such as <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>) and <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> in some cases rely on full trust.</span></span> <span data-ttu-id="2889e-104">Estos casos incluyen P/Invoke sin permisos <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> de aserción y rutas de código en las que <xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType> tiene peticiones de permiso para <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2889e-104">These include P/Invokes without asserting <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> permissions, and code paths where <xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType> has permission demands for <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2889e-105">A partir de .NET Framework 4.6.2, CngLightup se usaba para cambiar a <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> siempre que era posible.</span><span class="sxs-lookup"><span data-stu-id="2889e-105">Starting with the .NET Framework 4.6.2, CngLightup was used to switch to <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> wherever possible.</span></span> <span data-ttu-id="2889e-106">Como resultado, las aplicaciones de confianza parcial que usaban <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType> correctamente comenzaron a producir errores e iniciar <xref:System.Security.SecurityException> excepciones. Este cambio agrega las aserciones necesarias para que todas las funciones en las que se usa CngLightup tengan los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="2889e-106">As a result, partial trust apps that successfully used <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType> began to fail and throw <xref:System.Security.SecurityException> exceptions.This change adds the required asserts so that all functions using CngLightup have the required permissions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2889e-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="2889e-107">Suggestion</span></span>

<span data-ttu-id="2889e-108">Si este cambio en .NET Framework 4.6.2 ha afectado negativamente a las aplicaciones de confianza parcial, actualice a .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="2889e-108">If this change in the .NET Framework 4.6.2 has negatively impacted your partial trust apps, upgrade to the .NET Framework 4.7.1.</span></span>

| <span data-ttu-id="2889e-109">Nombre</span><span class="sxs-lookup"><span data-stu-id="2889e-109">Name</span></span>    | <span data-ttu-id="2889e-110">Valor</span><span class="sxs-lookup"><span data-stu-id="2889e-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2889e-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="2889e-111">Scope</span></span>   |<span data-ttu-id="2889e-112">Borde</span><span class="sxs-lookup"><span data-stu-id="2889e-112">Edge</span></span>|
|<span data-ttu-id="2889e-113">Versión</span><span class="sxs-lookup"><span data-stu-id="2889e-113">Version</span></span>|<span data-ttu-id="2889e-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="2889e-114">4.6.2</span></span>|
|<span data-ttu-id="2889e-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="2889e-115">Type</span></span>|<span data-ttu-id="2889e-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="2889e-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="2889e-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="2889e-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.DSACng.%23ctor(System.Security.Cryptography.CngKey)>
- <xref:System.Security.Cryptography.DSACng.Key?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSACng.LegalKeySizes?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.%23ctor(System.Security.Cryptography.CngKey)>
- <xref:System.Security.Cryptography.RSACng.Key?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.DSACng.#ctor(System.Security.Cryptography.CngKey)`
- `P:System.Security.Cryptography.DSACng.Key`
- `P:System.Security.Cryptography.DSACng.LegalKeySizes`
- `M:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])`
- `M:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])`
- `M:System.Security.Cryptography.RSACng.#ctor(System.Security.Cryptography.CngKey)`
- `P:System.Security.Cryptography.RSACng.Key`
- `M:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)`
- `M:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)`

-->
