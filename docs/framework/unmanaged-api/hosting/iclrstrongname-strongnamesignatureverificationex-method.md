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
ms.openlocfilehash: 3e4181cbd14674336133314acdcd6cdcf0c9ff6b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134928"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="bf36a-102">ICLRStrongName::StrongNameSignatureVerificationEx (Método)</span><span class="sxs-lookup"><span data-stu-id="bf36a-102">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>
<span data-ttu-id="bf36a-103">Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="bf36a-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf36a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf36a-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf36a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bf36a-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="bf36a-106">de Ruta de acceso al archivo portable ejecutable (. exe o. dll) del ensamblado que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="bf36a-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="bf36a-107">[in] `true` para realizar la comprobación, incluso si es necesario invalidar la configuración del registro; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="bf36a-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="bf36a-108">[out] `true` si se ha comprobado la firma de nombre seguro; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="bf36a-108">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="bf36a-109">`pfWasVerified` también se establece en `false` si la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="bf36a-109">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf36a-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bf36a-110">Return Value</span></span>  
 <span data-ttu-id="bf36a-111">`S_OK` si la comprobación se realizó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para una lista).</span><span class="sxs-lookup"><span data-stu-id="bf36a-111">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf36a-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf36a-112">Remarks</span></span>  
 <span data-ttu-id="bf36a-113">El método [ICLRStrongName:: strongnamesignatureverificationex (](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) proporciona una funcionalidad similar a la del método [ICLRStrongName:: strongnamesignatureverification (](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bf36a-113">The [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="bf36a-114">Sin embargo, el segundo parámetro de entrada y el parámetro de salida para [ICLRStrongName:: strongnamesignatureverificationex (](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) son de tipo `BOOLEAN` en lugar de `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="bf36a-114">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf36a-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf36a-115">Requirements</span></span>  
 <span data-ttu-id="bf36a-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf36a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf36a-117">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="bf36a-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bf36a-118">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bf36a-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bf36a-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf36a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf36a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf36a-120">See also</span></span>

- [<span data-ttu-id="bf36a-121">StrongNameSignatureVerification (método)</span><span class="sxs-lookup"><span data-stu-id="bf36a-121">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="bf36a-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf36a-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
