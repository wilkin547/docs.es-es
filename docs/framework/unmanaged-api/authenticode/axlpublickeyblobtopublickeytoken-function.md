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
ms.openlocfilehash: b4d720480e4c8b21b3aa56ce81634a26ac9c75de
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776673"
---
# <a name="_axlpublickeyblobtopublickeytoken-function"></a><span data-ttu-id="257c0-102">\_AxlPublicKeyBlobToPublicKeyToken función)</span><span class="sxs-lookup"><span data-stu-id="257c0-102">\_AxlPublicKeyBlobToPublicKeyToken Function</span></span>
<span data-ttu-id="257c0-103">Calcula el token de clave pública del nombre seguro a partir de un formato CSP PUBLICKEYBLOB.</span><span class="sxs-lookup"><span data-stu-id="257c0-103">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="257c0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="257c0-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="257c0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="257c0-105">Parameters</span></span>  
 `pCspPublicKeyBlob`  
 <span data-ttu-id="257c0-106">[in] Blob de clave pública CSP.</span><span class="sxs-lookup"><span data-stu-id="257c0-106">[in] The CSP public key blob.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="257c0-107">[out] Puntero a WCHAR \* para recibir el hash de clave pública de codificación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="257c0-107">[out] A pointer to WCHAR \* to receive the hex-encoded public key hash.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="257c0-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="257c0-108">Return Value</span></span>  
 <span data-ttu-id="257c0-109">`S_OK` si la función se realiza correctamente; de lo contrario es `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="257c0-109">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="257c0-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="257c0-110">See also</span></span>

- [<span data-ttu-id="257c0-111">Authenticode</span><span class="sxs-lookup"><span data-stu-id="257c0-111">Authenticode</span></span>](index.md)
