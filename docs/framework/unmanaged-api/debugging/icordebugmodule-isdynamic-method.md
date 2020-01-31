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
ms.openlocfilehash: 45b1d0c0a3199227ab644ba8732198dd14b1cb4c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792995"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="665c6-102">ICorDebugModule::IsDynamic (Método)</span><span class="sxs-lookup"><span data-stu-id="665c6-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="665c6-103">Obtiene un valor que indica si este módulo es dinámico.</span><span class="sxs-lookup"><span data-stu-id="665c6-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="665c6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="665c6-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="665c6-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="665c6-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="665c6-106">[out] `true` si este módulo es dinámico; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="665c6-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="665c6-107">Notas</span><span class="sxs-lookup"><span data-stu-id="665c6-107">Remarks</span></span>  
 <span data-ttu-id="665c6-108">Un módulo dinámico puede agregar nuevas clases y eliminar clases existentes incluso después de que se haya cargado el módulo.</span><span class="sxs-lookup"><span data-stu-id="665c6-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="665c6-109">Las devoluciones de llamada [ICorDebugManagedCallback:: loadClass](icordebugmanagedcallback-loadclass-method.md) y [ICorDebugManagedCallback:: UnloadClass (](icordebugmanagedcallback-unloadclass-method.md) informan al depurador cuando se ha agregado o eliminado una clase.</span><span class="sxs-lookup"><span data-stu-id="665c6-109">The [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="665c6-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="665c6-110">Requirements</span></span>  
 <span data-ttu-id="665c6-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="665c6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="665c6-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="665c6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="665c6-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="665c6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="665c6-114">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="665c6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
