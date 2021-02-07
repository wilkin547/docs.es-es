---
description: 'Más información acerca de: _AxlRSAKeyValueToPublicKeyToken función'
title: _AxlRSAKeyValueToPublicKeyToken función)
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
topic_type:
- apiref
ms.openlocfilehash: 01fc4cdc1d9985375748307ca2d7fff97191c908
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747275"
---
# <a name="_axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="18b2d-103">\_AxlRSAKeyValueToPublicKeyToken función)</span><span class="sxs-lookup"><span data-stu-id="18b2d-103">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="18b2d-104">Convierte un blob Modulus y Exponent en un token de clave pública de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="18b2d-104">Converts a Modulus and Exponent to a strong name public key token.</span></span>

## <a name="syntax"></a><span data-ttu-id="18b2d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18b2d-105">Syntax</span></span>

```cpp
HRESULT _AxlRSAKeyValueToPublicKeyToken (
    [in]  PCRYPT_DATA_BLOB pModulusBlob,
    [in]  PCRYPT_DATA_BLOB pExponentBlob,
    [out] LPWSTR           *ppwszPublicKeyToken
);
```

## <a name="parameters"></a><span data-ttu-id="18b2d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="18b2d-106">Parameters</span></span>

 `pModulusBlob`\
 <span data-ttu-id="18b2d-107">de El BLOB de módulo con codificación base64 (del \<Modulus> elemento).</span><span class="sxs-lookup"><span data-stu-id="18b2d-107">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="18b2d-108">Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="18b2d-108">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>

 `pExponentBlob`\
 <span data-ttu-id="18b2d-109">de El BLOB de exponente con codificación base64 (del \<Exponent> elemento).</span><span class="sxs-lookup"><span data-stu-id="18b2d-109">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="18b2d-110">Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="18b2d-110">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>

 `ppwszPublicKeyToken`\
 <span data-ttu-id="18b2d-111">[out] Puntero a WCHAR \* para recibir el token de clave pública de codificación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="18b2d-111">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>

## <a name="return-value"></a><span data-ttu-id="18b2d-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="18b2d-112">Return Value</span></span>

 <span data-ttu-id="18b2d-113">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="18b2d-113">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="18b2d-114">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="18b2d-114">Otherwise, returns an error code.</span></span>

## <a name="requirements"></a><span data-ttu-id="18b2d-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="18b2d-115">Requirements</span></span>

<span data-ttu-id="18b2d-116">**Ensamblado**: clr.dll</span><span class="sxs-lookup"><span data-stu-id="18b2d-116">**Assembly**: clr.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="18b2d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="18b2d-117">See also</span></span>

- [<span data-ttu-id="18b2d-118">Authenticode</span><span class="sxs-lookup"><span data-stu-id="18b2d-118">Authenticode</span></span>](index.md)
