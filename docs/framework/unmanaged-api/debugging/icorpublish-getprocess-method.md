---
title: "ICorPublish::GetProcess (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublish.GetProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e613b9101e842a584eef4bcbac1bf3de1dba5cd3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="6d2df-102">ICorPublish::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="6d2df-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="6d2df-103">Obtiene un [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instancia que representa el proceso con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="6d2df-103">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d2df-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d2df-104">Syntax</span></span>  
  
```  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d2df-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6d2df-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="6d2df-106">[in] El identificador del proceso.</span><span class="sxs-lookup"><span data-stu-id="6d2df-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="6d2df-107">[out] Un puntero a la dirección de un `ICorPublishProcess` instancia que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="6d2df-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d2df-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6d2df-108">Remarks</span></span>  
 <span data-ttu-id="6d2df-109">`GetProcess`se produce un error si el proceso no existe o no es un proceso administrado que puede ser depurado por el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="6d2df-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d2df-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d2df-110">Requirements</span></span>  
 <span data-ttu-id="6d2df-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d2df-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d2df-112">**Encabezado:** Cordebug.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="6d2df-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6d2df-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d2df-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d2df-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d2df-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d2df-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d2df-115">See Also</span></span>  
 [<span data-ttu-id="6d2df-116">ICorPublish (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d2df-116">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
