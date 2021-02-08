---
description: 'Más información sobre: ICLRStrongName:: Strongnamesignatureverificationex ((método)'
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
ms.openlocfilehash: 0e1692d7151e09a621b93823424b3ac10b6607d7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789767"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="99b1d-103">ICLRStrongName::StrongNameSignatureVerificationEx (Método)</span><span class="sxs-lookup"><span data-stu-id="99b1d-103">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>

<span data-ttu-id="99b1d-104">Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="99b1d-104">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99b1d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99b1d-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99b1d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="99b1d-106">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="99b1d-107">de Ruta de acceso al archivo portable ejecutable (. exe o. dll) del ensamblado que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="99b1d-107">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="99b1d-108">[in] `true` para realizar la comprobación, incluso si es necesario invalidar la configuración del registro; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="99b1d-108">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="99b1d-109">[out] `true` Si se ha comprobado la firma de nombre seguro; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="99b1d-109">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="99b1d-110">`pfWasVerified` también se establece en `false` si la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="99b1d-110">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99b1d-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="99b1d-111">Return Value</span></span>  

 <span data-ttu-id="99b1d-112">`S_OK` Si la comprobación se realizó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="99b1d-112">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99b1d-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="99b1d-113">Remarks</span></span>  

 <span data-ttu-id="99b1d-114">El método [ICLRStrongName:: strongnamesignatureverificationex (](iclrstrongname-strongnamesignatureverificationex-method.md) proporciona una funcionalidad similar a la del método [ICLRStrongName:: strongnamesignatureverification (](iclrstrongname-strongnamesignatureverification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="99b1d-114">The [ICLRStrongName::StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="99b1d-115">Sin embargo, el segundo parámetro de entrada y el parámetro de salida de [ICLRStrongName:: strongnamesignatureverificationex (](iclrstrongname-strongnamesignatureverificationex-method.md) son de tipo `BOOLEAN` en lugar de `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="99b1d-115">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99b1d-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99b1d-116">Requirements</span></span>  

 <span data-ttu-id="99b1d-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99b1d-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99b1d-118">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="99b1d-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="99b1d-119">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="99b1d-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99b1d-120">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99b1d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99b1d-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="99b1d-121">See also</span></span>

- [<span data-ttu-id="99b1d-122">Método StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="99b1d-122">StrongNameSignatureVerification Method</span></span>](iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="99b1d-123">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="99b1d-123">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
