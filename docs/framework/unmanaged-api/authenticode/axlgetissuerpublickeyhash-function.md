---
description: 'Más información acerca de: _AxlGetIssuerPublicKeyHash función'
title: _AxlGetIssuerPublicKeyHash (Función)
ms.date: 03/30/2017
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
topic_type:
- apiref
ms.openlocfilehash: 586a072b33376a2fdade119fe3db0f48addfa3f5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747366"
---
# <a name="_axlgetissuerpublickeyhash-function"></a><span data-ttu-id="9104f-103">\_AxlGetIssuerPublicKeyHash función)</span><span class="sxs-lookup"><span data-stu-id="9104f-103">\_AxlGetIssuerPublicKeyHash Function</span></span>

<span data-ttu-id="9104f-104">Recupera el hash SHA-1 de la clave pública asociada con la clave privada que se usa para firmar el certificado especificado.</span><span class="sxs-lookup"><span data-stu-id="9104f-104">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>

## <a name="syntax"></a><span data-ttu-id="9104f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9104f-105">Syntax</span></span>

```cpp
HRESULT _AxlGetIssuerPublicKeyHash (
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,
    [out] LPWSTR                *ppwszPublicKeyHash
);
```

## <a name="parameters"></a><span data-ttu-id="9104f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9104f-106">Parameters</span></span>

 `pChainContext`\
 <span data-ttu-id="9104f-107">[in] Blob de clave pública CSP.</span><span class="sxs-lookup"><span data-stu-id="9104f-107">[in] The CSP public key blob.</span></span> <span data-ttu-id="9104f-108">Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="9104f-108">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>

 `ppwszPublicKeyHash`\
 <span data-ttu-id="9104f-109">[out] Puntero a WCHAR \* para recibir el token de clave pública de codificación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="9104f-109">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>

## <a name="return-value"></a><span data-ttu-id="9104f-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9104f-110">Return Value</span></span>

 <span data-ttu-id="9104f-111">`S_OK` si la función se realiza correctamente; de lo contrario es `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="9104f-111">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>

## <a name="requirements"></a><span data-ttu-id="9104f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9104f-112">Requirements</span></span>

<span data-ttu-id="9104f-113">**Ensamblado**: clr.dll</span><span class="sxs-lookup"><span data-stu-id="9104f-113">**Assembly**: clr.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="9104f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9104f-114">See also</span></span>

- [<span data-ttu-id="9104f-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="9104f-115">Authenticode</span></span>](index.md)
