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
ms.openlocfilehash: 22a838748414f9d89cdc7ff469f7f5cc5e11b9d4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108308"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="2f14d-102">ICorDebugModule::EnableClassLoadCallbacks (Método)</span><span class="sxs-lookup"><span data-stu-id="2f14d-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="2f14d-103">Controles si el [loadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) y [UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) devoluciones de llamada se llaman para este módulo.</span><span class="sxs-lookup"><span data-stu-id="2f14d-103">Controls whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f14d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f14d-104">Syntax</span></span>  
  
```  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f14d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2f14d-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="2f14d-106">[in] Establezca este valor en `true` para habilitar common language runtime (CLR) para llamar a la `ICorDebugManagedCallback::LoadClass` y `ICorDebugManagedCallback::UnloadClass` métodos cuando se producen los eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="2f14d-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="2f14d-107">El valor predeterminado es `false` para módulos no dinámicos.</span><span class="sxs-lookup"><span data-stu-id="2f14d-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="2f14d-108">El valor es siempre `true` para los módulos dinámicos y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="2f14d-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f14d-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2f14d-109">Remarks</span></span>  
 <span data-ttu-id="2f14d-110">El `ICorDebugManagedCallback::LoadClass` y `ICorDebugManagedCallback::UnloadClass` devoluciones de llamada siempre están habilitadas para los módulos dinámicos y no se puede deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="2f14d-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f14d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2f14d-111">Requirements</span></span>  
 <span data-ttu-id="2f14d-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f14d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f14d-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f14d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f14d-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f14d-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2f14d-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2f14d-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2f14d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f14d-116">See also</span></span>
