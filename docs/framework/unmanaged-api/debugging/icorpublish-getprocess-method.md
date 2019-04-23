---
title: ICorPublish::GetProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 021068caa8f1ad2c64e5ca3d18ea25dc827563a4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085009"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="369ee-102">ICorPublish::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="369ee-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="369ee-103">Obtiene un [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instancia que representa el proceso con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="369ee-103">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="369ee-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="369ee-104">Syntax</span></span>  
  
```  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="369ee-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="369ee-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="369ee-106">[in] El identificador del proceso.</span><span class="sxs-lookup"><span data-stu-id="369ee-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="369ee-107">[out] Un puntero a la dirección de un `ICorPublishProcess` instancia que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="369ee-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="369ee-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="369ee-108">Remarks</span></span>  
 <span data-ttu-id="369ee-109">`GetProcess` se produce un error si el proceso no existe o no es un proceso administrado que se puede depurar por el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="369ee-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="369ee-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="369ee-110">Requirements</span></span>  
 <span data-ttu-id="369ee-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="369ee-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="369ee-112">**Encabezado**: CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="369ee-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="369ee-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="369ee-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="369ee-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="369ee-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="369ee-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="369ee-115">See also</span></span>

- [<span data-ttu-id="369ee-116">ICorPublish (interfaz)</span><span class="sxs-lookup"><span data-stu-id="369ee-116">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
