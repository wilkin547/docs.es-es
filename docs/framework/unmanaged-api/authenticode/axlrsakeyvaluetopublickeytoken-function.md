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
ms.openlocfilehash: e09391af9b5d71cfa423b3bf1a2b307117d0dee1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517603"
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="09272-102">\_Función AxlRSAKeyValueToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="09272-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="09272-103">Convierte un blob Modulus y Exponent en un token de clave pública de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="09272-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09272-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09272-104">Syntax</span></span>  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
### <a name="parameters"></a><span data-ttu-id="09272-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="09272-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="09272-106">[in] El blob Modulus con codificación base64 (desde el \<Modulus > elemento).</span><span class="sxs-lookup"><span data-stu-id="09272-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="09272-107">Consulte la [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) estructura.</span><span class="sxs-lookup"><span data-stu-id="09272-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="09272-108">[in] El blob Exponent con codificación base64 (desde el \<exponente > elemento).</span><span class="sxs-lookup"><span data-stu-id="09272-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="09272-109">Consulte la [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) estructura.</span><span class="sxs-lookup"><span data-stu-id="09272-109">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="09272-110">[out] Puntero a WCHAR \* para recibir el token de clave pública de codificación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="09272-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09272-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="09272-111">Return Value</span></span>  
 <span data-ttu-id="09272-112">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="09272-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="09272-113">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="09272-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09272-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="09272-114">See Also</span></span>  
 [<span data-ttu-id="09272-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="09272-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
