---
title: "ICorDebugProcess2::GetThreadForTaskID (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.GetThreadForTaskID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::GetThreadForTaskID
helpviewer_keywords:
- ICorDebugProcess2::GetThreadForTaskId method [.NET Framework debugging]
- GetThreadForTaskID method [.NET Framework debugging]
ms.assetid: 32d54a5b-8ad3-405b-a1b9-0936a3b49d1e
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6b7a16baca809bd794b5cf6b668f69487be7c122
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocess2getthreadfortaskid-method"></a><span data-ttu-id="fd13b-102">ICorDebugProcess2::GetThreadForTaskID (Método)</span><span class="sxs-lookup"><span data-stu-id="fd13b-102">ICorDebugProcess2::GetThreadForTaskID Method</span></span>
<span data-ttu-id="fd13b-103">Obtiene el subproceso en el que se ejecuta la tarea con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="fd13b-103">Gets the thread on which the task with the specified identifier is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd13b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd13b-104">Syntax</span></span>  
  
```  
HRESULT GetThreadForTaskID (  
    [in]  TASKID            taskid,  
    [out] ICorDebugThread2  **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd13b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fd13b-105">Parameters</span></span>  
 `taskid`  
 <span data-ttu-id="fd13b-106">[in] El identificador de la tarea.</span><span class="sxs-lookup"><span data-stu-id="fd13b-106">[in] The identifier of the task.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="fd13b-107">[out] Un puntero a la dirección de un objeto ICorDebugThread2 que representa el subproceso que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="fd13b-107">[out] A pointer to the address of an ICorDebugThread2 object that represents the thread to be retrieved.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd13b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fd13b-108">Remarks</span></span>  
 <span data-ttu-id="fd13b-109">El host puede establecer el identificador de tarea mediante la [ICLRTask:: SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="fd13b-109">The host can set the task identifier by using the [ICLRTask::SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd13b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd13b-110">Requirements</span></span>  
 <span data-ttu-id="fd13b-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd13b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd13b-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd13b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd13b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd13b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd13b-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd13b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
