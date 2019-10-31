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
ms.openlocfilehash: 33b8f47813a3bf43bd69741c9febb150fa3a92e3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099906"
---
# <a name="_axlpublickeyblobtopublickeytoken-function"></a><span data-ttu-id="111c6-102">\_función AxlPublicKeyBlobToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="111c6-102">\_AxlPublicKeyBlobToPublicKeyToken Function</span></span>
<span data-ttu-id="111c6-103">Calcula el token de clave pública del nombre seguro a partir de un formato CSP PUBLICKEYBLOB.</span><span class="sxs-lookup"><span data-stu-id="111c6-103">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="111c6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="111c6-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="111c6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="111c6-105">Parameters</span></span>  
 `pCspPublicKeyBlob`  
 <span data-ttu-id="111c6-106">[in] Blob de clave pública CSP.</span><span class="sxs-lookup"><span data-stu-id="111c6-106">[in] The CSP public key blob.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="111c6-107">[out] Puntero a WCHAR \* para recibir el hash de clave pública de codificación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="111c6-107">[out] A pointer to WCHAR \* to receive the hex-encoded public key hash.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="111c6-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="111c6-108">Return Value</span></span>  
 <span data-ttu-id="111c6-109">`S_OK` si la función se realiza correctamente; de lo contrario es `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="111c6-109">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="111c6-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="111c6-110">See also</span></span>

- [<span data-ttu-id="111c6-111">Authenticode</span><span class="sxs-lookup"><span data-stu-id="111c6-111">Authenticode</span></span>](index.md)
