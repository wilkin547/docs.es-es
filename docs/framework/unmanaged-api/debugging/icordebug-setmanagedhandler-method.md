---
title: ICorDebug::SetManagedHandler (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c195e61b5929acdb0aec7d9043ce6122b0a80739
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643278"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="ae84f-102">ICorDebug::SetManagedHandler (Método)</span><span class="sxs-lookup"><span data-stu-id="ae84f-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="ae84f-103">Especifica el objeto de controlador de eventos para eventos administrados.</span><span class="sxs-lookup"><span data-stu-id="ae84f-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae84f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae84f-104">Syntax</span></span>  
  
```  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae84f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ae84f-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="ae84f-106">[in] Un puntero a un [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) objeto, que es el objeto de controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="ae84f-106">[in] A pointer to an [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae84f-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ae84f-107">Remarks</span></span>  
 <span data-ttu-id="ae84f-108">`SetManagedHandler` se debe llamar en tiempo de creación.</span><span class="sxs-lookup"><span data-stu-id="ae84f-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="ae84f-109">Si el `ICorDebugManagedCallback` la implementación no contiene interfaces suficientes para controlar los eventos de depuración para la aplicación que se está depurando, `SetManagedHandler` devuelve un HRESULT de E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="ae84f-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae84f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae84f-110">Requirements</span></span>  
 <span data-ttu-id="ae84f-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae84f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae84f-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae84f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae84f-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae84f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae84f-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae84f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae84f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae84f-115">See also</span></span>
- [<span data-ttu-id="ae84f-116">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ae84f-116">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
