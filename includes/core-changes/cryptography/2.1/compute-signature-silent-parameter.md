---
ms.openlocfilehash: b861dbaa02c97a03c015fdf4e63d25c40c90ea0a
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83720925"
---
### <a name="boolean-parameter-of-signedcmscomputesignature-is-respected"></a><span data-ttu-id="ca7a4-101">Se respeta el parámetro booleano de SignedCms.ComputeSignature</span><span class="sxs-lookup"><span data-stu-id="ca7a4-101">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>

<span data-ttu-id="ca7a4-102">En .NET Core, se respeta el parámetro booleano `silent` del método <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-102">In .NET Core, the Boolean `silent` parameter of the <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> method is respected.</span></span> <span data-ttu-id="ca7a4-103">No se muestra una solicitud de PIN si este parámetro se establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-103">A PIN prompt is not shown if this parameter is set to `true`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="ca7a4-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="ca7a4-104">Change description</span></span>

<span data-ttu-id="ca7a4-105">En .NET Framework, se omite el parámetro `silent` del método <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> y siempre se muestra una solicitud de PIN si lo exige el proveedor.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-105">In .NET Framework, the `silent` parameter of the <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> method is ignored, and a PIN prompt is always shown if required by the provider.</span></span> <span data-ttu-id="ca7a4-106">En .NET Core, se respeta el parámetro `silent` y, si se establece en `true`, nunca se muestra una solicitud de PIN, aunque lo exija el proveedor.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-106">In .NET Core, the `silent` parameter is respected, and if set to `true`, a PIN prompt is never shown, even if it's required by the provider.</span></span>

<span data-ttu-id="ca7a4-107">La compatibilidad con los mensajes CMS/PKCS #7 se presentó en .NET Core en la versión 2.1.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-107">Support for CMS/PKCS #7 messages was introduced into .NET Core in version 2.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ca7a4-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ca7a4-108">Version introduced</span></span>

<span data-ttu-id="ca7a4-109">2.1</span><span class="sxs-lookup"><span data-stu-id="ca7a4-109">2.1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ca7a4-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="ca7a4-110">Recommended action</span></span>

<span data-ttu-id="ca7a4-111">Para asegurarse de que aparece una solicitud de PIN si esta se exige, las aplicaciones de escritorio deben llamar a <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> y establecer el parámetro booleano en `false`.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-111">To ensure a PIN prompt appears if required, desktop applications should call <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> and set the Boolean parameter to `false`.</span></span> <span data-ttu-id="ca7a4-112">El comportamiento resultante es el mismo que en .NET Framework independientemente de si el contexto silencioso está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-112">The resulting behavior is the same as on .NET Framework regardless of whether the silent context is disabled there.</span></span>

#### <a name="category"></a><span data-ttu-id="ca7a4-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="ca7a4-113">Category</span></span>

<span data-ttu-id="ca7a4-114">Criptografía</span><span class="sxs-lookup"><span data-stu-id="ca7a4-114">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ca7a4-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="ca7a4-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)`

-->
