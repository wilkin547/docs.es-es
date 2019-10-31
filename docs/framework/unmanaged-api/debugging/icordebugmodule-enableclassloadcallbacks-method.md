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
ms.openlocfilehash: c18ed781d44c873b4cd1957bf0102a4ce0cccad4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139216"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="7b05f-102">ICorDebugModule::EnableClassLoadCallbacks (Método)</span><span class="sxs-lookup"><span data-stu-id="7b05f-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="7b05f-103">Controla si se llama a las devoluciones de llamada [ICorDebugManagedCallback:: loadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) y [ICorDebugManagedCallback:: UnloadClass (](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) para este módulo.</span><span class="sxs-lookup"><span data-stu-id="7b05f-103">Controls whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b05f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b05f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b05f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b05f-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="7b05f-106">de Establezca este valor en `true` para permitir que el Common Language Runtime (CLR) llame a los métodos `ICorDebugManagedCallback::LoadClass` y `ICorDebugManagedCallback::UnloadClass` cuando se produzcan los eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="7b05f-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="7b05f-107">El valor predeterminado es `false` para los módulos no dinámicos.</span><span class="sxs-lookup"><span data-stu-id="7b05f-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="7b05f-108">El valor siempre es `true` para los módulos dinámicos y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="7b05f-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b05f-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7b05f-109">Remarks</span></span>  
 <span data-ttu-id="7b05f-110">Las devoluciones de llamada `ICorDebugManagedCallback::LoadClass` y `ICorDebugManagedCallback::UnloadClass` siempre están habilitadas para los módulos dinámicos y no se pueden deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="7b05f-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b05f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b05f-111">Requirements</span></span>  
 <span data-ttu-id="7b05f-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b05f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b05f-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b05f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b05f-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b05f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b05f-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b05f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b05f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b05f-116">See also</span></span>
