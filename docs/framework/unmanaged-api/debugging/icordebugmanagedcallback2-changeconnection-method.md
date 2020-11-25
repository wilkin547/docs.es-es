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
ms.openlocfilehash: 4ba04b1a4815587b40d03819fdac795dcc7f2c4f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697277"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a><span data-ttu-id="1089a-102">ICorDebugManagedCallback2::ChangeConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="1089a-102">ICorDebugManagedCallback2::ChangeConnection Method</span></span>

<span data-ttu-id="1089a-103">Notifica al depurador que ha cambiado el conjunto de tareas asociado a la conexión especificada.</span><span class="sxs-lookup"><span data-stu-id="1089a-103">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1089a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1089a-104">Syntax</span></span>  
  
```cpp  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1089a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1089a-105">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="1089a-106">de Un puntero a un objeto "ICorDebugProcess" que representa el proceso que contiene la conexión que cambió.</span><span class="sxs-lookup"><span data-stu-id="1089a-106">[in] A pointer to an "ICorDebugProcess" object that represents the process containing the connection that changed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="1089a-107">de IDENTIFICADOR de la conexión que cambió.</span><span class="sxs-lookup"><span data-stu-id="1089a-107">[in] The ID of the connection that changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1089a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1089a-108">Remarks</span></span>  

 <span data-ttu-id="1089a-109">Una `ChangeConnection` devolución de llamada se desencadenará en cualquiera de los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="1089a-109">A `ChangeConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="1089a-110">Cuando un depurador se asocia a un proceso que contiene conexiones.</span><span class="sxs-lookup"><span data-stu-id="1089a-110">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="1089a-111">En este caso, el tiempo de ejecución generará y enviará un evento [ICorDebugManagedCallback2:: CreateConnection](icordebugmanagedcallback2-createconnection-method.md) y un `ChangeConnection` evento para cada conexión del proceso.</span><span class="sxs-lookup"><span data-stu-id="1089a-111">In this case, the runtime will generate and dispatch a [ICorDebugManagedCallback2::CreateConnection](icordebugmanagedcallback2-createconnection-method.md) event and a `ChangeConnection` event for each connection in the process.</span></span> <span data-ttu-id="1089a-112">`ChangeConnection`Se genera un evento para cada conexión existente, independientemente de si el conjunto de tareas de la conexión se ha cambiado desde su creación.</span><span class="sxs-lookup"><span data-stu-id="1089a-112">A `ChangeConnection` event is generated for every existing connection, regardless of whether that connection’s set of tasks has been changed since its creation.</span></span>  
  
- <span data-ttu-id="1089a-113">Cuando un host llama a [ICLRDebugManager:: SetConnectionTasks](../hosting/iclrdebugmanager-setconnectiontasks-method.md) en la [API de hospedaje](../hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="1089a-113">When a host calls [ICLRDebugManager::SetConnectionTasks](../hosting/iclrdebugmanager-setconnectiontasks-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
 <span data-ttu-id="1089a-114">El depurador debe examinar todos los subprocesos del proceso para recopilar los cambios nuevos.</span><span class="sxs-lookup"><span data-stu-id="1089a-114">The debugger should scan all threads in the process to pick up the new changes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1089a-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1089a-115">Requirements</span></span>  

 <span data-ttu-id="1089a-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1089a-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1089a-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1089a-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1089a-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1089a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1089a-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1089a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1089a-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1089a-120">See also</span></span>

- [<span data-ttu-id="1089a-121">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1089a-121">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="1089a-122">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1089a-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
