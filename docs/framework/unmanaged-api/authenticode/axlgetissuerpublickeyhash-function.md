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
ms.openlocfilehash: 49674e43109108e41b135cecbec061ad61e14865
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679967"
---
# <a name="_axlgetissuerpublickeyhash-function"></a><span data-ttu-id="01211-102">\_AxlGetIssuerPublicKeyHash función)</span><span class="sxs-lookup"><span data-stu-id="01211-102">\_AxlGetIssuerPublicKeyHash Function</span></span>

<span data-ttu-id="01211-103">Recupera el hash SHA-1 de la clave pública asociada con la clave privada que se usa para firmar el certificado especificado.</span><span class="sxs-lookup"><span data-stu-id="01211-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01211-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="01211-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01211-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="01211-105">Parameters</span></span>  

 `pChainContext`  
 <span data-ttu-id="01211-106">[in] Blob de clave pública CSP.</span><span class="sxs-lookup"><span data-stu-id="01211-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="01211-107">Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="01211-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="01211-108">[out] Puntero a WCHAR \* para recibir el token de clave pública de codificación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="01211-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01211-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="01211-109">Return Value</span></span>  

 <span data-ttu-id="01211-110">`S_OK` si la función se realiza correctamente; de lo contrario es `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="01211-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01211-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01211-111">See also</span></span>

- [<span data-ttu-id="01211-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="01211-112">Authenticode</span></span>](index.md)
