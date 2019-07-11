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
ms.openlocfilehash: 73b84179717e4b96a5c3637b85ae936a23bbf42d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748855"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="dfc80-102">ICorDebugController::EnumerateThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="dfc80-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="dfc80-103">Obtiene un enumerador para los subprocesos administrados activos en el proceso.</span><span class="sxs-lookup"><span data-stu-id="dfc80-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfc80-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dfc80-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfc80-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dfc80-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="dfc80-106">[out] Un puntero a la dirección de un objeto "ICorDebugThreadEnum" que representa un enumerador para todos los subprocesos administrados que están activos en el proceso.</span><span class="sxs-lookup"><span data-stu-id="dfc80-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfc80-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dfc80-107">Remarks</span></span>  
 <span data-ttu-id="dfc80-108">Un subproceso se considera activo después de la [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) se ha enviado la devolución de llamada y antes de la [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) se ha enviado la devolución de llamada .</span><span class="sxs-lookup"><span data-stu-id="dfc80-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="dfc80-109">Un subproceso administrado no puede tener necesariamente ningún marco administrado en su pila.</span><span class="sxs-lookup"><span data-stu-id="dfc80-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="dfc80-110">Los subprocesos se pueden enumerar incluso antes el [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="dfc80-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="dfc80-111">Naturalmente, la enumeración estará vacía.</span><span class="sxs-lookup"><span data-stu-id="dfc80-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfc80-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dfc80-112">Requirements</span></span>  
 <span data-ttu-id="dfc80-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfc80-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfc80-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dfc80-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dfc80-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfc80-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfc80-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfc80-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfc80-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfc80-117">See also</span></span>
