---
title: "ICLRStrongName::StrongNameSignatureVerificationFromImage (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName.StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage method [.NET Framework hosting]
- StrongNameSignatureVerificationFromImage method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: da91c138-ee30-4fd4-a040-464d97d7e41a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 57c8422d59a07de9ad045f2043594cb8d01f2f74
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a><span data-ttu-id="841b7-102">ICLRStrongName::StrongNameSignatureVerificationFromImage (Método)</span><span class="sxs-lookup"><span data-stu-id="841b7-102">ICLRStrongName::StrongNameSignatureVerificationFromImage Method</span></span>
<span data-ttu-id="841b7-103">Comprueba que un ensamblado que ya se ha asignado a la memoria es válido para la clave pública asociada.</span><span class="sxs-lookup"><span data-stu-id="841b7-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="841b7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="841b7-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="841b7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="841b7-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="841b7-106">[in] La dirección virtual relativa del manifiesto del ensamblado asignado.</span><span class="sxs-lookup"><span data-stu-id="841b7-106">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="841b7-107">[in] El tamaño, en bytes, de la imagen asignada.</span><span class="sxs-lookup"><span data-stu-id="841b7-107">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="841b7-108">[in] Marcas que influyen en el comportamiento de la comprobación.</span><span class="sxs-lookup"><span data-stu-id="841b7-108">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="841b7-109">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="841b7-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="841b7-110">`SN_INFLAG_FORCE_VER`(0 x 00000001) - fuerza la comprobación aunque sea necesario invalidar la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="841b7-110">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="841b7-111">`SN_INFLAG_INSTALL`(0 x 00000002): Especifica que se trata de la primera comprobación que se realiza en esta imagen.</span><span class="sxs-lookup"><span data-stu-id="841b7-111">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
-   <span data-ttu-id="841b7-112">`SN_INFLAG_ADMIN_ACCESS`(0 x 00000004): Especifica que la memoria caché permitirá el acceso únicamente a los usuarios que tienen privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="841b7-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="841b7-113">`SN_INFLAG_USER_ACCESS`(0 x 00000008): Especifica que el ensamblado estará accesible sólo para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="841b7-113">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="841b7-114">`SN_INFLAG_ALL_ACCESS`(0 x 00000010): Especifica que la memoria caché no proporcionará ninguna garantía de restricción de acceso.</span><span class="sxs-lookup"><span data-stu-id="841b7-114">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="841b7-115">`SN_INFLAG_RUNTIME`(0 x 80000000) - reservado para la depuración interna.</span><span class="sxs-lookup"><span data-stu-id="841b7-115">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="841b7-116">[out] Una marca para obtener información de salida adicional.</span><span class="sxs-lookup"><span data-stu-id="841b7-116">[out] A flag for additional output information.</span></span> <span data-ttu-id="841b7-117">Se admite el siguiente valor:</span><span class="sxs-lookup"><span data-stu-id="841b7-117">The following value is supported:</span></span>  
  
-   <span data-ttu-id="841b7-118">`SN_OUTFLAG_WAS_VERIFIED`(0 x 00000001): este valor se establece en `false` para especificar que la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="841b7-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="841b7-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="841b7-119">Return Value</span></span>  
 <span data-ttu-id="841b7-120">`S_OK`Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (vea [valores HRESULT comunes](http://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="841b7-120">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="841b7-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="841b7-121">Requirements</span></span>  
 <span data-ttu-id="841b7-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="841b7-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="841b7-123">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="841b7-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="841b7-124">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="841b7-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="841b7-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="841b7-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="841b7-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="841b7-126">See Also</span></span>  
 [<span data-ttu-id="841b7-127">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="841b7-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
