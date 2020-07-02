---
ms.openlocfilehash: 51208762cea2a5688c5d43e5d444d4e014e5f0b4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621428"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a><span data-ttu-id="49c17-101">X509Certificate2.ToString(Boolean) ahora no se inicia cuando .NET no puede controlar el certificado</span><span class="sxs-lookup"><span data-stu-id="49c17-101">X509Certificate2.ToString(Boolean) does not throw now when .NET cannot handle the certificate</span></span>

#### <a name="details"></a><span data-ttu-id="49c17-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="49c17-102">Details</span></span>

<span data-ttu-id="49c17-103">En .NET Framework 4.5.2 y versiones anteriores, este método iniciaba una excepción si se pasaba <code>true</code> para el parámetro detallado y había certificados instalados no admitidos por .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="49c17-103">In .NET Framework 4.5.2 and earlier versions, this method would throw if <code>true</code> was passed for the verbose parameter and there were certificates installed that weren't supported by the .NET Framework.</span></span> <span data-ttu-id="49c17-104">Ahora, el método se realizará correctamente y devolverá una cadena válida que omite las partes inaccesibles del certificado.</span><span class="sxs-lookup"><span data-stu-id="49c17-104">Now, the method will succeed and return a valid string that omits the inaccessible portions of the certificate.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="49c17-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="49c17-105">Suggestion</span></span>

<span data-ttu-id="49c17-106">Cualquier código que dependa de <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> se debe actualizar para esperar que la cadena devuelta pueda excluir algunos datos del certificado (como la clave pública, la clave privada y las extensiones) en algunos casos en los que anteriormente se habría iniciado la API.</span><span class="sxs-lookup"><span data-stu-id="49c17-106">Any code depending on <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> should be updated to expect that the returned string may exclude some certificate data (such as public key, private key, and extensions) in some cases in which the API would have previously thrown.</span></span>

| <span data-ttu-id="49c17-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="49c17-107">Name</span></span>    | <span data-ttu-id="49c17-108">Valor</span><span class="sxs-lookup"><span data-stu-id="49c17-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="49c17-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="49c17-109">Scope</span></span>   |<span data-ttu-id="49c17-110">Borde</span><span class="sxs-lookup"><span data-stu-id="49c17-110">Edge</span></span>|
|<span data-ttu-id="49c17-111">Versión</span><span class="sxs-lookup"><span data-stu-id="49c17-111">Version</span></span>|<span data-ttu-id="49c17-112">4.6</span><span class="sxs-lookup"><span data-stu-id="49c17-112">4.6</span></span>|
|<span data-ttu-id="49c17-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="49c17-113">Type</span></span>|<span data-ttu-id="49c17-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="49c17-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="49c17-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="49c17-115">Affected APIs</span></span>

-<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|
