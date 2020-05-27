---
ms.openlocfilehash: 3c6142fd536bad5676f02570fecd4eb0605db829
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721645"
---
### <a name="begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux"></a><span data-ttu-id="e6463-101">Ya no se admite la sintaxis "BEGIN TRUSTED CERTIFICATE" en certificados raíz de Linux</span><span class="sxs-lookup"><span data-stu-id="e6463-101">"BEGIN TRUSTED CERTIFICATE" syntax no longer supported for root certificates on Linux</span></span>

<span data-ttu-id="e6463-102">Los certificados raíz de Linux y otros sistemas similares a Unix (a excepción de macOS) se pueden presentar de dos formas: el encabezado PEM `BEGIN CERTIFICATE` estándar y el encabezado PEM `BEGIN TRUSTED CERTIFICATE` específico de OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="e6463-102">Root certificates on Linux and other Unix-like systems (but not macOS) can be presented in two forms: the standard `BEGIN CERTIFICATE` PEM header, and the OpenSSL-specific `BEGIN TRUSTED CERTIFICATE` PEM header.</span></span> <span data-ttu-id="e6463-103">La última sintaxis permite una configuración adicional que ha provocado problemas de compatibilidad con la clase <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName> de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e6463-103">The latter syntax allows for additional configuration that has caused compatibility issues with .NET Core's <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName> class.</span></span> <span data-ttu-id="e6463-104">El motor de cadena ya no carga el contenido del certificado raíz `BEGIN TRUSTED CERTIFICATE` a partir de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e6463-104">`BEGIN TRUSTED CERTIFICATE` root certificate contents are no longer loaded by the chain engine starting in .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e6463-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="e6463-105">Change description</span></span>

