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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: abbf893b3d49101b5cc9d38ffc31b171ff023f8a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146931"
---
# <a name="certverifyauthenticodelicense-function"></a><span data-ttu-id="326cb-102">CertVerifyAuthenticodeLicense (Función)</span><span class="sxs-lookup"><span data-stu-id="326cb-102">CertVerifyAuthenticodeLicense Function</span></span>
<span data-ttu-id="326cb-103">Comprueba la validez de una licencia Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="326cb-103">Verifies the validity of an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="326cb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="326cb-104">Syntax</span></span>  
  
```  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="326cb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="326cb-105">Parameters</span></span>  
 `pLicenseBlob`  
 <span data-ttu-id="326cb-106">[in] Licencia Authenticode XrML que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="326cb-106">[in] The Authenticode XrML license to be verified.</span></span>  
  
 <span data-ttu-id="326cb-107">Consulte la [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) estructura.</span><span class="sxs-lookup"><span data-stu-id="326cb-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="326cb-108">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="326cb-108">[in] Optional.</span></span> <span data-ttu-id="326cb-109">Una combinación de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="326cb-109">A combination of following values:</span></span>  
  
-   <span data-ttu-id="326cb-110">AXL_REVOCATION_NO_CHECK</span><span class="sxs-lookup"><span data-stu-id="326cb-110">AXL_REVOCATION_NO_CHECK</span></span>  
  
-   <span data-ttu-id="326cb-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span><span class="sxs-lookup"><span data-stu-id="326cb-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span></span>  
  
-   <span data-ttu-id="326cb-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span><span class="sxs-lookup"><span data-stu-id="326cb-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span></span>  
  
-   <span data-ttu-id="326cb-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span><span class="sxs-lookup"><span data-stu-id="326cb-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span></span>  
  
-   <span data-ttu-id="326cb-114">AXL_LIFETIME_SIGNING</span><span class="sxs-lookup"><span data-stu-id="326cb-114">AXL_LIFETIME_SIGNING</span></span>  
  
-   <span data-ttu-id="326cb-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span><span class="sxs-lookup"><span data-stu-id="326cb-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span></span>  
  
 `pSignerInfo`  
 <span data-ttu-id="326cb-116">[out] Para recibir la información del firmante.</span><span class="sxs-lookup"><span data-stu-id="326cb-116">[out] To receive the signer's information.</span></span> <span data-ttu-id="326cb-117">Si la licencia no estaba firmada, `dwError` se establece en TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="326cb-117">If the license wasn't signed, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="326cb-118">Es responsabilidad del llamante liberar recursos usando el [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) función tras su uso.</span><span class="sxs-lookup"><span data-stu-id="326cb-118">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="326cb-119">Consulte [AXL_AUTHENTICODE_SIGNER_INFO (estructura)](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="326cb-119">See [AXL_AUTHENTICODE_SIGNER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span></span>  
  
 `pTimestamperInfo`  
 <span data-ttu-id="326cb-120">[out] Para recibir la información del autor de la marca de hora, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="326cb-120">[out] To receive time stamper's information, if available.</span></span> <span data-ttu-id="326cb-121">Si la licencia no tenía marca de hora, `dwError` se establece en TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="326cb-121">If the license was not time-stamped, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="326cb-122">Es responsabilidad del llamante liberar recursos usando el [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) función tras su uso.</span><span class="sxs-lookup"><span data-stu-id="326cb-122">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="326cb-123">Consulte [AXL_AUTHENTICODE_TIMESTAMPER_INFO (estructura)](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="326cb-123">See [AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="326cb-124">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="326cb-124">Return Value</span></span>  
 <span data-ttu-id="326cb-125">Si la operación se realiza correctamente, devuelve `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="326cb-125">Returns `S_OK` if successful.</span></span> <span data-ttu-id="326cb-126">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="326cb-126">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="326cb-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="326cb-127">See also</span></span>

- [<span data-ttu-id="326cb-128">Authenticode</span><span class="sxs-lookup"><span data-stu-id="326cb-128">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
- [<span data-ttu-id="326cb-129">Método GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="326cb-129">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="326cb-130">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="326cb-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
