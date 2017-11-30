---
title: "CertVerifyAuthenticodeLicense (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CertVerifyAuthenticodeLicense
api_location: clr.dll
api_type: DLLExport
ms.assetid: 00118de7-33c6-41c4-8e1f-5d5e35e0da83
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 16d8067b4cd5d0a7b3db5be5b3b9ed4d689e1b0e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="certverifyauthenticodelicense-function"></a><span data-ttu-id="b2097-102">CertVerifyAuthenticodeLicense (Función)</span><span class="sxs-lookup"><span data-stu-id="b2097-102">CertVerifyAuthenticodeLicense Function</span></span>
<span data-ttu-id="b2097-103">Comprueba la validez de una licencia Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="b2097-103">Verifies the validity of an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2097-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2097-104">Syntax</span></span>  
  
```  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b2097-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b2097-105">Parameters</span></span>  
 `pLicenseBlob`  
 <span data-ttu-id="b2097-106">[in] Licencia Authenticode XrML que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="b2097-106">[in] The Authenticode XrML license to be verified.</span></span>  
  
 <span data-ttu-id="b2097-107">Consulte la [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) estructura.</span><span class="sxs-lookup"><span data-stu-id="b2097-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b2097-108">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="b2097-108">[in] Optional.</span></span> <span data-ttu-id="b2097-109">Una combinación de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="b2097-109">A combination of following values:</span></span>  
  
-   <span data-ttu-id="b2097-110">AXL_REVOCATION_NO_CHECK</span><span class="sxs-lookup"><span data-stu-id="b2097-110">AXL_REVOCATION_NO_CHECK</span></span>  
  
-   <span data-ttu-id="b2097-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span><span class="sxs-lookup"><span data-stu-id="b2097-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span></span>  
  
-   <span data-ttu-id="b2097-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span><span class="sxs-lookup"><span data-stu-id="b2097-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span></span>  
  
-   <span data-ttu-id="b2097-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span><span class="sxs-lookup"><span data-stu-id="b2097-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span></span>  
  
-   <span data-ttu-id="b2097-114">AXL_LIFETIME_SIGNING</span><span class="sxs-lookup"><span data-stu-id="b2097-114">AXL_LIFETIME_SIGNING</span></span>  
  
-   <span data-ttu-id="b2097-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span><span class="sxs-lookup"><span data-stu-id="b2097-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span></span>  
  
 `pSignerInfo`  
 <span data-ttu-id="b2097-116">[out] Para recibir la información del firmante.</span><span class="sxs-lookup"><span data-stu-id="b2097-116">[out] To receive the signer's information.</span></span> <span data-ttu-id="b2097-117">Si la licencia no estaba firmada, `dwError` se establece en TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="b2097-117">If the license wasn't signed, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="b2097-118">Es responsabilidad del llamante liberar recursos usando la [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) función tras su uso.</span><span class="sxs-lookup"><span data-stu-id="b2097-118">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="b2097-119">Vea [AXL_AUTHENTICODE_SIGNER_INFO (estructura)](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="b2097-119">See [AXL_AUTHENTICODE_SIGNER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span></span>  
  
 `pTimestamperInfo`  
 <span data-ttu-id="b2097-120">[out] Para recibir la información del autor de la marca de hora, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="b2097-120">[out] To receive time stamper's information, if available.</span></span> <span data-ttu-id="b2097-121">Si la licencia no tenía marca de hora, `dwError` se establece en TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="b2097-121">If the license was not time-stamped, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="b2097-122">Es responsabilidad del llamante liberar recursos usando la [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) función tras su uso.</span><span class="sxs-lookup"><span data-stu-id="b2097-122">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="b2097-123">Vea [AXL_AUTHENTICODE_TIMESTAMPER_INFO (estructura)](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="b2097-123">See [AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2097-124">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b2097-124">Return Value</span></span>  
 <span data-ttu-id="b2097-125">Si la operación se realiza correctamente, devuelve `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="b2097-125">Returns `S_OK` if successful.</span></span> <span data-ttu-id="b2097-126">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="b2097-126">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2097-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2097-127">See Also</span></span>  
 [<span data-ttu-id="b2097-128">Authenticode</span><span class="sxs-lookup"><span data-stu-id="b2097-128">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)  
 [<span data-ttu-id="b2097-129">GetHashFromHandle (método)</span><span class="sxs-lookup"><span data-stu-id="b2097-129">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)  
 [<span data-ttu-id="b2097-130">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2097-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
