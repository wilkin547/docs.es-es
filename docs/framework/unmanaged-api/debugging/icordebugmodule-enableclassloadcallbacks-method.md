---
title: "ICorDebugModule::EnableClassLoadCallbacks (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.EnableClassLoadCallbacks
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::EnableClassLoadCallbacks
helpviewer_keywords:
- ICorDebugModule::EnableClassLoadCallbacks method [.NET Framework debugging]
- EnableClassLoadCallbacks method [.NET Framework debugging]
ms.assetid: 78dad5e4-8e2e-400f-bec3-92ff0205cd82
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5aa4add6dcaf662f1b5ec48b1243f012a6ae1f1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="a2307-102">ICorDebugModule::EnableClassLoadCallbacks (Método)</span><span class="sxs-lookup"><span data-stu-id="a2307-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="a2307-103">Controles si el [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) y [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) las devoluciones de llamada se llama para este módulo.</span><span class="sxs-lookup"><span data-stu-id="a2307-103">Controls whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2307-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a2307-104">Syntax</span></span>  
  
```  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2307-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a2307-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="a2307-106">[in] Establezca este valor en `true` para habilitar common language runtime (CLR) para llamar a la `ICorDebugManagedCallback::LoadClass` y `ICorDebugManagedCallback::UnloadClass` métodos cuando se producen los eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="a2307-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="a2307-107">El valor predeterminado es `false` para módulos no dinámicos.</span><span class="sxs-lookup"><span data-stu-id="a2307-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="a2307-108">El valor es siempre `true` para los módulos dinámicos y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="a2307-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2307-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a2307-109">Remarks</span></span>  
 <span data-ttu-id="a2307-110">El `ICorDebugManagedCallback::LoadClass` y `ICorDebugManagedCallback::UnloadClass` las devoluciones de llamada siempre están habilitadas para los módulos dinámicos y no puede deshabilitarse.</span><span class="sxs-lookup"><span data-stu-id="a2307-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2307-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a2307-111">Requirements</span></span>  
 <span data-ttu-id="a2307-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2307-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2307-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2307-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2307-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2307-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2307-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2307-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2307-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2307-116">See Also</span></span>  
    
 
