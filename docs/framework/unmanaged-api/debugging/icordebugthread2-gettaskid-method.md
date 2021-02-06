---
description: 'Más información sobre: ICorDebugThread2:: getTaskID ((método)'
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
ms.openlocfilehash: 5429daee9150d63834c747dd5ebb763dd6f0da6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658703"
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="19722-103">ICorDebugThread2::GetTaskID (Método)</span><span class="sxs-lookup"><span data-stu-id="19722-103">ICorDebugThread2::GetTaskID Method</span></span>

<span data-ttu-id="19722-104">Obtiene el identificador de la tarea que se ejecuta en este subproceso.</span><span class="sxs-lookup"><span data-stu-id="19722-104">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19722-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19722-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19722-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="19722-106">Parameters</span></span>  

 `pTaskId`  
 <span data-ttu-id="19722-107">enuncia Puntero al identificador de la tarea que se ejecuta en el subproceso representado por este objeto ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="19722-107">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19722-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="19722-108">Remarks</span></span>  

 <span data-ttu-id="19722-109">Una tarea solo se puede ejecutar en el subproceso si el subproceso está asociado a una conexión.</span><span class="sxs-lookup"><span data-stu-id="19722-109">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="19722-110">`GetTaskID` devuelve cero en `pTaskId` si el subproceso no está asociado a una conexión.</span><span class="sxs-lookup"><span data-stu-id="19722-110">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19722-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19722-111">Requirements</span></span>  

 <span data-ttu-id="19722-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19722-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19722-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19722-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19722-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19722-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19722-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19722-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
