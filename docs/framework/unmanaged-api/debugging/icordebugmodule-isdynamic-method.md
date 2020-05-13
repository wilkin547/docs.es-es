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
ms.openlocfilehash: 4517f266bbb500223214a6a8fe5881e8b29566c3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206881"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="4549b-102">ICorDebugModule::IsDynamic (Método)</span><span class="sxs-lookup"><span data-stu-id="4549b-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="4549b-103">Obtiene un valor que indica si este módulo es dinámico.</span><span class="sxs-lookup"><span data-stu-id="4549b-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4549b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4549b-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4549b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4549b-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="4549b-106">[out] `true` Si este módulo es dinámico; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="4549b-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4549b-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4549b-107">Remarks</span></span>  
 <span data-ttu-id="4549b-108">Un módulo dinámico puede agregar nuevas clases y eliminar clases existentes incluso después de que se haya cargado el módulo.</span><span class="sxs-lookup"><span data-stu-id="4549b-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="4549b-109">Las devoluciones de llamada [ICorDebugManagedCallback:: loadClass](icordebugmanagedcallback-loadclass-method.md) y [ICorDebugManagedCallback:: UnloadClass (](icordebugmanagedcallback-unloadclass-method.md) informan al depurador cuando se ha agregado o eliminado una clase.</span><span class="sxs-lookup"><span data-stu-id="4549b-109">The [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4549b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4549b-110">Requirements</span></span>  
 <span data-ttu-id="4549b-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4549b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4549b-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4549b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4549b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4549b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4549b-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4549b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
