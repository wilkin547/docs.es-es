---
title: StrongNameSignatureVerification (Función)
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerification
helpviewer_keywords:
- StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de267042eab8d0f3d8dc2562c13bcdd068837220
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559481"
---
# <a name="strongnamesignatureverification-function"></a><span data-ttu-id="cd409-102">StrongNameSignatureVerification (Función)</span><span class="sxs-lookup"><span data-stu-id="cd409-102">StrongNameSignatureVerification Function</span></span>
<span data-ttu-id="cd409-103">Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro, que se comprueba según las marcas indicadas.</span><span class="sxs-lookup"><span data-stu-id="cd409-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
 <span data-ttu-id="cd409-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="cd409-104">This function has been deprecated.</span></span> <span data-ttu-id="cd409-105">Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="cd409-105">Use the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd409-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd409-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd409-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cd409-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="cd409-108">[in] La ruta de acceso al archivo ejecutable portable (.dll o .exe) del ensamblado comprobar.</span><span class="sxs-lookup"><span data-stu-id="cd409-108">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="cd409-109">[in] Marcas para modificar el comportamiento de comprobación.</span><span class="sxs-lookup"><span data-stu-id="cd409-109">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="cd409-110">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="cd409-110">The following values are supported:</span></span>  
  
-   <span data-ttu-id="cd409-111">`SN_INFLAG_FORCE_VER` (0 x 00000001) - fuerza la comprobación incluso si es necesario invalidar la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="cd409-111">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="cd409-112">`SN_INFLAG_INSTALL` (0 x 00000002): Especifica que se trata de la primera vez que se comprueba el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="cd409-112">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   <span data-ttu-id="cd409-113">`SN_INFLAG_ADMIN_ACCESS` (0 x 00000004): Especifica que la memoria caché permitirá el acceso únicamente a los usuarios que tienen privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="cd409-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="cd409-114">`SN_INFLAG_USER_ACCESS` (0 x 00000008): Especifica que el ensamblado será accesible solo para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="cd409-114">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="cd409-115">`SN_INFLAG_ALL_ACCESS` (0 x 00000010): Especifica que la memoria caché no proporcionará ninguna garantía de restricción de acceso.</span><span class="sxs-lookup"><span data-stu-id="cd409-115">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="cd409-116">`SN_INFLAG_RUNTIME` (0 x 80000000): reservado para la depuración interna.</span><span class="sxs-lookup"><span data-stu-id="cd409-116">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="cd409-117">[out] Marcas que indican si se ha comprobado la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="cd409-117">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="cd409-118">Se admite el siguiente valor:</span><span class="sxs-lookup"><span data-stu-id="cd409-118">The following value is supported:</span></span>  
  
-   <span data-ttu-id="cd409-119">`SN_OUTFLAG_WAS_VERIFIED` (0 x 00000001): este valor se establece en `false` para especificar que la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="cd409-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd409-120">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cd409-120">Return Value</span></span>  
 <span data-ttu-id="cd409-121">`true` Si la comprobación se realizó correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="cd409-121">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd409-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd409-122">Requirements</span></span>  
 <span data-ttu-id="cd409-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd409-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd409-124">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="cd409-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="cd409-125">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cd409-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cd409-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd409-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd409-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd409-127">See also</span></span>
- [<span data-ttu-id="cd409-128">StrongNameSignatureVerification (método)</span><span class="sxs-lookup"><span data-stu-id="cd409-128">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="cd409-129">StrongNameSignatureVerificationEx (método)</span><span class="sxs-lookup"><span data-stu-id="cd409-129">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="cd409-130">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd409-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
