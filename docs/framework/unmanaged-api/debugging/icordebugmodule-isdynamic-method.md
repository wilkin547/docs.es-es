---
description: 'Más información acerca de: ICorDebugModule:: isDynamic ((método)'
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
ms.openlocfilehash: 06ecb7aaffbe73da29bbdbba9446839db54c58c3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660107"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="35ba0-103">ICorDebugModule::IsDynamic (Método)</span><span class="sxs-lookup"><span data-stu-id="35ba0-103">ICorDebugModule::IsDynamic Method</span></span>

<span data-ttu-id="35ba0-104">Obtiene un valor que indica si este módulo es dinámico.</span><span class="sxs-lookup"><span data-stu-id="35ba0-104">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35ba0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35ba0-105">Syntax</span></span>  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35ba0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="35ba0-106">Parameters</span></span>  

 `pDynamic`  
 <span data-ttu-id="35ba0-107">[out] `true` Si este módulo es dinámico; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="35ba0-107">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35ba0-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="35ba0-108">Remarks</span></span>  

 <span data-ttu-id="35ba0-109">Un módulo dinámico puede agregar nuevas clases y eliminar clases existentes incluso después de que se haya cargado el módulo.</span><span class="sxs-lookup"><span data-stu-id="35ba0-109">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="35ba0-110">Las devoluciones de llamada [ICorDebugManagedCallback:: loadClass](icordebugmanagedcallback-loadclass-method.md) y [ICorDebugManagedCallback:: UnloadClass (](icordebugmanagedcallback-unloadclass-method.md) informan al depurador cuando se ha agregado o eliminado una clase.</span><span class="sxs-lookup"><span data-stu-id="35ba0-110">The [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35ba0-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35ba0-111">Requirements</span></span>  

 <span data-ttu-id="35ba0-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35ba0-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35ba0-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35ba0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35ba0-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35ba0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35ba0-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35ba0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
