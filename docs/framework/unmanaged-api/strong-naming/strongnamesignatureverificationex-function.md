---
title: StrongNameSignatureVerificationEx (Función)
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9887a05236b213fb439e334cdf1455f8f445e7e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671933"
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="9a3a0-102">StrongNameSignatureVerificationEx (Función)</span><span class="sxs-lookup"><span data-stu-id="9a3a0-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="9a3a0-103">Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="9a3a0-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="9a3a0-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="9a3a0-104">This function has been deprecated.</span></span> <span data-ttu-id="9a3a0-105">Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="9a3a0-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a3a0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a3a0-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a3a0-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9a3a0-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="9a3a0-108">[in] La ruta de acceso al archivo ejecutable portable (.dll o .exe) del ensamblado que debe comprobarse.</span><span class="sxs-lookup"><span data-stu-id="9a3a0-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="9a3a0-109">[in] `true` para realizar la comprobación, incluso si es necesario reemplazar la configuración del registro; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="9a3a0-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="9a3a0-110">[out] `true` si la firma de nombre seguro se ha comprobado; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="9a3a0-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="9a3a0-111">`pfWasVerified` También se establece en `false` si la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="9a3a0-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a3a0-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9a3a0-112">Return Value</span></span>  
 <span data-ttu-id="9a3a0-113">`true` Si la comprobación se realizó correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="9a3a0-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a3a0-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9a3a0-114">Remarks</span></span>  
 <span data-ttu-id="9a3a0-115">`StrongNameSignatureVerificationEx` Proporciona una funcionalidad similar a la [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="9a3a0-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="9a3a0-116">Sin embargo, el segundo parámetro de entrada y el parámetro de salida para `StrongNameSignatureVerificationEx` son del tipo `BOOLEAN` en lugar de `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="9a3a0-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a3a0-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a3a0-117">Requirements</span></span>  
 <span data-ttu-id="9a3a0-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a3a0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a3a0-119">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="9a3a0-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9a3a0-120">**Biblioteca:** Incluye como recurso en mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9a3a0-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="9a3a0-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a3a0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a3a0-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a3a0-122">See also</span></span>
- [<span data-ttu-id="9a3a0-123">StrongNameSignatureVerificationEx (método)</span><span class="sxs-lookup"><span data-stu-id="9a3a0-123">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="9a3a0-124">StrongNameSignatureVerification (método)</span><span class="sxs-lookup"><span data-stu-id="9a3a0-124">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="9a3a0-125">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a3a0-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
