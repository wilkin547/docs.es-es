---
title: _AxlRSAKeyValueToPublicKeyToken (Función)
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
ms.openlocfilehash: 7ef73f0f7599fdff887437756a5995591fd8ec89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402418"
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="ef250-102">_AxlRSAKeyValueToPublicKeyToken (Función)</span><span class="sxs-lookup"><span data-stu-id="ef250-102">_AxlRSAKeyValueToPublicKeyToken Function</span></span>
<span data-ttu-id="ef250-103">Convierte un blob Modulus y Exponent en un token de clave pública de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="ef250-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef250-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef250-104">Syntax</span></span>  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef250-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef250-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="ef250-106">[in] El blob Modulus con codificación base64 (desde el \<Modulus > elemento).</span><span class="sxs-lookup"><span data-stu-id="ef250-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="ef250-107">Consulte la [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) estructura.</span><span class="sxs-lookup"><span data-stu-id="ef250-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="ef250-108">[in] El blob Exponent con codificación base64 (desde el \<exponente > elemento).</span><span class="sxs-lookup"><span data-stu-id="ef250-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="ef250-109">Consulte la [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) estructura.</span><span class="sxs-lookup"><span data-stu-id="ef250-109">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="ef250-110">[out] Puntero a WCHAR \* para recibir el token de clave pública de codificación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="ef250-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef250-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ef250-111">Return Value</span></span>  
 <span data-ttu-id="ef250-112">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="ef250-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="ef250-113">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="ef250-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef250-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef250-114">See Also</span></span>  
 [<span data-ttu-id="ef250-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="ef250-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
