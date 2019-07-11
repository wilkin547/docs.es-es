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
ms.openlocfilehash: 8826644ae3bdfbef76e9143de5f8f449c1555095
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761206"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="d3ff7-102">ICorDebugManagedCallback::UnloadModule (Método)</span><span class="sxs-lookup"><span data-stu-id="d3ff7-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="d3ff7-103">Notifica al depurador que se ha descargado un módulo de common language runtime (DLL).</span><span class="sxs-lookup"><span data-stu-id="d3ff7-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3ff7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3ff7-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3ff7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d3ff7-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="d3ff7-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el módulo.</span><span class="sxs-lookup"><span data-stu-id="d3ff7-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="d3ff7-107">[in] Un puntero a un objeto ICorDebugModule que representa el módulo.</span><span class="sxs-lookup"><span data-stu-id="d3ff7-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3ff7-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d3ff7-108">Remarks</span></span>  
 <span data-ttu-id="d3ff7-109">El módulo no debe utilizarse después de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="d3ff7-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3ff7-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3ff7-110">Requirements</span></span>  
 <span data-ttu-id="d3ff7-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3ff7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3ff7-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3ff7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3ff7-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3ff7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3ff7-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3ff7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ff7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3ff7-115">See also</span></span>

- [<span data-ttu-id="d3ff7-116">LoadModule (método)</span><span class="sxs-lookup"><span data-stu-id="d3ff7-116">LoadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="d3ff7-117">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3ff7-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
