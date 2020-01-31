---
title: ICorDebugManagedCallback2::CreateConnection (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.CreateConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::CreateConnection
helpviewer_keywords:
- CreateConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::CreateConnection method [.NET Framework debugging]
ms.assetid: 49e647be-9d63-4250-9d11-704e2a400d1b
topic_type:
- apiref
ms.openlocfilehash: e98748b523b948dc002f2ebc4e2e79fc7d659918
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781587"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="f40e7-102">ICorDebugManagedCallback2::CreateConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="f40e7-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="f40e7-103">Notifica al depurador que se ha creado una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="f40e7-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f40e7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f40e7-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f40e7-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="f40e7-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="f40e7-106">de Un puntero a un objeto "ICorDebugProcess" que representa el proceso en el que se creó la conexión.</span><span class="sxs-lookup"><span data-stu-id="f40e7-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="f40e7-107">de IDENTIFICADOR de la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="f40e7-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="f40e7-108">de Puntero al nombre de la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="f40e7-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f40e7-109">Notas</span><span class="sxs-lookup"><span data-stu-id="f40e7-109">Remarks</span></span>  
 <span data-ttu-id="f40e7-110">Una devolución de llamada de `CreateConnection` se desencadenará en cualquiera de los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="f40e7-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="f40e7-111">Cuando un depurador se asocia a un proceso que contiene conexiones.</span><span class="sxs-lookup"><span data-stu-id="f40e7-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="f40e7-112">En este caso, el tiempo de ejecución generará y enviará un evento `CreateConnection` y un evento [ICorDebugManagedCallback2:: ChangeConnection (](icordebugmanagedcallback2-changeconnection-method.md) para cada conexión del proceso.</span><span class="sxs-lookup"><span data-stu-id="f40e7-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
- <span data-ttu-id="f40e7-113">Cuando un host llama a [ICLRDebugManager:: BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) en la [API de hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="f40e7-113">When a host calls [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f40e7-114">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="f40e7-114">Requirements</span></span>  
 <span data-ttu-id="f40e7-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f40e7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f40e7-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f40e7-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f40e7-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f40e7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f40e7-118">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f40e7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f40e7-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f40e7-119">See also</span></span>

- [<span data-ttu-id="f40e7-120">ICorDebugManagedCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f40e7-120">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="f40e7-121">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f40e7-121">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
