---
title: CertVerifyAuthenticodeLicense (Función)
ms.date: 03/30/2017
api_name:
- CertVerifyAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 00118de7-33c6-41c4-8e1f-5d5e35e0da83
ms.openlocfilehash: 388814d1c63f048c0aa231a1d0058a390cba9493
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674065"
---
# <a name="certverifyauthenticodelicense-function"></a><span data-ttu-id="3b2b1-102">CertVerifyAuthenticodeLicense (Función)</span><span class="sxs-lookup"><span data-stu-id="3b2b1-102">CertVerifyAuthenticodeLicense Function</span></span>

<span data-ttu-id="3b2b1-103">Comprueba la validez de una licencia Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="3b2b1-103">Verifies the validity of an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b2b1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b2b1-104">Syntax</span></span>  
  
```cpp  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b2b1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b2b1-105">Parameters</span></span>  

 `pLicenseBlob`  
 <span data-ttu-id="3b2b1-106">[in] Licencia Authenticode XrML que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="3b2b1-106">[in] The Authenticode XrML license to be verified.</span></span>  
  
 <span data-ttu-id="3b2b1-107">Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="3b2b1-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3b2b1-108">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="3b2b1-108">[in] Optional.</span></span> <span data-ttu-id="3b2b1-109">Una combinación de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="3b2b1-109">A combination of following values:</span></span>  
  
- <span data-ttu-id="3b2b1-110">AXL_REVOCATION_NO_CHECK</span><span class="sxs-lookup"><span data-stu-id="3b2b1-110">AXL_REVOCATION_NO_CHECK</span></span>  
  
- <span data-ttu-id="3b2b1-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span><span class="sxs-lookup"><span data-stu-id="3b2b1-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span></span>  
  
- <span data-ttu-id="3b2b1-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span><span class="sxs-lookup"><span data-stu-id="3b2b1-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span></span>  
  
- <span data-ttu-id="3b2b1-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span><span class="sxs-lookup"><span data-stu-id="3b2b1-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span></span>  
  
- <span data-ttu-id="3b2b1-114">AXL_LIFETIME_SIGNING</span><span class="sxs-lookup"><span data-stu-id="3b2b1-114">AXL_LIFETIME_SIGNING</span></span>  
  
- <span data-ttu-id="3b2b1-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span><span class="sxs-lookup"><span data-stu-id="3b2b1-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span></span>  
  
 `pSignerInfo`  
 <span data-ttu-id="3b2b1-116">[out] Para recibir la información del firmante.</span><span class="sxs-lookup"><span data-stu-id="3b2b1-116">[out] To receive the signer's information.</span></span> <span data-ttu-id="3b2b1-117">Si la licencia no estaba firmada, `dwError` se establece en TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="3b2b1-117">If the license wasn't signed, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="3b2b1-118">Es responsabilidad del autor de la llamada liberar recursos mediante la función [certfreeauthenticodesignerinfo (](certfreeauthenticodesignerinfo-function.md) después del uso.</span><span class="sxs-lookup"><span data-stu-id="3b2b1-118">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeSignerInfo](certfreeauthenticodesignerinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="3b2b1-119">Vea [estructura de AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="3b2b1-119">See [AXL_AUTHENTICODE_SIGNER_INFO Structure](axl-authenticode-signer-info-structure.md).</span></span>  
  
 `pTimestamperInfo`  
 <span data-ttu-id="3b2b1-120">[out] Para recibir la información del autor de la marca de hora, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="3b2b1-120">[out] To receive time stamper's information, if available.</span></span> <span data-ttu-id="3b2b1-121">Si la licencia no tenía marca de hora, `dwError` se establece en TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="3b2b1-121">If the license was not time-stamped, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="3b2b1-122">Es responsabilidad del autor de la llamada liberar recursos mediante la función [certfreeauthenticodetimestamperinfo (](certfreeauthenticodetimestamperinfo-function.md) después del uso.</span><span class="sxs-lookup"><span data-stu-id="3b2b1-122">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeTimestamperInfo](certfreeauthenticodetimestamperinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="3b2b1-123">Vea [estructura de AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="3b2b1-123">See [AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure](axl-authenticode-timestamper-info-structure.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b2b1-124">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3b2b1-124">Return Value</span></span>  

 <span data-ttu-id="3b2b1-125">Si la operación se realiza correctamente, devuelve `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="3b2b1-125">Returns `S_OK` if successful.</span></span> <span data-ttu-id="3b2b1-126">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="3b2b1-126">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b2b1-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b2b1-127">See also</span></span>

- [<span data-ttu-id="3b2b1-128">Authenticode</span><span class="sxs-lookup"><span data-stu-id="3b2b1-128">Authenticode</span></span>](index.md)
- [<span data-ttu-id="3b2b1-129">Método GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="3b2b1-129">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="3b2b1-130">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b2b1-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
