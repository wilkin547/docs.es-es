---
description: 'Más información acerca de: ICorDebugModule:: EnableClassLoadCallbacks ((método)'
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
ms.openlocfilehash: 16516cceae9a10288f8660fa69d8e0c018953777
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801090"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="2a5a6-103">ICorDebugModule::EnableClassLoadCallbacks (Método)</span><span class="sxs-lookup"><span data-stu-id="2a5a6-103">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>

<span data-ttu-id="2a5a6-104">Controla si se llama a las devoluciones de llamada [ICorDebugManagedCallback:: loadClass](icordebugmanagedcallback-loadclass-method.md) y [ICorDebugManagedCallback:: UnloadClass (](icordebugmanagedcallback-unloadclass-method.md) para este módulo.</span><span class="sxs-lookup"><span data-stu-id="2a5a6-104">Controls whether the [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a5a6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a5a6-105">Syntax</span></span>  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a5a6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a5a6-106">Parameters</span></span>  

 `bClassLoadCallbacks`  
 <span data-ttu-id="2a5a6-107">de Establezca este valor en `true` para permitir que el Common Language Runtime (CLR) llame a `ICorDebugManagedCallback::LoadClass` los `ICorDebugManagedCallback::UnloadClass` métodos y cuando se produzcan los eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="2a5a6-107">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="2a5a6-108">El valor predeterminado es `false` para los módulos no dinámicos.</span><span class="sxs-lookup"><span data-stu-id="2a5a6-108">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="2a5a6-109">El valor siempre es `true` para los módulos dinámicos y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="2a5a6-109">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a5a6-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2a5a6-110">Remarks</span></span>  

 <span data-ttu-id="2a5a6-111">Las `ICorDebugManagedCallback::LoadClass` `ICorDebugManagedCallback::UnloadClass` devoluciones de llamada y siempre están habilitadas para los módulos dinámicos y no se pueden deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="2a5a6-111">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a5a6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a5a6-112">Requirements</span></span>  

 <span data-ttu-id="2a5a6-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a5a6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a5a6-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a5a6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a5a6-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a5a6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a5a6-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a5a6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a5a6-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a5a6-117">See also</span></span>
