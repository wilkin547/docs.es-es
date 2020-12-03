---
title: 'Cambio importante: Conjuntos de cifrado TLS predeterminados para .NET en Linux'
description: Obtenga información sobre el cambio importante en .NET 5.0, donde .NET, para Linux ahora respeta la configuración de OpenSSL para los conjuntos de cifrado predeterminados al realizar TLS/SSL.
ms.date: 10/16/2020
ms.openlocfilehash: f1c23517161ac213a9cd7cf6e7da8eebeb91583b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760084"
---
# <a name="default-tls-cipher-suites-for-net-on-linux"></a><span data-ttu-id="8370d-103">Conjuntos de cifrado TLS predeterminados para .NET en Linux</span><span class="sxs-lookup"><span data-stu-id="8370d-103">Default TLS cipher suites for .NET on Linux</span></span>

<span data-ttu-id="8370d-104">Ahora .NET en Linux respeta la configuración de OpenSSL para los conjuntos de cifrado predeterminados al realizar TLS/SSL a través de la clase <xref:System.Net.Security.SslStream> o de las operaciones de nivel superior, como HTTPS a través de la clase <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="8370d-104">.NET, on Linux, now respects the OpenSSL configuration for default cipher suites when doing TLS/SSL via the <xref:System.Net.Security.SslStream> class or higher-level operations, such as HTTPS via the <xref:System.Net.Http.HttpClient> class.</span></span> <span data-ttu-id="8370d-105">Cuando los conjuntos de cifrado predeterminados no se configuran de forma explícita, .NET en Linux usa una lista rigurosamente restringida de conjuntos de cifrado permitidos.</span><span class="sxs-lookup"><span data-stu-id="8370d-105">When default cipher suites aren't explicitly configured, .NET on Linux uses a tightly restricted list of permitted cipher suites.</span></span>

## <a name="change-description"></a><span data-ttu-id="8370d-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="8370d-106">Change description</span></span>

<span data-ttu-id="8370d-107">En versiones anteriores, .NET no respeta la configuración del sistema para los conjuntos de cifrado predeterminados.</span><span class="sxs-lookup"><span data-stu-id="8370d-107">In previous .NET versions, .NET does not respect system configuration for default cipher suites.</span></span> <span data-ttu-id="8370d-108">La lista de conjuntos de cifrado predeterminados para .NET en Linux es muy permisiva.</span><span class="sxs-lookup"><span data-stu-id="8370d-108">The default cipher suite list for .NET on Linux is very permissive.</span></span>

<span data-ttu-id="8370d-109">A partir de .NET 5.0, .NET en Linux respeta la configuración de OpenSSL para los conjuntos de cifrado predeterminados cuando se especifica en *openssl.cnf*.</span><span class="sxs-lookup"><span data-stu-id="8370d-109">Starting in .NET 5.0, .NET on Linux respects the OpenSSL configuration for default cipher suites when it's specified in *openssl.cnf*.</span></span> <span data-ttu-id="8370d-110">Cuando los conjuntos de cifrado no se configuran de forma explícita, los únicos que se permiten son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8370d-110">When cipher suites aren't explicitly configured, the only permitted cipher suites are as follows:</span></span>

- <span data-ttu-id="8370d-111">Conjuntos de cifrado TLS 1.3</span><span class="sxs-lookup"><span data-stu-id="8370d-111">TLS 1.3 cipher suites</span></span>
- <span data-ttu-id="8370d-112">TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384</span><span class="sxs-lookup"><span data-stu-id="8370d-112">TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384</span></span>
- <span data-ttu-id="8370d-113">TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256</span><span class="sxs-lookup"><span data-stu-id="8370d-113">TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256</span></span>
- <span data-ttu-id="8370d-114">TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384</span><span class="sxs-lookup"><span data-stu-id="8370d-114">TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384</span></span>
- <span data-ttu-id="8370d-115">TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256</span><span class="sxs-lookup"><span data-stu-id="8370d-115">TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256</span></span>
- <span data-ttu-id="8370d-116">TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384</span><span class="sxs-lookup"><span data-stu-id="8370d-116">TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384</span></span>
- <span data-ttu-id="8370d-117">TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="8370d-117">TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256</span></span>
- <span data-ttu-id="8370d-118">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384</span><span class="sxs-lookup"><span data-stu-id="8370d-118">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384</span></span>
- <span data-ttu-id="8370d-119">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="8370d-119">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256</span></span>

<span data-ttu-id="8370d-120">Como este valor predeterminado de reserva no incluye ningún conjunto de cifrado que sea compatible con TLS 1.0 o TLS 1.1, estas versiones de protocolo anteriores están deshabilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8370d-120">Since this fallback default doesn't include any cipher suites that are compatible with TLS 1.0 or TLS 1.1, these older protocol versions are effectively disabled by default.</span></span>

