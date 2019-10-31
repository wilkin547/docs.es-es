---
title: ICorDebugModule::IsDynamic (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsDynamic
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsDynamic
helpviewer_keywords:
- IsDynamic method [.NET Framework debugging]
- ICorDebugModule::IsDynamic method [.NET Framework debugging]
ms.assetid: 5eefe716-5025-4a4c-970c-c823cdc7bb87
topic_type:
- apiref
ms.openlocfilehash: 5774b40178ce0d7c2ef5d063a37b9011fc2630df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127951"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="0f22e-102">ICorDebugModule::IsDynamic (Método)</span><span class="sxs-lookup"><span data-stu-id="0f22e-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="0f22e-103">Obtiene un valor que indica si este módulo es dinámico.</span><span class="sxs-lookup"><span data-stu-id="0f22e-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f22e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f22e-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f22e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f22e-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="0f22e-106">[out] `true` si este módulo es dinámico; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="0f22e-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f22e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0f22e-107">Remarks</span></span>  
 <span data-ttu-id="0f22e-108">Un módulo dinámico puede agregar nuevas clases y eliminar clases existentes incluso después de que se haya cargado el módulo.</span><span class="sxs-lookup"><span data-stu-id="0f22e-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="0f22e-109">Las devoluciones de llamada [ICorDebugManagedCallback:: loadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) y [ICorDebugManagedCallback:: UnloadClass (](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) informan al depurador cuando se ha agregado o eliminado una clase.</span><span class="sxs-lookup"><span data-stu-id="0f22e-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f22e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f22e-110">Requirements</span></span>  
 <span data-ttu-id="0f22e-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f22e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f22e-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f22e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f22e-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f22e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f22e-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f22e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
