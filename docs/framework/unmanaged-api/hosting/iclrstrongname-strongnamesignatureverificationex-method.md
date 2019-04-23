---
title: ICLRStrongName::StrongNameSignatureVerificationEx (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureVerificationEx method [.NET Framework hosting]
ms.assetid: dbd2f662-208b-4174-b301-5c99af91040f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b36e1d34b874f47f1edb0e1ffe3dc2fe2d87ddcc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124298"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="a94b0-102">ICLRStrongName::StrongNameSignatureVerificationEx (Método)</span><span class="sxs-lookup"><span data-stu-id="a94b0-102">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>
<span data-ttu-id="a94b0-103">Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="a94b0-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a94b0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a94b0-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a94b0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a94b0-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="a94b0-106">[in] La ruta de acceso al archivo ejecutable portable (.dll o .exe) del ensamblado que debe comprobarse.</span><span class="sxs-lookup"><span data-stu-id="a94b0-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="a94b0-107">[in] `true` para realizar la comprobación, incluso si es necesario reemplazar la configuración del registro; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a94b0-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="a94b0-108">[out] `true` si la firma de nombre seguro se ha comprobado; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a94b0-108">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="a94b0-109">`pfWasVerified` También se establece en `false` si la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="a94b0-109">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a94b0-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a94b0-110">Return Value</span></span>  
 <span data-ttu-id="a94b0-111">`S_OK` Si la comprobación se realizó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="a94b0-111">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a94b0-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a94b0-112">Remarks</span></span>  
 <span data-ttu-id="a94b0-113">El [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) método proporciona una funcionalidad similar a la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="a94b0-113">The [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="a94b0-114">Sin embargo, el segundo parámetro de entrada y el parámetro de salida para [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) son del tipo `BOOLEAN` en lugar de `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="a94b0-114">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a94b0-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a94b0-115">Requirements</span></span>  
 <span data-ttu-id="a94b0-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a94b0-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a94b0-117">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a94b0-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a94b0-118">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a94b0-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a94b0-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a94b0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a94b0-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a94b0-120">See also</span></span>

- [<span data-ttu-id="a94b0-121">StrongNameSignatureVerification (método)</span><span class="sxs-lookup"><span data-stu-id="a94b0-121">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="a94b0-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a94b0-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
