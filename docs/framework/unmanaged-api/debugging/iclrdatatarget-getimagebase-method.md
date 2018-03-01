---
title: "ICLRDataTarget::GetImageBase (Método)"
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
- ICLRDataTarget.GetImageBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 504c3ce7115cbab11d0510eaa2ebb0fdd9f1888b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="3fdfb-102">ICLRDataTarget::GetImageBase (Método)</span><span class="sxs-lookup"><span data-stu-id="3fdfb-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="3fdfb-103">Obtiene la dirección de memoria de base de la imagen especificada.</span><span class="sxs-lookup"><span data-stu-id="3fdfb-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fdfb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3fdfb-104">Syntax</span></span>  
  
```  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3fdfb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3fdfb-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="3fdfb-106">[in] El nombre de archivo de la imagen, incluida su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="3fdfb-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="3fdfb-107">[out] Un puntero a CLRDATA_ADDRESS que almacena la dirección base de la imagen.</span><span class="sxs-lookup"><span data-stu-id="3fdfb-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fdfb-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3fdfb-108">Remarks</span></span>  
 <span data-ttu-id="3fdfb-109">El nombre de archivo de imagen puede tener o no una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="3fdfb-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="3fdfb-110">Si se especifica una ruta de acceso, se realiza la coincidencia en la ruta de acceso completa; en caso contrario, la coincidencia se realiza únicamente en el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="3fdfb-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fdfb-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3fdfb-111">Requirements</span></span>  
 <span data-ttu-id="3fdfb-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fdfb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fdfb-113">**Encabezado:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="3fdfb-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="3fdfb-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fdfb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fdfb-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fdfb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fdfb-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3fdfb-116">See Also</span></span>  
 [<span data-ttu-id="3fdfb-117">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3fdfb-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