<span data-ttu-id="e6463-106">Anteriormente, las sintaxis `BEGIN CERTIFICATE` y `BEGIN TRUSTED CERTIFICATE` se usaban para rellenar la lista de confianza raíz.</span><span class="sxs-lookup"><span data-stu-id="e6463-106">Previously, both the `BEGIN CERTIFICATE` and `BEGIN TRUSTED CERTIFICATE` syntaxes were used to populate the root trust list.</span></span> <span data-ttu-id="e6463-107">Si se ha usado la sintaxis `BEGIN TRUSTED CERTIFICATE` y se han especificado opciones adicionales en el archivo, es posible que <xref:System.Security.Cryptography.X509Certificates.X509Chain> haya informado de que la confianza de cadena no se permite explícitamente (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.ExplicitDistrust?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="e6463-107">If the `BEGIN TRUSTED CERTIFICATE` syntax was used and additional options were specified in the file, <xref:System.Security.Cryptography.X509Certificates.X509Chain> may have reported that the chain trust was explicitly disallowed (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.ExplicitDistrust?displayProperty=nameWithType>).</span></span> <span data-ttu-id="e6463-108">Con todo, si el certificado también se había especificado con la sintaxis `BEGIN CERTIFICATE` en un archivo cargado anteriormente, se permitía la confianza de cadena.</span><span class="sxs-lookup"><span data-stu-id="e6463-108">However, if the certificate was also specified with the `BEGIN CERTIFICATE` syntax in a previously loaded file, the chain trust was allowed.</span></span>

<span data-ttu-id="e6463-109">A partir de .NET Core 3.0, ya no se lee el contenido de `BEGIN TRUSTED CERTIFICATE`.</span><span class="sxs-lookup"><span data-stu-id="e6463-109">Starting in .NET Core 3.0, `BEGIN TRUSTED CERTIFICATE` contents are no longer read.</span></span> <span data-ttu-id="e6463-110">Si el certificado no se especifica también mediante una sintaxis `BEGIN CERTIFICATE` estándar, <xref:System.Security.Cryptography.X509Certificates.X509Chain> informa de que la raíz no es de confianza (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.UntrustedRoot?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="e6463-110">If the certificate is not also specified via a standard `BEGIN CERTIFICATE` syntax, the <xref:System.Security.Cryptography.X509Certificates.X509Chain> reports that the root is not trusted (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.UntrustedRoot?displayProperty=nameWithType>).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e6463-111">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="e6463-111">Version introduced</span></span>

<span data-ttu-id="e6463-112">3.0</span><span class="sxs-lookup"><span data-stu-id="e6463-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e6463-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="e6463-113">Recommended action</span></span>

<span data-ttu-id="e6463-114">La mayoría de las aplicaciones no se ven afectadas por este cambio, pero las aplicaciones que no pueden ver ambos orígenes del certificado raíz por problemas de permisos pueden experimentar errores inesperados de `UntrustedRoot` después de actualizarse.</span><span class="sxs-lookup"><span data-stu-id="e6463-114">Most applications are unaffected by this change, but applications that cannot see both root certificate sources because of permissions problems may experience unexpected `UntrustedRoot` errors after upgrading.</span></span>

<span data-ttu-id="e6463-115">Muchas distribuciones de Linux escriben certificados raíz en dos ubicaciones: un directorio con un certificado por archivo y una concatenación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="e6463-115">Many Linux distributions (or distros) write root certificates into two locations: a one-certificate-per-file directory, and a one-file concatenation.</span></span> <span data-ttu-id="e6463-116">En algunas distribuciones, el directorio con un certificado por archivo usa la sintaxis `BEGIN TRUSTED CERTIFICATE` mientras que la concatenación de archivos usa la sintaxis `BEGIN CERTIFICATE` estándar.</span><span class="sxs-lookup"><span data-stu-id="e6463-116">On some distros, the one-certificate-per-file directory uses the `BEGIN TRUSTED CERTIFICATE` syntax while the file concatenation uses the standard `BEGIN CERTIFICATE` syntax.</span></span> <span data-ttu-id="e6463-117">Asegúrese de que los certificados raíz personalizados se agregan como `BEGIN CERTIFICATE` en al menos una de estas ubicaciones y que la aplicación puede leer ambas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="e6463-117">Ensure that any custom root certificates are added as `BEGIN CERTIFICATE` in at least one of these locations, and that both locations can be read by your application.</span></span>

<span data-ttu-id="e6463-118">El directorio típico es */etc/ssl/certs/* y el archivo concatenado típico es */etc/ssl/cert.pem*.</span><span class="sxs-lookup"><span data-stu-id="e6463-118">The typical directory is */etc/ssl/certs/* and the typical concatenated file is */etc/ssl/cert.pem*.</span></span> <span data-ttu-id="e6463-119">Use el comando `openssl version -d` para determinar la raíz específica de la plataforma, que puede ser diferente de */etc/ssl/* .</span><span class="sxs-lookup"><span data-stu-id="e6463-119">Use the command `openssl version -d` to determine the platform-specific root, which may differ from */etc/ssl/*.</span></span> <span data-ttu-id="e6463-120">Por ejemplo, en Ubuntu 18.04, el directorio es */usr/lib/ssl/certs/* y el archivo es */usr/lib/ssl/cert.pem*.</span><span class="sxs-lookup"><span data-stu-id="e6463-120">For example, on Ubuntu 18.04, the directory is */usr/lib/ssl/certs/* and the file is */usr/lib/ssl/cert.pem*.</span></span> <span data-ttu-id="e6463-121">A pesar de esto, */usr/lib/ssl/certs/* es un vínculo simbólico a */etc/ssl/certs/* y */usr/lib/ssl/cert.pem* no existe.</span><span class="sxs-lookup"><span data-stu-id="e6463-121">However, */usr/lib/ssl/certs/* is a symlink to */etc/ssl/certs/* and */usr/lib/ssl/cert.pem* does not exist.</span></span>

```bash
$ openssl version -d
OPENSSLDIR: "/usr/lib/ssl"
$ ls -al /usr/lib/ssl
total 12
drwxr-xr-x  3 root root 4096 Dec 12 17:10 .
drwxr-xr-x 73 root root 4096 Feb 20 15:18 ..
lrwxrwxrwx  1 root root   14 Mar 27  2018 certs -> /etc/ssl/certs
drwxr-xr-x  2 root root 4096 Dec 12 17:10 misc
lrwxrwxrwx  1 root root   20 Nov 12 16:58 openssl.cnf -> /etc/ssl/openssl.cnf
lrwxrwxrwx  1 root root   16 Mar 27  2018 private -> /etc/ssl/private
```

#### <a name="category"></a><span data-ttu-id="e6463-122">Categoría</span><span class="sxs-lookup"><span data-stu-id="e6463-122">Category</span></span>

<span data-ttu-id="e6463-123">Criptografía</span><span class="sxs-lookup"><span data-stu-id="e6463-123">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e6463-124">API afectadas</span><span class="sxs-lookup"><span data-stu-id="e6463-124">Affected APIs</span></span>

- <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.X509Certificates.X509Chain`

-->
