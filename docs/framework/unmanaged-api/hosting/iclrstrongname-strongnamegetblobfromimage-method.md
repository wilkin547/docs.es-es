---
title: "ICLRStrongName::StrongNameGetBlobFromImage (Método)"
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
- ICLRStrongName.StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetBlobFromImage method [.NET Framework hosting]
ms.assetid: 0f5a2ec8-e776-4fd8-bda6-937b6834575a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ff2ec30068903397d9f8d736f4f270c8d3c1669f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a><span data-ttu-id="932ed-102">ICLRStrongName::StrongNameGetBlobFromImage (Método)</span><span class="sxs-lookup"><span data-stu-id="932ed-102">ICLRStrongName::StrongNameGetBlobFromImage Method</span></span>
<span data-ttu-id="932ed-103">Obtiene una representación binaria de la imagen de ensamblado en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="932ed-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="932ed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="932ed-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="932ed-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="932ed-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="932ed-106">[in] La dirección de memoria del manifiesto del ensamblado asignado.</span><span class="sxs-lookup"><span data-stu-id="932ed-106">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="932ed-107">[in] El tamaño, en bytes, de la imagen en `pbBase`.</span><span class="sxs-lookup"><span data-stu-id="932ed-107">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="932ed-108">[in] Un búfer que contiene la representación binaria de la imagen.</span><span class="sxs-lookup"><span data-stu-id="932ed-108">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="932ed-109">[entrada, salida] El solicita el tamaño máximo, en bytes, de `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="932ed-109">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="932ed-110">Al volver, el tamaño real, en bytes, de `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="932ed-110">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="932ed-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="932ed-111">Return Value</span></span>  
 <span data-ttu-id="932ed-112">`S_OK`Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (vea [valores HRESULT comunes](http://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="932ed-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="932ed-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="932ed-113">Requirements</span></span>  
 <span data-ttu-id="932ed-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="932ed-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="932ed-115">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="932ed-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="932ed-116">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="932ed-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="932ed-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="932ed-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="932ed-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="932ed-118">See Also</span></span>  
 [<span data-ttu-id="932ed-119">StrongNameGetBlob (método)</span><span class="sxs-lookup"><span data-stu-id="932ed-119">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [<span data-ttu-id="932ed-120">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="932ed-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
