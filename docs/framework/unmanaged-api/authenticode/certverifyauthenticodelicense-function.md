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
ms.openlocfilehash: 7cd25a24533b04dc45ee734f9e9639391311405a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099743"
---
# <a name="certverifyauthenticodelicense-function"></a><span data-ttu-id="aa724-102">CertVerifyAuthenticodeLicense (Función)</span><span class="sxs-lookup"><span data-stu-id="aa724-102">CertVerifyAuthenticodeLicense Function</span></span>
<span data-ttu-id="aa724-103">Comprueba la validez de una licencia Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="aa724-103">Verifies the validity of an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa724-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa724-104">Syntax</span></span>  
  
```cpp  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa724-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aa724-105">Parameters</span></span>  
 `pLicenseBlob`  
 <span data-ttu-id="aa724-106">[in] Licencia Authenticode XrML que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="aa724-106">[in] The Authenticode XrML license to be verified.</span></span>  
  
 <span data-ttu-id="aa724-107">Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="aa724-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="aa724-108">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="aa724-108">[in] Optional.</span></span> <span data-ttu-id="aa724-109">Una combinación de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="aa724-109">A combination of following values:</span></span>  
  
- <span data-ttu-id="aa724-110">AXL_REVOCATION_NO_CHECK</span><span class="sxs-lookup"><span data-stu-id="aa724-110">AXL_REVOCATION_NO_CHECK</span></span>  
  
- <span data-ttu-id="aa724-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span><span class="sxs-lookup"><span data-stu-id="aa724-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span></span>  
  
- <span data-ttu-id="aa724-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span><span class="sxs-lookup"><span data-stu-id="aa724-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span></span>  
  
- <span data-ttu-id="aa724-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span><span class="sxs-lookup"><span data-stu-id="aa724-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span></span>  
  
- <span data-ttu-id="aa724-114">AXL_LIFETIME_SIGNING</span><span class="sxs-lookup"><span data-stu-id="aa724-114">AXL_LIFETIME_SIGNING</span></span>  
  
- <span data-ttu-id="aa724-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span><span class="sxs-lookup"><span data-stu-id="aa724-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span></span>  
  
 `pSignerInfo`  
 <span data-ttu-id="aa724-116">[out] Para recibir la información del firmante.</span><span class="sxs-lookup"><span data-stu-id="aa724-116">[out] To receive the signer's information.</span></span> <span data-ttu-id="aa724-117">Si la licencia no estaba firmada, `dwError` se establece en TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="aa724-117">If the license wasn't signed, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="aa724-118">Es responsabilidad del autor de la llamada liberar recursos mediante la función [certfreeauthenticodesignerinfo (](certfreeauthenticodesignerinfo-function.md) después del uso.</span><span class="sxs-lookup"><span data-stu-id="aa724-118">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeSignerInfo](certfreeauthenticodesignerinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="aa724-119">Vea [estructura AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="aa724-119">See [AXL_AUTHENTICODE_SIGNER_INFO Structure](axl-authenticode-signer-info-structure.md).</span></span>  
  
 `pTimestamperInfo`  
 <span data-ttu-id="aa724-120">[out] Para recibir la información del autor de la marca de hora, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="aa724-120">[out] To receive time stamper's information, if available.</span></span> <span data-ttu-id="aa724-121">Si la licencia no tenía marca de hora, `dwError` se establece en TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="aa724-121">If the license was not time-stamped, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="aa724-122">Es responsabilidad del autor de la llamada liberar recursos mediante la función [certfreeauthenticodetimestamperinfo (](certfreeauthenticodetimestamperinfo-function.md) después del uso.</span><span class="sxs-lookup"><span data-stu-id="aa724-122">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeTimestamperInfo](certfreeauthenticodetimestamperinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="aa724-123">Vea [estructura AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="aa724-123">See [AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure](axl-authenticode-timestamper-info-structure.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa724-124">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="aa724-124">Return Value</span></span>  
 <span data-ttu-id="aa724-125">Si la operación se realiza correctamente, devuelve `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="aa724-125">Returns `S_OK` if successful.</span></span> <span data-ttu-id="aa724-126">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="aa724-126">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa724-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa724-127">See also</span></span>

- [<span data-ttu-id="aa724-128">Authenticode</span><span class="sxs-lookup"><span data-stu-id="aa724-128">Authenticode</span></span>](index.md)
- [<span data-ttu-id="aa724-129">GetHashFromHandle (método)</span><span class="sxs-lookup"><span data-stu-id="aa724-129">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="aa724-130">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa724-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
