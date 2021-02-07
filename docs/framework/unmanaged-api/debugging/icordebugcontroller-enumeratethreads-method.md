---
description: 'Más información acerca de: ICorDebugController:: Enumeratethreads ((método)'
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
ms.openlocfilehash: b53425de36be5a435ef0dac538c5165f41db63f2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710782"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="33238-103">ICorDebugController::EnumerateThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="33238-103">ICorDebugController::EnumerateThreads Method</span></span>

<span data-ttu-id="33238-104">Obtiene un enumerador para los subprocesos administrados activos en el proceso.</span><span class="sxs-lookup"><span data-stu-id="33238-104">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33238-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33238-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33238-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33238-106">Parameters</span></span>  

 `ppThreads`  
 <span data-ttu-id="33238-107">enuncia Puntero a la dirección de un objeto "ICorDebugThreadEnum (" que representa un enumerador para todos los subprocesos administrados que están activos en el proceso.</span><span class="sxs-lookup"><span data-stu-id="33238-107">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33238-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="33238-108">Remarks</span></span>  

 <span data-ttu-id="33238-109">Un subproceso se considera activo después de que se haya enviado la devolución de llamada [ICorDebugManagedCallback:: CreateThread](icordebugmanagedcallback-createthread-method.md) y antes de que se haya enviado la devolución de llamada [ICorDebugManagedCallback:: ExitThread](icordebugmanagedcallback-exitthread-method.md) .</span><span class="sxs-lookup"><span data-stu-id="33238-109">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="33238-110">Es posible que un subproceso administrado no tenga necesariamente ningún marco administrado en la pila.</span><span class="sxs-lookup"><span data-stu-id="33238-110">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="33238-111">Los subprocesos se pueden enumerar incluso antes de la devolución de llamada [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="33238-111">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="33238-112">La enumeración estará vacía naturalmente.</span><span class="sxs-lookup"><span data-stu-id="33238-112">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33238-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33238-113">Requirements</span></span>  

 <span data-ttu-id="33238-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33238-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33238-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33238-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33238-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33238-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33238-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33238-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33238-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="33238-118">See also</span></span>
