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
ms.openlocfilehash: bcf97f9fffabb9ae9579016517cfc335e6f783a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404578"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="2a220-102">ICorDebug::SetManagedHandler (Método)</span><span class="sxs-lookup"><span data-stu-id="2a220-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="2a220-103">Especifica el objeto de controlador de eventos para los eventos administrados.</span><span class="sxs-lookup"><span data-stu-id="2a220-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a220-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a220-104">Syntax</span></span>  
  
```  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a220-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a220-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="2a220-106">[in] Un puntero a un [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) objeto, que es el objeto de controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="2a220-106">[in] A pointer to an [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a220-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2a220-107">Remarks</span></span>  
 <span data-ttu-id="2a220-108">`SetManagedHandler` se debe llamar en tiempo de creación.</span><span class="sxs-lookup"><span data-stu-id="2a220-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="2a220-109">Si el `ICorDebugManagedCallback` la implementación contiene interfaces suficientes para controlar los eventos de depuración para la aplicación que se está depurando, `SetManagedHandler` devuelve un HRESULT de E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="2a220-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a220-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a220-110">Requirements</span></span>  
 <span data-ttu-id="2a220-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a220-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a220-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a220-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a220-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a220-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a220-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a220-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a220-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a220-115">See Also</span></span>  
 [<span data-ttu-id="2a220-116">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2a220-116">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
