---
title: _AxlPublicKeyBlobToPublicKeyToken (Función)
ms.date: 03/30/2017
api_name:
- _AxlPublicKeyBlobToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56333165d179abd79e82f1416342a2700029eb12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401679"
---
# <a name="axlpublickeyblobtopublickeytoken-function"></a><span data-ttu-id="e5360-102">_AxlPublicKeyBlobToPublicKeyToken (Función)</span><span class="sxs-lookup"><span data-stu-id="e5360-102">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>
<span data-ttu-id="e5360-103">Calcula el token de clave pública del nombre seguro a partir de un formato CSP PUBLICKEYBLOB.</span><span class="sxs-lookup"><span data-stu-id="e5360-103">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5360-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5360-104">Syntax</span></span>  
  
```  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5360-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5360-105">Parameters</span></span>  
 `pCspPublicKeyBlob`  
 <span data-ttu-id="e5360-106">[in] Blob de clave pública CSP.</span><span class="sxs-lookup"><span data-stu-id="e5360-106">[in] The CSP public key blob.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="e5360-107">[out] Puntero a WCHAR \* para recibir el hash de clave pública de codificación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="e5360-107">[out] A pointer to WCHAR \* to receive the hex-encoded public key hash.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5360-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e5360-108">Return Value</span></span>  
 <span data-ttu-id="e5360-109">`S_OK` si la función se realiza correctamente; de lo contrario es `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="e5360-109">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5360-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5360-110">See Also</span></span>  
 [<span data-ttu-id="e5360-111">Authenticode</span><span class="sxs-lookup"><span data-stu-id="e5360-111">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
