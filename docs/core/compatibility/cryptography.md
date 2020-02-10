---
title: Cambios importantes de criptografía
description: Enumera los cambios importantes relacionados con la criptografía en .NET Core.
ms.date: 09/20/2019
ms.openlocfilehash: fcef4b65245a5dd9219cbdbb548ca575a823a949
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093037"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="67e75-103">Cambios importantes de criptografía</span><span class="sxs-lookup"><span data-stu-id="67e75-103">Cryptography breaking changes</span></span>

<span data-ttu-id="67e75-104">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="67e75-104">The following breaking changes are documented on this page:</span></span>

- [<span data-ttu-id="67e75-105">EnvelopedCms usa de forma predeterminada el cifrado AES-256</span><span class="sxs-lookup"><span data-stu-id="67e75-105">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption)
- [<span data-ttu-id="67e75-106">Ha aumentado el tamaño mínimo de la generación de claves RSAOpenSsl</span><span class="sxs-lookup"><span data-stu-id="67e75-106">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased)
- [<span data-ttu-id="67e75-107">.NET Core 3.0 prefiere OpenSSL 1.1.x a OpenSSL 1.0.x</span><span class="sxs-lookup"><span data-stu-id="67e75-107">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x)
- [<span data-ttu-id="67e75-108">Mejor validación de argumentos en el constructor de Pkcs8PrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="67e75-108">Better argument validation in the Pkcs8PrivateKeyInfo constructor</span></span>](#better-argument-validation-in-the-pkcs8privatekeyinfo-constructor)

## <a name="net-core-30"></a><span data-ttu-id="67e75-109">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="67e75-109">.NET Core 3.0</span></span>

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

***

## <a name="net-core-30-preview-9"></a><span data-ttu-id="67e75-110">.NET Core 3.0 (versión preliminar 9)</span><span class="sxs-lookup"><span data-stu-id="67e75-110">.NET Core 3.0 Preview 9</span></span>

[!INCLUDE[Better argument validation in the Pkcs8PrivateKeyInfo constructor](~/includes/core-changes/cryptography/3.0/better-argument-validation-in-pkcs8privatekeyinfo-ctor.md)]

***
