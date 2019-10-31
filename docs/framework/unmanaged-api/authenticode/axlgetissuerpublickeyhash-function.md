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
ms.openlocfilehash: 6d5ad995b55a3cde6363b297df6b8faf72689468
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132486"
---
# <a name="_axlgetissuerpublickeyhash-function"></a><span data-ttu-id="f29d8-102">\_función AxlGetIssuerPublicKeyHash</span><span class="sxs-lookup"><span data-stu-id="f29d8-102">\_AxlGetIssuerPublicKeyHash Function</span></span>
<span data-ttu-id="f29d8-103">Recupera el hash SHA-1 de la clave pública asociada con la clave privada que se usa para firmar el certificado especificado.</span><span class="sxs-lookup"><span data-stu-id="f29d8-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f29d8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f29d8-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f29d8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f29d8-105">Parameters</span></span>  
 `pChainContext`  
 <span data-ttu-id="f29d8-106">[in] Blob de clave pública CSP.</span><span class="sxs-lookup"><span data-stu-id="f29d8-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="f29d8-107">Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="f29d8-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="f29d8-108">[out] Puntero a WCHAR \* para recibir el token de clave pública de codificación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="f29d8-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f29d8-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f29d8-109">Return Value</span></span>  
 <span data-ttu-id="f29d8-110">`S_OK` si la función se realiza correctamente; de lo contrario es `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="f29d8-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f29d8-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f29d8-111">See also</span></span>

- [<span data-ttu-id="f29d8-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="f29d8-112">Authenticode</span></span>](index.md)
