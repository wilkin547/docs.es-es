---
title: ICorDebugManagedCallback2::ChangeConnection (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ChangeConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4eeecc22db5786f66b3d484b521989e71817d8e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995129"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a><span data-ttu-id="96036-102">ICorDebugManagedCallback2::ChangeConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="96036-102">ICorDebugManagedCallback2::ChangeConnection Method</span></span>
<span data-ttu-id="96036-103">Notifica al depurador que se ha cambiado el conjunto de tareas asociadas con la conexión especificada.</span><span class="sxs-lookup"><span data-stu-id="96036-103">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96036-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96036-104">Syntax</span></span>  
  
```  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96036-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="96036-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="96036-106">[in] Un puntero a un objeto "ICorDebugProcess" que representa el proceso que contiene la conexión que ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="96036-106">[in] A pointer to an "ICorDebugProcess" object that represents the process containing the connection that changed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="96036-107">[in] El identificador de la conexión que ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="96036-107">[in] The ID of the connection that changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96036-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="96036-108">Remarks</span></span>  
 <span data-ttu-id="96036-109">Un `ChangeConnection` se desencadenará una devolución de llamada en cualquiera de los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="96036-109">A `ChangeConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="96036-110">Cuando se adjunta un depurador a un proceso que contiene las conexiones.</span><span class="sxs-lookup"><span data-stu-id="96036-110">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="96036-111">En este caso, el tiempo de ejecución generará y enviar un [Icordebugmanagedcallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) eventos y un `ChangeConnection` eventos para cada conexión en el proceso.</span><span class="sxs-lookup"><span data-stu-id="96036-111">In this case, the runtime will generate and dispatch a [ICorDebugManagedCallback2::CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) event and a `ChangeConnection` event for each connection in the process.</span></span> <span data-ttu-id="96036-112">Un `ChangeConnection` evento se genera para todas las conexiones existentes, independientemente de si el conjunto de la conexión de tareas ha cambiado desde su creación.</span><span class="sxs-lookup"><span data-stu-id="96036-112">A `ChangeConnection` event is generated for every existing connection, regardless of whether that connection’s set of tasks has been changed since its creation.</span></span>  
  
- <span data-ttu-id="96036-113">Cuando llama un host [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) en el [API de hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="96036-113">When a host calls [ICLRDebugManager::SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
 <span data-ttu-id="96036-114">El depurador debe examinar todos los subprocesos del proceso para recoger los cambios nuevo.</span><span class="sxs-lookup"><span data-stu-id="96036-114">The debugger should scan all threads in the process to pick up the new changes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96036-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="96036-115">Requirements</span></span>  
 <span data-ttu-id="96036-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96036-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96036-117">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96036-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96036-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96036-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96036-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96036-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96036-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="96036-120">See also</span></span>

- [<span data-ttu-id="96036-121">ICorDebugManagedCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="96036-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="96036-122">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="96036-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
