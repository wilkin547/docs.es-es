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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 42330296defe90980dd431ce39765a549057b82a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416886"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="d46ff-102">ICorDebugManagedCallback::ExitProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="d46ff-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="d46ff-103">Notifica al depurador que un proceso ha terminado.</span><span class="sxs-lookup"><span data-stu-id="d46ff-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d46ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d46ff-104">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d46ff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d46ff-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="d46ff-106">[in] Un puntero a un objeto ICorDebugProcess que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="d46ff-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d46ff-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d46ff-107">Remarks</span></span>  
 <span data-ttu-id="d46ff-108">No puede continuar desde un `ExitProcess` eventos.</span><span class="sxs-lookup"><span data-stu-id="d46ff-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="d46ff-109">Este evento se puede activar de forma asincrónica a otros eventos mientras el proceso parece estar detenido.</span><span class="sxs-lookup"><span data-stu-id="d46ff-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="d46ff-110">Esto puede ocurrir si el proceso finaliza mientras está detenido, normalmente debido a alguna causa externa.</span><span class="sxs-lookup"><span data-stu-id="d46ff-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="d46ff-111">Si common language runtime (CLR) que ya está ejecutando una devolución de llamada administrada, este evento se retrasará hasta después de esa devolución de llamada ha devuelto.</span><span class="sxs-lookup"><span data-stu-id="d46ff-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="d46ff-112">El `ExitProcess` evento es el único evento de salida/descarga que se garantiza que se llama al apagar el equipo.</span><span class="sxs-lookup"><span data-stu-id="d46ff-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d46ff-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d46ff-113">Requirements</span></span>  
 <span data-ttu-id="d46ff-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d46ff-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d46ff-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d46ff-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d46ff-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d46ff-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d46ff-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d46ff-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d46ff-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d46ff-118">See Also</span></span>  
 [<span data-ttu-id="d46ff-119">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d46ff-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
