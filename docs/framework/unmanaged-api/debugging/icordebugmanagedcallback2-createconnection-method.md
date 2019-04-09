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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f5035cd22ed099cec5e327c6957b13bcee52c766
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191129"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="4833c-102">ICorDebugManagedCallback2::CreateConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="4833c-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="4833c-103">Notifica al depurador que se ha creado una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="4833c-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4833c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4833c-104">Syntax</span></span>  
  
```  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4833c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4833c-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="4833c-106">[in] Un puntero a un objeto "ICorDebugProcess" que representa el proceso en el que se creó la conexión</span><span class="sxs-lookup"><span data-stu-id="4833c-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="4833c-107">[in] El identificador de la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="4833c-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="4833c-108">[in] Un puntero al nombre de la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="4833c-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4833c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4833c-109">Remarks</span></span>  
 <span data-ttu-id="4833c-110">Un `CreateConnection` se desencadenará una devolución de llamada en cualquiera de los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4833c-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
-   <span data-ttu-id="4833c-111">Cuando se adjunta un depurador a un proceso que contiene las conexiones.</span><span class="sxs-lookup"><span data-stu-id="4833c-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="4833c-112">En este caso, el tiempo de ejecución generará y enviar un `CreateConnection` eventos y un [ICorDebugManagedCallback2:: ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) eventos para cada conexión en el proceso.</span><span class="sxs-lookup"><span data-stu-id="4833c-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
-   <span data-ttu-id="4833c-113">Cuando llama un host [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) en el [API de hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="4833c-113">When a host calls [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4833c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4833c-114">Requirements</span></span>  
 <span data-ttu-id="4833c-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4833c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4833c-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4833c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4833c-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4833c-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4833c-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4833c-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4833c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="4833c-119">See also</span></span>

- [<span data-ttu-id="4833c-120">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4833c-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="4833c-121">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4833c-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
