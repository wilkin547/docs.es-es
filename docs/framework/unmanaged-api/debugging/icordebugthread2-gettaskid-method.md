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
ms.openlocfilehash: 9b17a179745af65bde05527bd0157f3ce06c12c6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678680"
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="acaf0-102">ICorDebugThread2::GetTaskID (Método)</span><span class="sxs-lookup"><span data-stu-id="acaf0-102">ICorDebugThread2::GetTaskID Method</span></span>

<span data-ttu-id="acaf0-103">Obtiene el identificador de la tarea que se ejecuta en este subproceso.</span><span class="sxs-lookup"><span data-stu-id="acaf0-103">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acaf0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="acaf0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acaf0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="acaf0-105">Parameters</span></span>  

 `pTaskId`  
 <span data-ttu-id="acaf0-106">enuncia Puntero al identificador de la tarea que se ejecuta en el subproceso representado por este objeto ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="acaf0-106">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acaf0-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="acaf0-107">Remarks</span></span>  

 <span data-ttu-id="acaf0-108">Una tarea solo se puede ejecutar en el subproceso si el subproceso está asociado a una conexión.</span><span class="sxs-lookup"><span data-stu-id="acaf0-108">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="acaf0-109">`GetTaskID` devuelve cero en `pTaskId` si el subproceso no está asociado a una conexión.</span><span class="sxs-lookup"><span data-stu-id="acaf0-109">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acaf0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="acaf0-110">Requirements</span></span>  

 <span data-ttu-id="acaf0-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acaf0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acaf0-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="acaf0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="acaf0-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acaf0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acaf0-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acaf0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
