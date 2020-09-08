---
ms.openlocfilehash: c8f017084fc1ec1eca636ef0178a40559e15b2c5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497530"
---
### <a name="improved-wcf-chain-trust-certificate-validation-for-nettcp-certificate-authentication"></a><span data-ttu-id="399db-101">Mejora de la validación de certificados de confianza de cadena de WCF para la autenticación de certificados de Net.Tcp</span><span class="sxs-lookup"><span data-stu-id="399db-101">Improved WCF chain trust certificate validation for Net.Tcp certificate authentication</span></span>

#### <a name="details"></a><span data-ttu-id="399db-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="399db-102">Details</span></span>

<span data-ttu-id="399db-103">.NET Framework 4.7.2 mejora la validación de certificados de confianza de cadena al usar la autenticación de certificados con seguridad de transporte con WCF.</span><span class="sxs-lookup"><span data-stu-id="399db-103">.NET Framework 4.7.2 improves chain trust certificate validation when using certificate authentication with transport security with WCF.</span></span> <span data-ttu-id="399db-104">Con esta mejora, los certificados de cliente que se usan para la autenticación en un servidor se deben configurar para la autenticación de cliente.</span><span class="sxs-lookup"><span data-stu-id="399db-104">With this improvement, client certificates that are used to authenticate to a server must be configured for client authentication.</span></span>  <span data-ttu-id="399db-105">De forma similar, los certificados de servidor que sirven para autenticar un servidor se deben configurar para la autenticación de servidor.</span><span class="sxs-lookup"><span data-stu-id="399db-105">Similarly server certificates that are for the authenticating a server must be configured for server authentication.</span></span> <span data-ttu-id="399db-106">Con este cambio, si el certificado raíz está deshabilitado, se produce un error en la validación de la cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="399db-106">With this change, if the root certificate is disabled, the certificate chain validation fails.</span></span> <span data-ttu-id="399db-107">El mismo cambio también se realizó en .NET Framework 3.5 y versiones posteriores mediante la acumulación de seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="399db-107">The same change was also made to .NET Framework 3.5 and later versions via Windows security roll-up.</span></span> <span data-ttu-id="399db-108">Puede encontrar más información [aquí](https://support.microsoft.com/help/4055269/security-only-update-for-net-framework-3-5-1-4-5-2-4-6-4-6-1-4-6-2-4-7). Este cambio se activa de forma predeterminada y se puede desactivar con una opción de configuración.</span><span class="sxs-lookup"><span data-stu-id="399db-108">You can find more information [here](https://support.microsoft.com/help/4055269/security-only-update-for-net-framework-3-5-1-4-5-2-4-6-4-6-1-4-6-2-4-7).This change is on by default and can be turned off by a configuration setting.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="399db-109">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="399db-109">Suggestion</span></span>

<ul><li><span data-ttu-id="399db-110">Valide si la certificación de servidor y cliente tiene el OID del EKU necesario.</span><span class="sxs-lookup"><span data-stu-id="399db-110">Validate if your server and client certification has the required EKU OID.</span></span> <span data-ttu-id="399db-111">Si no es así, actualice la certificación.</span><span class="sxs-lookup"><span data-stu-id="399db-111">If not, update your certification.</span></span></li><li><span data-ttu-id="399db-112">Compruebe si el certificado raíz no es válido.</span><span class="sxs-lookup"><span data-stu-id="399db-112">Validate if your root certificate is invalid.</span></span> <span data-ttu-id="399db-113">Si es así, actualice el certificado raíz.</span><span class="sxs-lookup"><span data-stu-id="399db-113">If so, update the root certificate.</span></span></li><li><span data-ttu-id="399db-114">Cómo descartar el cambio: si no puede actualizar el certificado, puede evitar temporalmente la novedad con la opción de configuración siguiente. Pero no participar en el cambio dejará el sistema vulnerable al problema de seguridad.</span><span class="sxs-lookup"><span data-stu-id="399db-114">How to opt out of the change: If you can't update the certificate, you can work around the breaking change temporarily with the following configration setting,  However, opting out of the change will leave your system vulnerable to the security issue.</span></span></li></ul><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;wcf:useLegacyCertificateUsagePolicy&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="399db-115">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="399db-115">Name</span></span>    | <span data-ttu-id="399db-116">Valor</span><span class="sxs-lookup"><span data-stu-id="399db-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="399db-117">Ámbito</span><span class="sxs-lookup"><span data-stu-id="399db-117">Scope</span></span>   |<span data-ttu-id="399db-118">Secundaria</span><span class="sxs-lookup"><span data-stu-id="399db-118">Minor</span></span>|
|<span data-ttu-id="399db-119">Versión</span><span class="sxs-lookup"><span data-stu-id="399db-119">Version</span></span>|<span data-ttu-id="399db-120">4.7.2</span><span class="sxs-lookup"><span data-stu-id="399db-120">4.7.2</span></span>|
|<span data-ttu-id="399db-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="399db-121">Type</span></span>|<span data-ttu-id="399db-122">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="399db-122">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="399db-123">API afectadas</span><span class="sxs-lookup"><span data-stu-id="399db-123">Affected APIs</span></span>

<span data-ttu-id="399db-124">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="399db-124">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
