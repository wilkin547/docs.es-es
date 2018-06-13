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
ms.openlocfilehash: 6f8276e2a8fd1bdc546add2ae1ca5d96298186c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412836"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="bd8f1-102">ICorDebugController::EnumerateThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="bd8f1-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="bd8f1-103">Obtiene un enumerador para los subprocesos administrados activos en el proceso.</span><span class="sxs-lookup"><span data-stu-id="bd8f1-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd8f1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd8f1-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd8f1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bd8f1-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="bd8f1-106">[out] Un puntero a la dirección de un objeto de "ICorDebugThreadEnum" que representa un enumerador para todos los subprocesos administrados que están activos en el proceso.</span><span class="sxs-lookup"><span data-stu-id="bd8f1-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd8f1-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bd8f1-107">Remarks</span></span>  
 <span data-ttu-id="bd8f1-108">Un subproceso se considera activo después de la [ICorDebugManagedCallback:: CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) ha sido enviado con devolución de llamada y antes de la [ICorDebugManagedCallback:: ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) ha sido enviado con devolución de llamada .</span><span class="sxs-lookup"><span data-stu-id="bd8f1-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="bd8f1-109">Un subproceso administrado no puede tener necesariamente los fotogramas administrados en la pila.</span><span class="sxs-lookup"><span data-stu-id="bd8f1-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="bd8f1-110">Los subprocesos se pueden enumerar incluso antes el [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="bd8f1-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="bd8f1-111">Naturalmente, la enumeración estará vacía.</span><span class="sxs-lookup"><span data-stu-id="bd8f1-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd8f1-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd8f1-112">Requirements</span></span>  
 <span data-ttu-id="bd8f1-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd8f1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd8f1-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd8f1-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd8f1-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd8f1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd8f1-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd8f1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd8f1-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd8f1-117">See Also</span></span>  
 
