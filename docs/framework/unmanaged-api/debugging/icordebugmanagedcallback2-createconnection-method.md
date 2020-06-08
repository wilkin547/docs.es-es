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
ms.openlocfilehash: 8e31f0a649fd1ca80d6557a0a7176549c67bf203
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501929"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="cb08d-102">ICorDebugManagedCallback2::CreateConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="cb08d-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="cb08d-103">Notifica al depurador que se ha creado una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="cb08d-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb08d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb08d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb08d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cb08d-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="cb08d-106">de Un puntero a un objeto "ICorDebugProcess" que representa el proceso en el que se creó la conexión.</span><span class="sxs-lookup"><span data-stu-id="cb08d-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="cb08d-107">de IDENTIFICADOR de la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="cb08d-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="cb08d-108">de Puntero al nombre de la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="cb08d-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb08d-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cb08d-109">Remarks</span></span>  
 <span data-ttu-id="cb08d-110">Una `CreateConnection` devolución de llamada se desencadenará en cualquiera de los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="cb08d-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="cb08d-111">Cuando un depurador se asocia a un proceso que contiene conexiones.</span><span class="sxs-lookup"><span data-stu-id="cb08d-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="cb08d-112">En este caso, el tiempo de ejecución generará y enviará un `CreateConnection` evento y un evento [ICorDebugManagedCallback2:: ChangeConnection (](icordebugmanagedcallback2-changeconnection-method.md) para cada conexión del proceso.</span><span class="sxs-lookup"><span data-stu-id="cb08d-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
- <span data-ttu-id="cb08d-113">Cuando un host llama a [ICLRDebugManager:: BeginConnection](../hosting/iclrdebugmanager-beginconnection-method.md) en la [API de hospedaje](../hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="cb08d-113">When a host calls [ICLRDebugManager::BeginConnection](../hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb08d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb08d-114">Requirements</span></span>  
 <span data-ttu-id="cb08d-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb08d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb08d-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb08d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb08d-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb08d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb08d-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb08d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb08d-119">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="cb08d-119">See also</span></span>

- [<span data-ttu-id="cb08d-120">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb08d-120">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="cb08d-121">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb08d-121">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
