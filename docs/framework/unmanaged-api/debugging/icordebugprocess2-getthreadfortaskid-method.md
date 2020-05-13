---
title: ICorDebugProcess2::GetThreadForTaskID (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetThreadForTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetThreadForTaskID
helpviewer_keywords:
- ICorDebugProcess2::GetThreadForTaskId method [.NET Framework debugging]
- GetThreadForTaskID method [.NET Framework debugging]
ms.assetid: 32d54a5b-8ad3-405b-a1b9-0936a3b49d1e
topic_type:
- apiref
ms.openlocfilehash: 89be29c770098d92ce3c47f7c45b1bb8580f2edb
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213522"
---
# <a name="icordebugprocess2getthreadfortaskid-method"></a><span data-ttu-id="bab2a-102">ICorDebugProcess2::GetThreadForTaskID (Método)</span><span class="sxs-lookup"><span data-stu-id="bab2a-102">ICorDebugProcess2::GetThreadForTaskID Method</span></span>
<span data-ttu-id="bab2a-103">Obtiene el subproceso en el que se está ejecutando la tarea con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="bab2a-103">Gets the thread on which the task with the specified identifier is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bab2a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bab2a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadForTaskID (  
    [in]  TASKID            taskid,  
    [out] ICorDebugThread2  **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bab2a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bab2a-105">Parameters</span></span>  
 `taskid`  
 <span data-ttu-id="bab2a-106">de Identificador de la tarea.</span><span class="sxs-lookup"><span data-stu-id="bab2a-106">[in] The identifier of the task.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="bab2a-107">enuncia Puntero a la dirección de un objeto ICorDebugThread2 que representa el subproceso que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="bab2a-107">[out] A pointer to the address of an ICorDebugThread2 object that represents the thread to be retrieved.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bab2a-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bab2a-108">Remarks</span></span>  
 <span data-ttu-id="bab2a-109">El host puede establecer el identificador de tarea mediante el método [ICLRTask:: settaskidentifier (](../hosting/iclrtask-settaskidentifier-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bab2a-109">The host can set the task identifier by using the [ICLRTask::SetTaskIdentifier](../hosting/iclrtask-settaskidentifier-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bab2a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bab2a-110">Requirements</span></span>  
 <span data-ttu-id="bab2a-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bab2a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bab2a-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bab2a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bab2a-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bab2a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bab2a-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bab2a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
