---
title: Cambios importantes de criptografía
description: Se enumeran los cambios importantes relacionados con la criptografía en .NET Core 2.1-3.0.
ms.date: 04/22/2020
ms.openlocfilehash: a4801bb4d5a859e2c8c2b536ee0597cb4db2f65d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682658"
---
# <a name="cryptography-breaking-changes-for-net-core-21-30"></a><span data-ttu-id="6f032-103">Cambios importantes de criptografía para .NET Core 2.1-3.0</span><span class="sxs-lookup"><span data-stu-id="6f032-103">Cryptography breaking changes for .NET Core 2.1-3.0</span></span>

<span data-ttu-id="6f032-104">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="6f032-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="6f032-105">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="6f032-105">Breaking change</span></span> | <span data-ttu-id="6f032-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="6f032-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="6f032-107">Ya no se admite la sintaxis "BEGIN TRUSTED CERTIFICATE" en Linux</span><span class="sxs-lookup"><span data-stu-id="6f032-107">BEGIN TRUSTED CERTIFICATE syntax no longer supported on Linux</span></span>](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | <span data-ttu-id="6f032-108">3.0</span><span class="sxs-lookup"><span data-stu-id="6f032-108">3.0</span></span> |
| [<span data-ttu-id="6f032-109">EnvelopedCms usa de forma predeterminada el cifrado AES-256</span><span class="sxs-lookup"><span data-stu-id="6f032-109">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="6f032-110">3.0</span><span class="sxs-lookup"><span data-stu-id="6f032-110">3.0</span></span> |
| [<span data-ttu-id="6f032-111">Ha aumentado el tamaño mínimo de la generación de claves RSAOpenSsl</span><span class="sxs-lookup"><span data-stu-id="6f032-111">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="6f032-112">3.0</span><span class="sxs-lookup"><span data-stu-id="6f032-112">3.0</span></span> |
| [<span data-ttu-id="6f032-113">.NET Core 3.0 prefiere OpenSSL 1.1.x a OpenSSL 1.0.x</span><span class="sxs-lookup"><span data-stu-id="6f032-113">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="6f032-114">3.0</span><span class="sxs-lookup"><span data-stu-id="6f032-114">3.0</span></span> |
| [<span data-ttu-id="6f032-115">Transformación del bloque final solo durante el proceso de escritura mediante CryptoStream.Dispose</span><span class="sxs-lookup"><span data-stu-id="6f032-115">CryptoStream.Dispose transforms final block only when writing</span></span>](#cryptostreamdispose-transforms-final-block-only-when-writing) | <span data-ttu-id="6f032-116">3.0</span><span class="sxs-lookup"><span data-stu-id="6f032-116">3.0</span></span> |
| [<span data-ttu-id="6f032-117">Se respeta el parámetro booleano de SignedCms.ComputeSignature</span><span class="sxs-lookup"><span data-stu-id="6f032-117">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="6f032-118">2.1</span><span class="sxs-lookup"><span data-stu-id="6f032-118">2.1</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="6f032-119">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6f032-119">.NET Core 3.0</span></span>

[!INCLUDE [begin-trusted-cert-linux](~/includes/core-changes/cryptography/3.0/begin-trusted-cert-linux.md)]

***

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

<span data-ttu-id="6f032-120">\*\*_</span><span class="sxs-lookup"><span data-stu-id="6f032-120">\*\*_</span></span>

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

_*_

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

_*_

[!INCLUDE [CryptoStream.Dispose transforms final block only when writing](~/includes/core-changes/cryptography/3.0/cryptography-cryptostream-dispose-final-block-write.md)]

_*_

## <a name="net-core-21"></a><span data-ttu-id="6f032-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="6f032-121">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

<span data-ttu-id="6f032-122">_\*\*</span><span class="sxs-lookup"><span data-stu-id="6f032-122">_\*\*</span></span>
