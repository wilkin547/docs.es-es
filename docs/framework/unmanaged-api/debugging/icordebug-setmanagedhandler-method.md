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
ms.openlocfilehash: 88f30089879f2d023c8fb04b52e75b2942da2a83
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130174"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="198ae-102">ICorDebug::SetManagedHandler (Método)</span><span class="sxs-lookup"><span data-stu-id="198ae-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="198ae-103">Especifica el objeto de controlador de eventos para eventos administrados.</span><span class="sxs-lookup"><span data-stu-id="198ae-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="198ae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="198ae-104">Syntax</span></span>  
  
```  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="198ae-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="198ae-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="198ae-106">[in] Un puntero a un [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) objeto, que es el objeto de controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="198ae-106">[in] A pointer to an [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="198ae-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="198ae-107">Remarks</span></span>  
 <span data-ttu-id="198ae-108">`SetManagedHandler` se debe llamar en tiempo de creación.</span><span class="sxs-lookup"><span data-stu-id="198ae-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="198ae-109">Si el `ICorDebugManagedCallback` la implementación no contiene interfaces suficientes para controlar los eventos de depuración para la aplicación que se está depurando, `SetManagedHandler` devuelve un HRESULT de E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="198ae-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="198ae-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="198ae-110">Requirements</span></span>  
 <span data-ttu-id="198ae-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="198ae-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="198ae-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="198ae-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="198ae-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="198ae-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="198ae-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="198ae-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="198ae-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="198ae-115">See also</span></span>

- [<span data-ttu-id="198ae-116">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="198ae-116">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
