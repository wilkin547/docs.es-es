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
ms.openlocfilehash: 49476a4417e5431842f8e2ba0371c53c5c9f03e9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207830"
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="c2a8d-102">\_Función AxlRSAKeyValueToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="c2a8d-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="c2a8d-103">Convierte un blob Modulus y Exponent en un token de clave pública de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="c2a8d-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2a8d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2a8d-104">Syntax</span></span>  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2a8d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c2a8d-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="c2a8d-106">[in] El blob Modulus con codificación base64 (desde el \<Modulus > elemento).</span><span class="sxs-lookup"><span data-stu-id="c2a8d-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="c2a8d-107">Consulte la [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) estructura.</span><span class="sxs-lookup"><span data-stu-id="c2a8d-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="c2a8d-108">[in] El blob Exponent con codificación base64 (desde el \<exponente > elemento).</span><span class="sxs-lookup"><span data-stu-id="c2a8d-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="c2a8d-109">Consulte la [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) estructura.</span><span class="sxs-lookup"><span data-stu-id="c2a8d-109">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="c2a8d-110">[out] Puntero a WCHAR \* para recibir el token de clave pública de codificación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="c2a8d-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2a8d-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c2a8d-111">Return Value</span></span>  
 <span data-ttu-id="c2a8d-112">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="c2a8d-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="c2a8d-113">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="c2a8d-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2a8d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2a8d-114">See also</span></span>

- [<span data-ttu-id="c2a8d-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="c2a8d-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
