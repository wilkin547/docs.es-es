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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8012d669cabc1bb589dcfe66bdf2e9b83dc5cb2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988040"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="baedd-102">ICorDebugModule::IsDynamic (Método)</span><span class="sxs-lookup"><span data-stu-id="baedd-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="baedd-103">Obtiene un valor que indica si este módulo es dinámico.</span><span class="sxs-lookup"><span data-stu-id="baedd-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baedd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="baedd-104">Syntax</span></span>  
  
```  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="baedd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="baedd-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="baedd-106">[out] `true` si este módulo es dinámico; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="baedd-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="baedd-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="baedd-107">Remarks</span></span>  
 <span data-ttu-id="baedd-108">Un módulo dinámico puede agregar nuevas clases y eliminar las clases existentes, incluso después de que se ha cargado el módulo.</span><span class="sxs-lookup"><span data-stu-id="baedd-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="baedd-109">El [loadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) y [UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) devoluciones de llamada de informan al depurador cuando se han agregado o eliminado una clase.</span><span class="sxs-lookup"><span data-stu-id="baedd-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baedd-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="baedd-110">Requirements</span></span>  
 <span data-ttu-id="baedd-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="baedd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baedd-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="baedd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="baedd-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="baedd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="baedd-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baedd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
