---
title: ICorDebugController::EnumerateThreads (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugController.EnumerateThreads
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d73a82ddbb15ba7895f1e5e10f7066909a3c7e43
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54697158"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="f88ef-102">ICorDebugController::EnumerateThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="f88ef-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="f88ef-103">Obtiene un enumerador para los subprocesos administrados activos en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f88ef-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f88ef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f88ef-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f88ef-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f88ef-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="f88ef-106">[out] Un puntero a la dirección de un objeto "ICorDebugThreadEnum" que representa un enumerador para todos los subprocesos administrados que están activos en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f88ef-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f88ef-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f88ef-107">Remarks</span></span>  
 <span data-ttu-id="f88ef-108">Un subproceso se considera activo después de la [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) se ha enviado la devolución de llamada y antes de la [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) se ha enviado la devolución de llamada .</span><span class="sxs-lookup"><span data-stu-id="f88ef-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="f88ef-109">Un subproceso administrado no puede tener necesariamente ningún marco administrado en su pila.</span><span class="sxs-lookup"><span data-stu-id="f88ef-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="f88ef-110">Los subprocesos se pueden enumerar incluso antes el [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f88ef-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="f88ef-111">Naturalmente, la enumeración estará vacía.</span><span class="sxs-lookup"><span data-stu-id="f88ef-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f88ef-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f88ef-112">Requirements</span></span>  
 <span data-ttu-id="f88ef-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f88ef-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f88ef-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f88ef-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f88ef-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f88ef-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f88ef-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f88ef-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f88ef-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f88ef-117">See also</span></span>

