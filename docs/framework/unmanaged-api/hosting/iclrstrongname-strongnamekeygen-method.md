---
title: "ICLRStrongName::StrongNameKeyGen (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameKeyGen
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3b434783d7537c5f6a3127183f66d4b0b3f77534
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="68ad2-102">ICLRStrongName::StrongNameKeyGen (Método)</span><span class="sxs-lookup"><span data-stu-id="68ad2-102">ICLRStrongName::StrongNameKeyGen Method</span></span>
<span data-ttu-id="68ad2-103">Crea un nuevo par de claves pública y privada para su uso de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="68ad2-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68ad2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68ad2-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="68ad2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="68ad2-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="68ad2-106">[in] El nombre de contenedor de claves solicitado.</span><span class="sxs-lookup"><span data-stu-id="68ad2-106">[in] The requested key container name.</span></span> <span data-ttu-id="68ad2-107">`wszKeyContainer`debe ser una cadena no vacía o null para generar un nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="68ad2-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="68ad2-108">[in] Un valor que especifica si se debe abandonar la clave registrada.</span><span class="sxs-lookup"><span data-stu-id="68ad2-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="68ad2-109">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="68ad2-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="68ad2-110">0 x 00000000: se usa cuando `wszKeyContainer` es null para generar un nombre de contenedor de claves temporal.</span><span class="sxs-lookup"><span data-stu-id="68ad2-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="68ad2-111">0 x 00000001 (`SN_LEAVE_KEY`)-especifica que la clave debería quedar registrada.</span><span class="sxs-lookup"><span data-stu-id="68ad2-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="68ad2-112">[out] El par de claves pública y privada devuelto.</span><span class="sxs-lookup"><span data-stu-id="68ad2-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="68ad2-113">[out] El tamaño, en bytes, de `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="68ad2-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68ad2-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="68ad2-114">Return Value</span></span>  
 <span data-ttu-id="68ad2-115">`S_OK`Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (vea [valores HRESULT comunes](http://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="68ad2-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68ad2-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="68ad2-116">Remarks</span></span>  
 <span data-ttu-id="68ad2-117">El [ICLRStrongName:: StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) método crea una clave de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="68ad2-117">The [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="68ad2-118">Una vez recuperada la clave, debe llamar a la [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) método para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="68ad2-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68ad2-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="68ad2-119">Requirements</span></span>  
 <span data-ttu-id="68ad2-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68ad2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68ad2-121">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="68ad2-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="68ad2-122">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="68ad2-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68ad2-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68ad2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68ad2-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="68ad2-124">See Also</span></span>  
 [<span data-ttu-id="68ad2-125">StrongNameKeyGenEx (método)</span><span class="sxs-lookup"><span data-stu-id="68ad2-125">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)  
 [<span data-ttu-id="68ad2-126">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="68ad2-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
