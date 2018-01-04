---
title: "ICorDebugModule::IsDynamic (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.IsDynamic
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::IsDynamic
helpviewer_keywords:
- IsDynamic method [.NET Framework debugging]
- ICorDebugModule::IsDynamic method [.NET Framework debugging]
ms.assetid: 5eefe716-5025-4a4c-970c-c823cdc7bb87
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b9d7ae1a8619e3d259b6dd44c6b7b0a1c7c057c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="51bc2-102">ICorDebugModule::IsDynamic (Método)</span><span class="sxs-lookup"><span data-stu-id="51bc2-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="51bc2-103">Obtiene un valor que indica si este módulo es dinámico.</span><span class="sxs-lookup"><span data-stu-id="51bc2-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51bc2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51bc2-104">Syntax</span></span>  
  
```  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="51bc2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="51bc2-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="51bc2-106">[out] `true` si este módulo es dinámico; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="51bc2-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51bc2-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="51bc2-107">Remarks</span></span>  
 <span data-ttu-id="51bc2-108">Un módulo dinámico puede agregar nuevas clases y eliminar las clases existentes incluso después de que se ha cargado el módulo.</span><span class="sxs-lookup"><span data-stu-id="51bc2-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="51bc2-109">El [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) y [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) las devoluciones de llamada informarán el depurador cuando se han agregado o eliminado una clase.</span><span class="sxs-lookup"><span data-stu-id="51bc2-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51bc2-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51bc2-110">Requirements</span></span>  
 <span data-ttu-id="51bc2-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51bc2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51bc2-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51bc2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51bc2-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51bc2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51bc2-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51bc2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
