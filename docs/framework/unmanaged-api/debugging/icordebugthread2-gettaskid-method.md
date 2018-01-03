---
title: "ICorDebugThread2::GetTaskID (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread2.GetTaskID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread2::GetTaskID
helpviewer_keywords:
- ICorDebugThread2::GetTaskID method [.NET Framework debugging]
- GetTaskID method [.NET Framework debugging]
ms.assetid: 6ba3c6ee-4ba1-4c98-bf1e-8531acd3da09
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b94478a0dfb8cc4d90dea611620238024634799
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="cfb55-102">ICorDebugThread2::GetTaskID (Método)</span><span class="sxs-lookup"><span data-stu-id="cfb55-102">ICorDebugThread2::GetTaskID Method</span></span>
<span data-ttu-id="cfb55-103">Obtiene el identificador de la tarea que se ejecuta en este subproceso.</span><span class="sxs-lookup"><span data-stu-id="cfb55-103">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfb55-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cfb55-104">Syntax</span></span>  
  
```  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cfb55-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cfb55-105">Parameters</span></span>  
 `pTaskId`  
 <span data-ttu-id="cfb55-106">[out] Un puntero al identificador de la tarea que se ejecuta en el subproceso representado por este objeto ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="cfb55-106">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cfb55-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cfb55-107">Remarks</span></span>  
 <span data-ttu-id="cfb55-108">Una tarea solo puede ejecutarse en el subproceso si el subproceso está asociado a una conexión.</span><span class="sxs-lookup"><span data-stu-id="cfb55-108">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="cfb55-109">`GetTaskID`Devuelve cero `pTaskId` si el subproceso no está asociado a una conexión.</span><span class="sxs-lookup"><span data-stu-id="cfb55-109">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfb55-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cfb55-110">Requirements</span></span>  
 <span data-ttu-id="cfb55-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfb55-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfb55-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cfb55-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cfb55-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfb55-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfb55-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfb55-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
