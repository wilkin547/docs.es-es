---
title: ICorDebugManagedCallback::UnloadModule (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02ca9ed57e62d2c066de2d7c1a1e4b57094dbc0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413360"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="7528e-102">ICorDebugManagedCallback::UnloadModule (Método)</span><span class="sxs-lookup"><span data-stu-id="7528e-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="7528e-103">Notifica al depurador que un módulo de common language runtime (DLL) se ha descargado.</span><span class="sxs-lookup"><span data-stu-id="7528e-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7528e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7528e-104">Syntax</span></span>  
  
```  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7528e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7528e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="7528e-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contenía el módulo.</span><span class="sxs-lookup"><span data-stu-id="7528e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="7528e-107">[in] Un puntero a un objeto ICorDebugModule que representa el módulo.</span><span class="sxs-lookup"><span data-stu-id="7528e-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7528e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7528e-108">Remarks</span></span>  
 <span data-ttu-id="7528e-109">El módulo no debe utilizarse después de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="7528e-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7528e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7528e-110">Requirements</span></span>  
 <span data-ttu-id="7528e-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7528e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7528e-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7528e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7528e-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7528e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7528e-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7528e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7528e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7528e-115">See Also</span></span>  
 [<span data-ttu-id="7528e-116">LoadModule (método)</span><span class="sxs-lookup"><span data-stu-id="7528e-116">LoadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)  
 [<span data-ttu-id="7528e-117">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7528e-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
