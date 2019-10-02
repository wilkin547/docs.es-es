---
title: Cambios importantes de criptografía - .NET Core
description: Enumera los cambios importantes relacionados con la criptografía en .NET Core.
ms.date: 09/20/2019
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80b62f9b32487e88a309ea7686f78d68af8f2e0a
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216988"
---
# <a name="cryptography-breaking-changes"></a>Cambios importantes de criptografía

> [!IMPORTANT]
> Este artículo está en construcción. Esta no es una lista completa de todos los cambios importantes en .NET Core. Para obtener más información sobre los cambios importantes en .NET Core, puede consultar las [propuestas de cambios importantes](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) individuales en el repositorio dotnet/docs de GitHub. 

A continuación, se muestra una lista de cambios importantes relacionados con la criptografía según la versión de .NET Core.

## <a name="net-core-30-preview-9"></a>.NET Core 3.0 (versión preliminar 9)

[!INCLUDE[Better argument validation in the Pkcs8PrivateKeyInfo constructor](~/includes/core-changes/cryptography/better-argument-validation-in-pkcs8privatekeyinfo-ctor.md)]

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/net-core-3-0-prefers-openssl-1-1-x.md)]