<span data-ttu-id="8370d-121">Si se proporciona un valor CipherSuitePolicy a SslStream para una sesión específica, se reemplazará el contenido del archivo de configuración o el valor predeterminado de reserva de .NET.</span><span class="sxs-lookup"><span data-stu-id="8370d-121">Supplying a CipherSuitePolicy value to SslStream for a specific session will still replace the configuration file content and/or .NET fallback default.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="8370d-122">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="8370d-122">Reason for change</span></span>

<span data-ttu-id="8370d-123">Los usuarios que ejecutan .NET en Linux han solicitado que la configuración predeterminada de <xref:System.Net.Security.SslStream> se cambie por otra que proporcione una clasificación de alta seguridad de herramientas de evaluación de terceros.</span><span class="sxs-lookup"><span data-stu-id="8370d-123">Users running .NET on Linux requested that the default configuration for <xref:System.Net.Security.SslStream> be changed to one that provided a high security rating from third-party assessment tools.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="8370d-124">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="8370d-124">Version introduced</span></span>

<span data-ttu-id="8370d-125">5.0</span><span class="sxs-lookup"><span data-stu-id="8370d-125">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="8370d-126">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="8370d-126">Recommended action</span></span>

<span data-ttu-id="8370d-127">Es probable que los nuevos valores predeterminados funcionen al comunicarse con servidores o clientes modernos.</span><span class="sxs-lookup"><span data-stu-id="8370d-127">The new defaults are likely to work when communicating with modern clients or servers.</span></span> <span data-ttu-id="8370d-128">Si tiene que expandir la lista de conjuntos de cifrado predeterminados para aceptar clientes heredados (o para ponerse en contacto con servidores heredados), especifique un valor de `CipherSuitePolicy` o cambie el archivo de configuración de OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="8370d-128">If you need to expand the default cipher suite list to accept legacy clients (or to contact legacy servers), either specify a `CipherSuitePolicy` value or change the OpenSSL configuration file.</span></span> <span data-ttu-id="8370d-129">En muchas distribuciones de Linux, el archivo de configuración de OpenSSL está en */etc/ssl/openssl.cnf*.</span><span class="sxs-lookup"><span data-stu-id="8370d-129">On many Linux distributions, the OpenSSL configuration file is at */etc/ssl/openssl.cnf*.</span></span>

<span data-ttu-id="8370d-130">Este archivo *openssl.cnf* de ejemplo es un archivo mínimo que equivale a la directiva de conjuntos de cifrado predeterminados para .NET 5.0 y versiones posteriores en Linux.</span><span class="sxs-lookup"><span data-stu-id="8370d-130">This sample *openssl.cnf* file is a minimal file that's equivalent to the default cipher suites policy for .NET 5.0 and later on Linux.</span></span> <span data-ttu-id="8370d-131">En lugar de reemplazar el archivo del sistema, combine estos conceptos con el archivo que se encuentre en el sistema.</span><span class="sxs-lookup"><span data-stu-id="8370d-131">Instead of replacing the system file, merge these concepts with the file that's present on your system.</span></span>

```ini
openssl_conf = default_conf

[default_conf]
ssl_conf = ssl_sect

[ssl_sect]
system_default = system_default_sect

[system_default_sect]
CipherString = ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES256-SHA384:ECDHE-RSA-AES128-SHA256
```

<span data-ttu-id="8370d-132">En las distribuciones Red Hat Enterprise Linux, CentOS y Fedora, las aplicaciones .NET tienen como valor predeterminado los conjuntos de cifrado permitidos por las directivas de cifrado de todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="8370d-132">On the Red Hat Enterprise Linux, CentOS, and Fedora distributions, .NET applications default to the cipher suites permitted by the system-wide cryptographic policies.</span></span> <span data-ttu-id="8370d-133">En estas distribuciones, use la configuración de directivas de cifrado en lugar de *openssl.cnf*.</span><span class="sxs-lookup"><span data-stu-id="8370d-133">On these distributions, use the crypto-policies configuration instead of *openssl.cnf*.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="8370d-134">API afectadas</span><span class="sxs-lookup"><span data-stu-id="8370d-134">Affected APIs</span></span>

<span data-ttu-id="8370d-135">No detectable a través del análisis de API.</span><span class="sxs-lookup"><span data-stu-id="8370d-135">Not detectible via API analysis.</span></span>

<!--

### Affected APIs

- Not detectible via API analysis.

### Category

- Cryptography
- Security

-->
