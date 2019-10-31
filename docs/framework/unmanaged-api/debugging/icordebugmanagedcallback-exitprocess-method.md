---
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
ms.openlocfilehash: 4518637eb47acf416a02c045f8ca6f8a90167277
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130788"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="ea905-102">ICorDebugManagedCallback::ExitProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="ea905-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="ea905-103">Notifica al depurador que se ha salido de un proceso.</span><span class="sxs-lookup"><span data-stu-id="ea905-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea905-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea905-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea905-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ea905-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="ea905-106">de Un puntero a un objeto ICorDebugProcess que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="ea905-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea905-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ea905-107">Remarks</span></span>  
 <span data-ttu-id="ea905-108">No se puede continuar desde un evento `ExitProcess`.</span><span class="sxs-lookup"><span data-stu-id="ea905-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="ea905-109">Este evento puede desencadenarse de forma asincrónica en otros eventos mientras el proceso parece estar detenido.</span><span class="sxs-lookup"><span data-stu-id="ea905-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="ea905-110">Esto puede ocurrir si el proceso finaliza mientras se detiene, normalmente debido a una fuerza externa.</span><span class="sxs-lookup"><span data-stu-id="ea905-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="ea905-111">Si el Common Language Runtime (CLR) ya está enviando una devolución de llamada administrada, este evento se retrasará hasta que se devuelva esa devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="ea905-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="ea905-112">El evento `ExitProcess` es el único evento de salida o descarga que se garantiza que se llamará al apagar.</span><span class="sxs-lookup"><span data-stu-id="ea905-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea905-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea905-113">Requirements</span></span>  
 <span data-ttu-id="ea905-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea905-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea905-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea905-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea905-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea905-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea905-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea905-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea905-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea905-118">See also</span></span>

- [<span data-ttu-id="ea905-119">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ea905-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
