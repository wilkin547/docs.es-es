---
description: 'Más información sobre: ICorDebugManagedCallback2:: CreateConnection (método)'
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
ms.openlocfilehash: c7ac91217d43531505dc27a20da9cf4534366119
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790911"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="1cd47-103">ICorDebugManagedCallback2::CreateConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="1cd47-103">ICorDebugManagedCallback2::CreateConnection Method</span></span>

<span data-ttu-id="1cd47-104">Notifica al depurador que se ha creado una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="1cd47-104">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cd47-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1cd47-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1cd47-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1cd47-106">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="1cd47-107">de Un puntero a un objeto "ICorDebugProcess" que representa el proceso en el que se creó la conexión.</span><span class="sxs-lookup"><span data-stu-id="1cd47-107">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="1cd47-108">de IDENTIFICADOR de la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="1cd47-108">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="1cd47-109">de Puntero al nombre de la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="1cd47-109">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1cd47-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1cd47-110">Remarks</span></span>  

 <span data-ttu-id="1cd47-111">Una `CreateConnection` devolución de llamada se desencadenará en cualquiera de los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="1cd47-111">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="1cd47-112">Cuando un depurador se asocia a un proceso que contiene conexiones.</span><span class="sxs-lookup"><span data-stu-id="1cd47-112">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="1cd47-113">En este caso, el tiempo de ejecución generará y enviará un `CreateConnection` evento y un evento [ICorDebugManagedCallback2:: ChangeConnection (](icordebugmanagedcallback2-changeconnection-method.md) para cada conexión del proceso.</span><span class="sxs-lookup"><span data-stu-id="1cd47-113">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
- <span data-ttu-id="1cd47-114">Cuando un host llama a [ICLRDebugManager:: BeginConnection](../hosting/iclrdebugmanager-beginconnection-method.md) en la [API de hospedaje](../hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="1cd47-114">When a host calls [ICLRDebugManager::BeginConnection](../hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cd47-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1cd47-115">Requirements</span></span>  

 <span data-ttu-id="1cd47-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cd47-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cd47-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1cd47-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1cd47-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1cd47-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1cd47-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cd47-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cd47-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1cd47-120">See also</span></span>

- [<span data-ttu-id="1cd47-121">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1cd47-121">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="1cd47-122">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1cd47-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
