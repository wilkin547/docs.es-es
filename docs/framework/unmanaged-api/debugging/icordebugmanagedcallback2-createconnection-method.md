---
title: "ICorDebugManagedCallback2::CreateConnection (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.CreateConnection
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::CreateConnection
helpviewer_keywords:
- CreateConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::CreateConnection method [.NET Framework debugging]
ms.assetid: 49e647be-9d63-4250-9d11-704e2a400d1b
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5e0037f72e51683e5b1d62ad7ecb9aa185f53370
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="26da8-102">ICorDebugManagedCallback2::CreateConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="26da8-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="26da8-103">Notifica al depurador que se ha creado una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="26da8-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26da8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26da8-104">Syntax</span></span>  
  
```  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="26da8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="26da8-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="26da8-106">[in] Un puntero a un objeto de "ICorDebugProcess" que representa el proceso en el que se creó la conexión</span><span class="sxs-lookup"><span data-stu-id="26da8-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="26da8-107">[in] El identificador de la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="26da8-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="26da8-108">[in] Un puntero al nombre de la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="26da8-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26da8-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="26da8-109">Remarks</span></span>  
 <span data-ttu-id="26da8-110">Un `CreateConnection` devolución de llamada se activarán en cualquiera de los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="26da8-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
-   <span data-ttu-id="26da8-111">Cuando se adjunta un depurador a un proceso que contiene las conexiones.</span><span class="sxs-lookup"><span data-stu-id="26da8-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="26da8-112">En este caso, el tiempo de ejecución generará y enviar un `CreateConnection` eventos y un [ICorDebugManagedCallback2:: ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) eventos para cada conexión en el proceso.</span><span class="sxs-lookup"><span data-stu-id="26da8-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
-   <span data-ttu-id="26da8-113">Cuando un host llama al método [ICLRDebugManager:: BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) en el [API de hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="26da8-113">When a host calls [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26da8-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26da8-114">Requirements</span></span>  
 <span data-ttu-id="26da8-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26da8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26da8-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26da8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26da8-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26da8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26da8-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26da8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26da8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="26da8-119">See Also</span></span>  
 [<span data-ttu-id="26da8-120">ICorDebugManagedCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="26da8-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="26da8-121">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="26da8-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
