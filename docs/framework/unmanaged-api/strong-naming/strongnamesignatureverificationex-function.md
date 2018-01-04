---
title: "StrongNameSignatureVerificationEx (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureVerificationEx
helpviewer_keywords: StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8d00c2f03968e69423da31a336d275c46291d8da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="b9839-102">StrongNameSignatureVerificationEx (Función)</span><span class="sxs-lookup"><span data-stu-id="b9839-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="b9839-103">Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="b9839-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="b9839-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="b9839-104">This function has been deprecated.</span></span> <span data-ttu-id="b9839-105">Use la [ICLRStrongName:: StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="b9839-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9839-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9839-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9839-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b9839-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="b9839-108">[in] La ruta de acceso al archivo ejecutable portable (.dll o .exe) del ensamblado que debe comprobarse.</span><span class="sxs-lookup"><span data-stu-id="b9839-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="b9839-109">[in] `true` para realizar la comprobación, incluso si es necesario reemplazar la configuración del registro; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b9839-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="b9839-110">[out] `true` si la firma de nombre seguro se ha comprobado; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b9839-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="b9839-111">`pfWasVerified`También se establece en `false` si la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="b9839-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9839-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b9839-112">Return Value</span></span>  
 <span data-ttu-id="b9839-113">`true`Si la comprobación se realizó correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b9839-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9839-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b9839-114">Remarks</span></span>  
 <span data-ttu-id="b9839-115">`StrongNameSignatureVerificationEx`Proporciona una funcionalidad similar a la [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="b9839-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="b9839-116">Sin embargo, el segundo parámetro de entrada y el parámetro de salida para `StrongNameSignatureVerificationEx` son de tipo `BOOLEAN` en lugar de `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="b9839-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9839-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9839-117">Requirements</span></span>  
 <span data-ttu-id="b9839-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9839-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9839-119">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="b9839-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b9839-120">**Biblioteca:** incluye como recurso en mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b9839-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="b9839-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9839-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9839-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9839-122">See Also</span></span>  
 [<span data-ttu-id="b9839-123">StrongNameSignatureVerificationEx (método)</span><span class="sxs-lookup"><span data-stu-id="b9839-123">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="b9839-124">StrongNameSignatureVerification (método)</span><span class="sxs-lookup"><span data-stu-id="b9839-124">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="b9839-125">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9839-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
