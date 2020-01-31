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
ms.openlocfilehash: d60644d54373dfb3d1d191900df71d3e5f6547a6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788294"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a><span data-ttu-id="dfba8-102">ICorDebugManagedCallback2::ChangeConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="dfba8-102">ICorDebugManagedCallback2::ChangeConnection Method</span></span>
<span data-ttu-id="dfba8-103">Notifica al depurador que ha cambiado el conjunto de tareas asociado a la conexión especificada.</span><span class="sxs-lookup"><span data-stu-id="dfba8-103">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfba8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dfba8-104">Syntax</span></span>  
  
```cpp  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfba8-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="dfba8-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="dfba8-106">de Un puntero a un objeto "ICorDebugProcess" que representa el proceso que contiene la conexión que cambió.</span><span class="sxs-lookup"><span data-stu-id="dfba8-106">[in] A pointer to an "ICorDebugProcess" object that represents the process containing the connection that changed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="dfba8-107">de IDENTIFICADOR de la conexión que cambió.</span><span class="sxs-lookup"><span data-stu-id="dfba8-107">[in] The ID of the connection that changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfba8-108">Notas</span><span class="sxs-lookup"><span data-stu-id="dfba8-108">Remarks</span></span>  
 <span data-ttu-id="dfba8-109">Una devolución de llamada de `ChangeConnection` se desencadenará en cualquiera de los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="dfba8-109">A `ChangeConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="dfba8-110">Cuando un depurador se asocia a un proceso que contiene conexiones.</span><span class="sxs-lookup"><span data-stu-id="dfba8-110">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="dfba8-111">En este caso, el tiempo de ejecución generará y enviará un evento [ICorDebugManagedCallback2:: CreateConnection](icordebugmanagedcallback2-createconnection-method.md) y un evento `ChangeConnection` para cada conexión del proceso.</span><span class="sxs-lookup"><span data-stu-id="dfba8-111">In this case, the runtime will generate and dispatch a [ICorDebugManagedCallback2::CreateConnection](icordebugmanagedcallback2-createconnection-method.md) event and a `ChangeConnection` event for each connection in the process.</span></span> <span data-ttu-id="dfba8-112">Se genera un evento `ChangeConnection` para cada conexión existente, independientemente de si el conjunto de tareas de la conexión se ha cambiado desde su creación.</span><span class="sxs-lookup"><span data-stu-id="dfba8-112">A `ChangeConnection` event is generated for every existing connection, regardless of whether that connection’s set of tasks has been changed since its creation.</span></span>  
  
- <span data-ttu-id="dfba8-113">Cuando un host llama a [ICLRDebugManager:: SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) en la [API de hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="dfba8-113">When a host calls [ICLRDebugManager::SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
 <span data-ttu-id="dfba8-114">El depurador debe examinar todos los subprocesos del proceso para recopilar los cambios nuevos.</span><span class="sxs-lookup"><span data-stu-id="dfba8-114">The debugger should scan all threads in the process to pick up the new changes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfba8-115">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="dfba8-115">Requirements</span></span>  
 <span data-ttu-id="dfba8-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfba8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfba8-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dfba8-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dfba8-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfba8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfba8-119">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfba8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfba8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfba8-120">See also</span></span>

- [<span data-ttu-id="dfba8-121">ICorDebugManagedCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dfba8-121">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="dfba8-122">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dfba8-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
