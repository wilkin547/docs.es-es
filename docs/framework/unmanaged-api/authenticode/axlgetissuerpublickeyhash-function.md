---
title: "_AxlGetIssuerPublicKeyHash (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _AxlGetIssuerPublicKeyHash
api_location: clr.dll
api_type: DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 38be1f621425797e27fc41cb3192a628ebbfdb0c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="axlgetissuerpublickeyhash-function"></a><span data-ttu-id="c2272-102">_AxlGetIssuerPublicKeyHash (Función)</span><span class="sxs-lookup"><span data-stu-id="c2272-102">_AxlGetIssuerPublicKeyHash Function</span></span>
<span data-ttu-id="c2272-103">Recupera el hash SHA-1 de la clave pública asociada con la clave privada que se usa para firmar el certificado especificado.</span><span class="sxs-lookup"><span data-stu-id="c2272-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2272-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2272-104">Syntax</span></span>  
  
```  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2272-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c2272-105">Parameters</span></span>  
 `pChainContext`  
 <span data-ttu-id="c2272-106">[in] Blob de clave pública CSP.</span><span class="sxs-lookup"><span data-stu-id="c2272-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="c2272-107">Consulte la [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) estructura.</span><span class="sxs-lookup"><span data-stu-id="c2272-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="c2272-108">[out] Puntero a WCHAR * para recibir el token de clave pública de codificación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="c2272-108">[out] A pointer to WCHAR * to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2272-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c2272-109">Return Value</span></span>  
 <span data-ttu-id="c2272-110">`S_OK` si la función se realiza correctamente; de lo contrario es `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="c2272-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2272-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2272-111">See Also</span></span>  
 [<span data-ttu-id="c2272-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="c2272-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
