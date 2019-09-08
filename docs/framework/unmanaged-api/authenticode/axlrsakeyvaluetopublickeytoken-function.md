---
title: _AxlRSAKeyValueToPublicKeyToken función)
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 690035ffe0724d3987a198c78bf14e668527b98a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787018"
---
# <a name="_axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="2da95-102">\_AxlRSAKeyValueToPublicKeyToken función)</span><span class="sxs-lookup"><span data-stu-id="2da95-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="2da95-103">Convierte un blob Modulus y Exponent en un token de clave pública de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="2da95-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2da95-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2da95-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2da95-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2da95-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="2da95-106">de El BLOB de módulo con codificación base64 (del elemento de \<módulo >).</span><span class="sxs-lookup"><span data-stu-id="2da95-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="2da95-107">Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="2da95-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="2da95-108">de El BLOB de exponente con codificación base64 (del \<exponente > elemento).</span><span class="sxs-lookup"><span data-stu-id="2da95-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="2da95-109">Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="2da95-109">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="2da95-110">[out] Puntero a WCHAR \* para recibir el token de clave pública de codificación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="2da95-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2da95-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2da95-111">Return Value</span></span>  
 <span data-ttu-id="2da95-112">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="2da95-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="2da95-113">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="2da95-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2da95-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2da95-114">See also</span></span>

- [<span data-ttu-id="2da95-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="2da95-115">Authenticode</span></span>](index.md)
