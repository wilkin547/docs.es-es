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
ms.openlocfilehash: d79a8c5bc204b6479741c32c47e6b41ff873a1bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406928"
---
# <a name="certverifyauthenticodelicense-function"></a><span data-ttu-id="fec63-102">CertVerifyAuthenticodeLicense (Función)</span><span class="sxs-lookup"><span data-stu-id="fec63-102">CertVerifyAuthenticodeLicense Function</span></span>
<span data-ttu-id="fec63-103">Comprueba la validez de una licencia Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="fec63-103">Verifies the validity of an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fec63-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fec63-104">Syntax</span></span>  
  
```  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fec63-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fec63-105">Parameters</span></span>  
 `pLicenseBlob`  
 <span data-ttu-id="fec63-106">[in] Licencia Authenticode XrML que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="fec63-106">[in] The Authenticode XrML license to be verified.</span></span>  
  
 <span data-ttu-id="fec63-107">Consulte la [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) estructura.</span><span class="sxs-lookup"><span data-stu-id="fec63-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="fec63-108">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="fec63-108">[in] Optional.</span></span> <span data-ttu-id="fec63-109">Una combinación de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="fec63-109">A combination of following values:</span></span>  
  
-   <span data-ttu-id="fec63-110">AXL_REVOCATION_NO_CHECK</span><span class="sxs-lookup"><span data-stu-id="fec63-110">AXL_REVOCATION_NO_CHECK</span></span>  
  
-   <span data-ttu-id="fec63-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span><span class="sxs-lookup"><span data-stu-id="fec63-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span></span>  
  
-   <span data-ttu-id="fec63-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span><span class="sxs-lookup"><span data-stu-id="fec63-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span></span>  
  
-   <span data-ttu-id="fec63-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span><span class="sxs-lookup"><span data-stu-id="fec63-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span></span>  
  
-   <span data-ttu-id="fec63-114">AXL_LIFETIME_SIGNING</span><span class="sxs-lookup"><span data-stu-id="fec63-114">AXL_LIFETIME_SIGNING</span></span>  
  
-   <span data-ttu-id="fec63-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span><span class="sxs-lookup"><span data-stu-id="fec63-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span></span>  
  
 `pSignerInfo`  
 <span data-ttu-id="fec63-116">[out] Para recibir la información del firmante.</span><span class="sxs-lookup"><span data-stu-id="fec63-116">[out] To receive the signer's information.</span></span> <span data-ttu-id="fec63-117">Si la licencia no estaba firmada, `dwError` se establece en TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="fec63-117">If the license wasn't signed, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="fec63-118">Es responsabilidad del llamante liberar recursos usando la [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) función tras su uso.</span><span class="sxs-lookup"><span data-stu-id="fec63-118">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="fec63-119">Vea [AXL_AUTHENTICODE_SIGNER_INFO (estructura)](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="fec63-119">See [AXL_AUTHENTICODE_SIGNER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span></span>  
  
 `pTimestamperInfo`  
 <span data-ttu-id="fec63-120">[out] Para recibir la información del autor de la marca de hora, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="fec63-120">[out] To receive time stamper's information, if available.</span></span> <span data-ttu-id="fec63-121">Si la licencia no tenía marca de hora, `dwError` se establece en TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="fec63-121">If the license was not time-stamped, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="fec63-122">Es responsabilidad del llamante liberar recursos usando la [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) función tras su uso.</span><span class="sxs-lookup"><span data-stu-id="fec63-122">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="fec63-123">Vea [AXL_AUTHENTICODE_TIMESTAMPER_INFO (estructura)](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="fec63-123">See [AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fec63-124">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fec63-124">Return Value</span></span>  
 <span data-ttu-id="fec63-125">Si la operación se realiza correctamente, devuelve `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="fec63-125">Returns `S_OK` if successful.</span></span> <span data-ttu-id="fec63-126">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="fec63-126">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fec63-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="fec63-127">See Also</span></span>  
 [<span data-ttu-id="fec63-128">Authenticode</span><span class="sxs-lookup"><span data-stu-id="fec63-128">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)  
 [<span data-ttu-id="fec63-129">GetHashFromHandle (método)</span><span class="sxs-lookup"><span data-stu-id="fec63-129">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)  
 [<span data-ttu-id="fec63-130">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fec63-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
