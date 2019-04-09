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
ms.openlocfilehash: 51162bfb6f9763d2ab4ac1f86e0ccdc15b601271
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159879"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="a983b-102">ICorDebugManagedCallback::ExitProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="a983b-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="a983b-103">Notifica al depurador que un proceso ha terminado.</span><span class="sxs-lookup"><span data-stu-id="a983b-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a983b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a983b-104">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a983b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a983b-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="a983b-106">[in] Un puntero a un objeto ICorDebugProcess que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="a983b-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a983b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a983b-107">Remarks</span></span>  
 <span data-ttu-id="a983b-108">No puede continuar desde un `ExitProcess` eventos.</span><span class="sxs-lookup"><span data-stu-id="a983b-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="a983b-109">Este evento puede desencadenar de forma asincrónica a otros eventos mientras el proceso parece estar detenido.</span><span class="sxs-lookup"><span data-stu-id="a983b-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="a983b-110">Esto puede ocurrir si el proceso finaliza mientras está detenido, normalmente debido a algún factor externo.</span><span class="sxs-lookup"><span data-stu-id="a983b-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="a983b-111">Si common language runtime (CLR) que ya está ejecutando una devolución de llamada administrada, este evento se retrasará hasta después de que devuelva esa devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="a983b-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="a983b-112">El `ExitProcess` eventos es el único evento de salida o descarga que se garantiza que se llama a cerrar.</span><span class="sxs-lookup"><span data-stu-id="a983b-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a983b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a983b-113">Requirements</span></span>  
 <span data-ttu-id="a983b-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a983b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a983b-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a983b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a983b-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a983b-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a983b-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a983b-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a983b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a983b-118">See also</span></span>

- [<span data-ttu-id="a983b-119">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a983b-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
