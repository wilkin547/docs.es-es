---
description: 'Más información acerca de: ICorDebugManagedCallback:: ExitProcess (método)'
title: ICorDebugManagedCallback::ExitProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type:
- apiref
ms.openlocfilehash: 3418931b8397edefcb801986275c35b28e00072d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790963"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="4be40-103">ICorDebugManagedCallback::ExitProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="4be40-103">ICorDebugManagedCallback::ExitProcess Method</span></span>

<span data-ttu-id="4be40-104">Notifica al depurador que se ha salido de un proceso.</span><span class="sxs-lookup"><span data-stu-id="4be40-104">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4be40-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4be40-105">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4be40-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4be40-106">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="4be40-107">de Un puntero a un objeto ICorDebugProcess que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="4be40-107">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4be40-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4be40-108">Remarks</span></span>  

 <span data-ttu-id="4be40-109">No se puede continuar a partir de un `ExitProcess` evento.</span><span class="sxs-lookup"><span data-stu-id="4be40-109">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="4be40-110">Este evento puede desencadenarse de forma asincrónica en otros eventos mientras el proceso parece estar detenido.</span><span class="sxs-lookup"><span data-stu-id="4be40-110">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="4be40-111">Esto puede ocurrir si el proceso finaliza mientras se detiene, normalmente debido a una fuerza externa.</span><span class="sxs-lookup"><span data-stu-id="4be40-111">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="4be40-112">Si el Common Language Runtime (CLR) ya está enviando una devolución de llamada administrada, este evento se retrasará hasta que se devuelva esa devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="4be40-112">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="4be40-113">El `ExitProcess` evento es el único evento de salida o descarga que se garantiza que se llamará al apagar.</span><span class="sxs-lookup"><span data-stu-id="4be40-113">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4be40-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4be40-114">Requirements</span></span>  

 <span data-ttu-id="4be40-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4be40-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4be40-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4be40-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4be40-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4be40-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4be40-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4be40-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4be40-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="4be40-119">See also</span></span>

- [<span data-ttu-id="4be40-120">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4be40-120">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
