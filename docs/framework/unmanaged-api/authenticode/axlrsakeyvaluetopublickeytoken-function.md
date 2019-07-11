---
title: _AxlRSAKeyValueToPublicKeyToken (función)
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
ms.openlocfilehash: 4f9981c4cf2e45795576024b797f93831324dbc9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741265"
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="e9f69-102">\_Función AxlRSAKeyValueToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="e9f69-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="e9f69-103">Convierte un blob Modulus y Exponent en un token de clave pública de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="e9f69-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9f69-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9f69-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9f69-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9f69-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="e9f69-106">[in] El blob Modulus con codificación base64 (desde el \<Modulus > elemento).</span><span class="sxs-lookup"><span data-stu-id="e9f69-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="e9f69-107">Consulte la [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) estructura.</span><span class="sxs-lookup"><span data-stu-id="e9f69-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="e9f69-108">[in] El blob Exponent con codificación base64 (desde el \<exponente > elemento).</span><span class="sxs-lookup"><span data-stu-id="e9f69-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="e9f69-109">Consulte la [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) estructura.</span><span class="sxs-lookup"><span data-stu-id="e9f69-109">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="e9f69-110">[out] Puntero a WCHAR \* para recibir el token de clave pública de codificación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="e9f69-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9f69-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e9f69-111">Return Value</span></span>  
 <span data-ttu-id="e9f69-112">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="e9f69-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="e9f69-113">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="e9f69-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9f69-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9f69-114">See also</span></span>

- [<span data-ttu-id="e9f69-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="e9f69-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
