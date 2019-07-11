---
title: ICorDebugModule::EnableClassLoadCallbacks (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableClassLoadCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableClassLoadCallbacks
helpviewer_keywords:
- ICorDebugModule::EnableClassLoadCallbacks method [.NET Framework debugging]
- EnableClassLoadCallbacks method [.NET Framework debugging]
ms.assetid: 78dad5e4-8e2e-400f-bec3-92ff0205cd82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec9b4867ad19f25e35ca31c007c0d238b949abab
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762225"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="35552-102">ICorDebugModule::EnableClassLoadCallbacks (Método)</span><span class="sxs-lookup"><span data-stu-id="35552-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="35552-103">Controles si el [loadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) y [UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) devoluciones de llamada se llaman para este módulo.</span><span class="sxs-lookup"><span data-stu-id="35552-103">Controls whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35552-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35552-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35552-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="35552-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="35552-106">[in] Establezca este valor en `true` para habilitar common language runtime (CLR) para llamar a la `ICorDebugManagedCallback::LoadClass` y `ICorDebugManagedCallback::UnloadClass` métodos cuando se producen los eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="35552-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="35552-107">El valor predeterminado es `false` para módulos no dinámicos.</span><span class="sxs-lookup"><span data-stu-id="35552-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="35552-108">El valor es siempre `true` para los módulos dinámicos y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="35552-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35552-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="35552-109">Remarks</span></span>  
 <span data-ttu-id="35552-110">El `ICorDebugManagedCallback::LoadClass` y `ICorDebugManagedCallback::UnloadClass` devoluciones de llamada siempre están habilitadas para los módulos dinámicos y no se puede deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="35552-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35552-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35552-111">Requirements</span></span>  
 <span data-ttu-id="35552-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35552-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35552-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35552-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35552-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35552-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35552-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35552-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35552-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="35552-116">See also</span></span>
