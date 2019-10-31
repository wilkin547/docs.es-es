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
ms.openlocfilehash: 70aaf32b9da751b49571ab98a95e432b7f84caa9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130637"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="5e64b-102">ICorDebugManagedCallback::UnloadModule (Método)</span><span class="sxs-lookup"><span data-stu-id="5e64b-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="5e64b-103">Notifica al depurador que se ha descargado un módulo de Common Language Runtime (DLL).</span><span class="sxs-lookup"><span data-stu-id="5e64b-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e64b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e64b-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e64b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5e64b-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5e64b-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contenía el módulo.</span><span class="sxs-lookup"><span data-stu-id="5e64b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="5e64b-107">de Un puntero a un objeto ICorDebugModule que representa el módulo.</span><span class="sxs-lookup"><span data-stu-id="5e64b-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e64b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5e64b-108">Remarks</span></span>  
 <span data-ttu-id="5e64b-109">El módulo no debe usarse después de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="5e64b-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e64b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e64b-110">Requirements</span></span>  
 <span data-ttu-id="5e64b-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e64b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e64b-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e64b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e64b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e64b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e64b-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e64b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e64b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e64b-115">See also</span></span>

- [<span data-ttu-id="5e64b-116">LoadModule (método)</span><span class="sxs-lookup"><span data-stu-id="5e64b-116">LoadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="5e64b-117">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e64b-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
