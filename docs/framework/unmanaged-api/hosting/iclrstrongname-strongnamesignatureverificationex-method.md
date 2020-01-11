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
ms.openlocfilehash: fbc9ea6aab9f0c3d9be95e6affcd04342ce4c5cc
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901071"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="2462e-102">ICLRStrongName::StrongNameSignatureVerificationEx (Método)</span><span class="sxs-lookup"><span data-stu-id="2462e-102">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>
<span data-ttu-id="2462e-103">Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="2462e-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2462e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2462e-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2462e-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="2462e-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="2462e-106">de Ruta de acceso al archivo portable ejecutable (. exe o. dll) del ensamblado que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="2462e-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="2462e-107">[in] `true` para realizar la comprobación, incluso si es necesario invalidar la configuración del registro; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="2462e-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="2462e-108">[out] `true` si se ha comprobado la firma de nombre seguro; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="2462e-108">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="2462e-109">`pfWasVerified` también se establece en `false` si la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="2462e-109">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2462e-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2462e-110">Return Value</span></span>  
 <span data-ttu-id="2462e-111">`S_OK` si la comprobación se realizó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="2462e-111">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2462e-112">Notas</span><span class="sxs-lookup"><span data-stu-id="2462e-112">Remarks</span></span>  
 <span data-ttu-id="2462e-113">El método [ICLRStrongName:: strongnamesignatureverificationex (](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) proporciona una funcionalidad similar a la del método [ICLRStrongName:: strongnamesignatureverification (](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2462e-113">The [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="2462e-114">Sin embargo, el segundo parámetro de entrada y el parámetro de salida para [ICLRStrongName:: strongnamesignatureverificationex (](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) son de tipo `BOOLEAN` en lugar de `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="2462e-114">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2462e-115">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="2462e-115">Requirements</span></span>  
 <span data-ttu-id="2462e-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2462e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2462e-117">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="2462e-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2462e-118">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2462e-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2462e-119">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2462e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2462e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="2462e-120">See also</span></span>

- [<span data-ttu-id="2462e-121">StrongNameSignatureVerification (método)</span><span class="sxs-lookup"><span data-stu-id="2462e-121">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="2462e-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2462e-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
