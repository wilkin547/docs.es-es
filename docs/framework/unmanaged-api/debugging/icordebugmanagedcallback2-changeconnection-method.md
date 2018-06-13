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
ms.openlocfilehash: 68288111e3f862cf1364031eaad9c63cf347146f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415943"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a><span data-ttu-id="6873e-102">ICorDebugManagedCallback2::ChangeConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="6873e-102">ICorDebugManagedCallback2::ChangeConnection Method</span></span>
<span data-ttu-id="6873e-103">Notifica al depurador que se ha cambiado el conjunto de tareas asociadas con la conexión especificada.</span><span class="sxs-lookup"><span data-stu-id="6873e-103">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6873e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6873e-104">Syntax</span></span>  
  
```  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6873e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6873e-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="6873e-106">[in] Un puntero a un objeto de "ICorDebugProcess" que representa el proceso que contiene la conexión que cambió.</span><span class="sxs-lookup"><span data-stu-id="6873e-106">[in] A pointer to an "ICorDebugProcess" object that represents the process containing the connection that changed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="6873e-107">[in] El identificador de la conexión que cambió.</span><span class="sxs-lookup"><span data-stu-id="6873e-107">[in] The ID of the connection that changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6873e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6873e-108">Remarks</span></span>  
 <span data-ttu-id="6873e-109">Un `ChangeConnection` devolución de llamada se activarán en cualquiera de los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6873e-109">A `ChangeConnection` callback will be fired in either of the following cases:</span></span>  
  
-   <span data-ttu-id="6873e-110">Cuando se adjunta un depurador a un proceso que contiene las conexiones.</span><span class="sxs-lookup"><span data-stu-id="6873e-110">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="6873e-111">En este caso, el tiempo de ejecución generará y enviar un [ICorDebugManagedCallback2:: CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) eventos y un `ChangeConnection` eventos para cada conexión en el proceso.</span><span class="sxs-lookup"><span data-stu-id="6873e-111">In this case, the runtime will generate and dispatch a [ICorDebugManagedCallback2::CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) event and a `ChangeConnection` event for each connection in the process.</span></span> <span data-ttu-id="6873e-112">Un `ChangeConnection` evento se genera para todas las conexiones existentes, independientemente de si el conjunto de la conexión de tareas ha cambiado desde su creación.</span><span class="sxs-lookup"><span data-stu-id="6873e-112">A `ChangeConnection` event is generated for every existing connection, regardless of whether that connection’s set of tasks has been changed since its creation.</span></span>  
  
-   <span data-ttu-id="6873e-113">Cuando un host llama al método [ICLRDebugManager:: SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) en el [API de hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="6873e-113">When a host calls [ICLRDebugManager::SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
 <span data-ttu-id="6873e-114">El depurador debe examinar todos los subprocesos del proceso para recoger los cambios nuevo.</span><span class="sxs-lookup"><span data-stu-id="6873e-114">The debugger should scan all threads in the process to pick up the new changes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6873e-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6873e-115">Requirements</span></span>  
 <span data-ttu-id="6873e-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6873e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6873e-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6873e-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6873e-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6873e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6873e-119">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6873e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6873e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="6873e-120">See Also</span></span>  
 [<span data-ttu-id="6873e-121">ICorDebugManagedCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6873e-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="6873e-122">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6873e-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
