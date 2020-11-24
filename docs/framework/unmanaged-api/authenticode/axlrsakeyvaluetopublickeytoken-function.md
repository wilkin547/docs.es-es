---
title: _AxlRSAKeyValueToPublicKeyToken función)
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
ms.openlocfilehash: 5c1e2bfc7fd55e807af68744e28faa473daea772
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674221"
---
# <a name="_axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="56e87-102">\_AxlRSAKeyValueToPublicKeyToken función)</span><span class="sxs-lookup"><span data-stu-id="56e87-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="56e87-103">Convierte un blob Modulus y Exponent en un token de clave pública de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="56e87-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56e87-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56e87-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56e87-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="56e87-105">Parameters</span></span>  

 `pModulusBlob`  
 <span data-ttu-id="56e87-106">de El BLOB de módulo con codificación base64 (del \<Modulus> elemento).</span><span class="sxs-lookup"><span data-stu-id="56e87-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="56e87-107">Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="56e87-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="56e87-108">de El BLOB de exponente con codificación base64 (del \<Exponent> elemento).</span><span class="sxs-lookup"><span data-stu-id="56e87-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="56e87-109">Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="56e87-109">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="56e87-110">[out] Puntero a WCHAR \* para recibir el token de clave pública de codificación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="56e87-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56e87-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="56e87-111">Return Value</span></span>  

 <span data-ttu-id="56e87-112">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="56e87-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="56e87-113">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="56e87-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56e87-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="56e87-114">See also</span></span>

- [<span data-ttu-id="56e87-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="56e87-115">Authenticode</span></span>](index.md)
