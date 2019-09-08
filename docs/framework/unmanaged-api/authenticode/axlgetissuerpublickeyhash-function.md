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
ms.openlocfilehash: 4b101a912eb58ed14f81d847ea2fd6ce9f22c065
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787092"
---
# <a name="_axlgetissuerpublickeyhash-function"></a><span data-ttu-id="548b6-102">\_AxlGetIssuerPublicKeyHash función)</span><span class="sxs-lookup"><span data-stu-id="548b6-102">\_AxlGetIssuerPublicKeyHash Function</span></span>
<span data-ttu-id="548b6-103">Recupera el hash SHA-1 de la clave pública asociada con la clave privada que se usa para firmar el certificado especificado.</span><span class="sxs-lookup"><span data-stu-id="548b6-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="548b6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="548b6-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="548b6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="548b6-105">Parameters</span></span>  
 `pChainContext`  
 <span data-ttu-id="548b6-106">[in] Blob de clave pública CSP.</span><span class="sxs-lookup"><span data-stu-id="548b6-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="548b6-107">Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="548b6-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="548b6-108">[out] Puntero a WCHAR \* para recibir el token de clave pública de codificación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="548b6-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="548b6-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="548b6-109">Return Value</span></span>  
 <span data-ttu-id="548b6-110">`S_OK` si la función se realiza correctamente; de lo contrario es `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="548b6-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="548b6-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="548b6-111">See also</span></span>

- [<span data-ttu-id="548b6-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="548b6-112">Authenticode</span></span>](index.md)
