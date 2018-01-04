---
title: "ICorDebugManagedCallback::UnloadModule (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.UnloadModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7aeb3f12d5217c57d8d8f1f5665840a4515c0998
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="85acd-102">ICorDebugManagedCallback::UnloadModule (Método)</span><span class="sxs-lookup"><span data-stu-id="85acd-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="85acd-103">Notifica al depurador que un módulo de common language runtime (DLL) se ha descargado.</span><span class="sxs-lookup"><span data-stu-id="85acd-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85acd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85acd-104">Syntax</span></span>  
  
```  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85acd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="85acd-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="85acd-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contenía el módulo.</span><span class="sxs-lookup"><span data-stu-id="85acd-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="85acd-107">[in] Un puntero a un objeto ICorDebugModule que representa el módulo.</span><span class="sxs-lookup"><span data-stu-id="85acd-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85acd-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="85acd-108">Remarks</span></span>  
 <span data-ttu-id="85acd-109">El módulo no debe utilizarse después de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="85acd-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85acd-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85acd-110">Requirements</span></span>  
 <span data-ttu-id="85acd-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85acd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85acd-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85acd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85acd-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85acd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85acd-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85acd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85acd-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="85acd-115">See Also</span></span>  
 [<span data-ttu-id="85acd-116">LoadModule (método)</span><span class="sxs-lookup"><span data-stu-id="85acd-116">LoadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)  
 [<span data-ttu-id="85acd-117">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="85acd-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
