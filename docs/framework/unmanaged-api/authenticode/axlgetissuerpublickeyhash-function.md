---
title: _AxlGetIssuerPublicKeyHash (Función)
ms.date: 03/30/2017
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de55594db68e084009a095a083e065fbd0b8f0df
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741334"
---
# <a name="axlgetissuerpublickeyhash-function"></a><span data-ttu-id="1a621-102">\_Función AxlGetIssuerPublicKeyHash</span><span class="sxs-lookup"><span data-stu-id="1a621-102">\_AxlGetIssuerPublicKeyHash Function</span></span>
<span data-ttu-id="1a621-103">Recupera el hash SHA-1 de la clave pública asociada con la clave privada que se usa para firmar el certificado especificado.</span><span class="sxs-lookup"><span data-stu-id="1a621-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a621-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1a621-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a621-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1a621-105">Parameters</span></span>  
 `pChainContext`  
 <span data-ttu-id="1a621-106">[in] Blob de clave pública CSP.</span><span class="sxs-lookup"><span data-stu-id="1a621-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="1a621-107">Consulte la [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) estructura.</span><span class="sxs-lookup"><span data-stu-id="1a621-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="1a621-108">[out] Puntero a WCHAR \* para recibir el token de clave pública de codificación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="1a621-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a621-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1a621-109">Return Value</span></span>  
 <span data-ttu-id="1a621-110">`S_OK` si la función se realiza correctamente; de lo contrario es `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="1a621-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a621-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a621-111">See also</span></span>

- [<span data-ttu-id="1a621-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="1a621-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
