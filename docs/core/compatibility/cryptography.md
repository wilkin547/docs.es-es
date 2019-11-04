---
title: Cambios importantes de criptografía - .NET Core
description: Enumera los cambios importantes relacionados con la criptografía en .NET Core.
ms.date: 09/20/2019
ms.openlocfilehash: ce6739c57df801ef6ae3ab35e31bba6ad4055caa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73093093"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="d71a2-103">Cambios importantes de criptografía</span><span class="sxs-lookup"><span data-stu-id="d71a2-103">Cryptography breaking changes</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d71a2-104">Este artículo está en construcción.</span><span class="sxs-lookup"><span data-stu-id="d71a2-104">This article is under construction.</span></span> <span data-ttu-id="d71a2-105">Esta no es una lista completa de todos los cambios importantes en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d71a2-105">This is not a complete list of .NET Core breaking changes.</span></span> <span data-ttu-id="d71a2-106">Para obtener más información sobre los cambios importantes en .NET Core, puede consultar las [propuestas de cambios importantes](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) individuales en el repositorio dotnet/docs de GitHub.</span><span class="sxs-lookup"><span data-stu-id="d71a2-106">For more information on .NET Core breaking changes, you can examine individual [breaking changes issues](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) in the dotnet/docs repository on GitHub.</span></span> 

<span data-ttu-id="d71a2-107">A continuación, se muestra una lista de cambios importantes relacionados con la criptografía según la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d71a2-107">The following is a list of cryptography-related breaking changes by .NET Core version.</span></span>

## <a name="net-core-30-preview-9"></a><span data-ttu-id="d71a2-108">.NET Core 3.0 (versión preliminar 9)</span><span class="sxs-lookup"><span data-stu-id="d71a2-108">.NET Core 3.0 Preview 9</span></span>

[!INCLUDE[Better argument validation in the Pkcs8PrivateKeyInfo constructor](~/includes/core-changes/cryptography/better-argument-validation-in-pkcs8privatekeyinfo-ctor.md)]

## <a name="net-core-30"></a><span data-ttu-id="d71a2-109">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d71a2-109">.NET Core 3.0</span></span>

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/net-core-3-0-prefers-openssl-1-1-x.md)]
