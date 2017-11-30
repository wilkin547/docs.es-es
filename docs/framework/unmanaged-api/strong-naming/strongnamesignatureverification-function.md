---
title: "StrongNameSignatureVerification (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureVerification
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureVerification
helpviewer_keywords: StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a2c04aba5b774b299e26be8dc532b894b6c6fad5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignatureverification-function"></a><span data-ttu-id="8a5d4-102">StrongNameSignatureVerification (Función)</span><span class="sxs-lookup"><span data-stu-id="8a5d4-102">StrongNameSignatureVerification Function</span></span>
<span data-ttu-id="8a5d4-103">Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro, que se comprueba según los marcadores especificados.</span><span class="sxs-lookup"><span data-stu-id="8a5d4-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
 <span data-ttu-id="8a5d4-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="8a5d4-104">This function has been deprecated.</span></span> <span data-ttu-id="8a5d4-105">Use la [ICLRStrongName:: StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="8a5d4-105">Use the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a5d4-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a5d4-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a5d4-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8a5d4-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="8a5d4-108">[in] La ruta de acceso al archivo ejecutable portable (.dll o .exe) del ensamblado que debe comprobarse.</span><span class="sxs-lookup"><span data-stu-id="8a5d4-108">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="8a5d4-109">[in] Marcas para modificar el comportamiento de comprobación.</span><span class="sxs-lookup"><span data-stu-id="8a5d4-109">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="8a5d4-110">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="8a5d4-110">The following values are supported:</span></span>  
  
-   <span data-ttu-id="8a5d4-111">`SN_INFLAG_FORCE_VER`(0 x 00000001) - fuerza la comprobación aunque sea necesario invalidar la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="8a5d4-111">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="8a5d4-112">`SN_INFLAG_INSTALL`(0 x 00000002): Especifica que ésta es la primera vez que se comprueba el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="8a5d4-112">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   <span data-ttu-id="8a5d4-113">`SN_INFLAG_ADMIN_ACCESS`(0 x 00000004): Especifica que la memoria caché permitirá el acceso únicamente a los usuarios que tienen privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="8a5d4-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="8a5d4-114">`SN_INFLAG_USER_ACCESS`(0 x 00000008): Especifica que el ensamblado estará accesible sólo para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="8a5d4-114">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="8a5d4-115">`SN_INFLAG_ALL_ACCESS`(0 x 00000010): Especifica que la memoria caché no proporcionará ninguna garantía de restricción de acceso.</span><span class="sxs-lookup"><span data-stu-id="8a5d4-115">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="8a5d4-116">`SN_INFLAG_RUNTIME`(0 x 80000000) - reservado para la depuración interna.</span><span class="sxs-lookup"><span data-stu-id="8a5d4-116">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="8a5d4-117">[out] Marcas que indica si se ha comprobado la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="8a5d4-117">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="8a5d4-118">Se admite el siguiente valor:</span><span class="sxs-lookup"><span data-stu-id="8a5d4-118">The following value is supported:</span></span>  
  
-   <span data-ttu-id="8a5d4-119">`SN_OUTFLAG_WAS_VERIFIED`(0 x 00000001): este valor se establece en `false` para especificar que la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="8a5d4-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a5d4-120">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8a5d4-120">Return Value</span></span>  
 <span data-ttu-id="8a5d4-121">`true`Si la comprobación se realizó correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="8a5d4-121">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a5d4-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a5d4-122">Requirements</span></span>  
 <span data-ttu-id="8a5d4-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a5d4-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a5d4-124">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="8a5d4-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="8a5d4-125">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8a5d4-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8a5d4-126">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a5d4-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a5d4-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a5d4-127">See Also</span></span>  
 [<span data-ttu-id="8a5d4-128">StrongNameSignatureVerification (método)</span><span class="sxs-lookup"><span data-stu-id="8a5d4-128">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="8a5d4-129">StrongNameSignatureVerificationEx (método)</span><span class="sxs-lookup"><span data-stu-id="8a5d4-129">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="8a5d4-130">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a5d4-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
