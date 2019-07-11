---
title: ICorDebugThread2::GetTaskID (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetTaskID
helpviewer_keywords:
- ICorDebugThread2::GetTaskID method [.NET Framework debugging]
- GetTaskID method [.NET Framework debugging]
ms.assetid: 6ba3c6ee-4ba1-4c98-bf1e-8531acd3da09
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1272df17a9a9a500b84f62914811b8d109bf3cdd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768952"
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="2a05c-102">ICorDebugThread2::GetTaskID (Método)</span><span class="sxs-lookup"><span data-stu-id="2a05c-102">ICorDebugThread2::GetTaskID Method</span></span>
<span data-ttu-id="2a05c-103">Obtiene el identificador de la tarea que se ejecuta en este subproceso.</span><span class="sxs-lookup"><span data-stu-id="2a05c-103">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a05c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a05c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a05c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a05c-105">Parameters</span></span>  
 `pTaskId`  
 <span data-ttu-id="2a05c-106">[out] Un puntero al identificador de la tarea que se ejecuta en el subproceso representado por este objeto ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="2a05c-106">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a05c-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2a05c-107">Remarks</span></span>  
 <span data-ttu-id="2a05c-108">Solo se puede ejecutar una tarea en el subproceso si el subproceso está asociado con una conexión.</span><span class="sxs-lookup"><span data-stu-id="2a05c-108">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="2a05c-109">`GetTaskID` Devuelve cero `pTaskId` si el subproceso no está asociado con una conexión.</span><span class="sxs-lookup"><span data-stu-id="2a05c-109">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a05c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a05c-110">Requirements</span></span>  
 <span data-ttu-id="2a05c-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a05c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a05c-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a05c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a05c-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a05c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a05c-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a05c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
