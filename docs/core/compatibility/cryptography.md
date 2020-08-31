---
title: Cambios importantes de criptografía
description: Se enumeran los cambios importantes relacionados con la criptografía en .NET Core.
ms.date: 04/22/2020
ms.openlocfilehash: f7d580938fb7620728b8ff7f67412c9f5bbbb6c3
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558013"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="908a7-103">Cambios importantes de criptografía</span><span class="sxs-lookup"><span data-stu-id="908a7-103">Cryptography breaking changes</span></span>

<span data-ttu-id="908a7-104">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="908a7-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="908a7-105">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="908a7-105">Breaking change</span></span> | <span data-ttu-id="908a7-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="908a7-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="908a7-107">System.Security.Cryptography.Oid es funcionalmente de solo inicialización</span><span class="sxs-lookup"><span data-stu-id="908a7-107">System.Security.Cryptography.Oid is functionally init-only</span></span>](#systemsecuritycryptographyoid-is-functionally-init-only) | <span data-ttu-id="908a7-108">5.0</span><span class="sxs-lookup"><span data-stu-id="908a7-108">5.0</span></span> |
| [<span data-ttu-id="908a7-109">Ya no se admite la sintaxis "BEGIN TRUSTED CERTIFICATE" en Linux</span><span class="sxs-lookup"><span data-stu-id="908a7-109">BEGIN TRUSTED CERTIFICATE syntax no longer supported on Linux</span></span>](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | <span data-ttu-id="908a7-110">3.0</span><span class="sxs-lookup"><span data-stu-id="908a7-110">3.0</span></span> |
| [<span data-ttu-id="908a7-111">EnvelopedCms usa de forma predeterminada el cifrado AES-256</span><span class="sxs-lookup"><span data-stu-id="908a7-111">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="908a7-112">3.0</span><span class="sxs-lookup"><span data-stu-id="908a7-112">3.0</span></span> |
| [<span data-ttu-id="908a7-113">Ha aumentado el tamaño mínimo de la generación de claves RSAOpenSsl</span><span class="sxs-lookup"><span data-stu-id="908a7-113">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="908a7-114">3.0</span><span class="sxs-lookup"><span data-stu-id="908a7-114">3.0</span></span> |
| [<span data-ttu-id="908a7-115">.NET Core 3.0 prefiere OpenSSL 1.1.x a OpenSSL 1.0.x</span><span class="sxs-lookup"><span data-stu-id="908a7-115">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="908a7-116">3.0</span><span class="sxs-lookup"><span data-stu-id="908a7-116">3.0</span></span> |
| [<span data-ttu-id="908a7-117">Se respeta el parámetro booleano de SignedCms.ComputeSignature</span><span class="sxs-lookup"><span data-stu-id="908a7-117">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="908a7-118">2.1</span><span class="sxs-lookup"><span data-stu-id="908a7-118">2.1</span></span> |

## <a name="net-50"></a><span data-ttu-id="908a7-119">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="908a7-119">.NET 5.0</span></span>

[!INCLUDE [cryptography-oid-init-only](../../../includes/core-changes/cryptography/5.0/cryptography-oid-init-only.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="908a7-120">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="908a7-120">.NET Core 3.0</span></span>

[!INCLUDE [begin-trusted-cert-linux](~/includes/core-changes/cryptography/3.0/begin-trusted-cert-linux.md)]

***

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="908a7-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="908a7-121">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***
