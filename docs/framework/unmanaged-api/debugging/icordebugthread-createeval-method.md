---
title: "ICorDebugThread::CreateEval (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.CreateEval
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 766677d9eef60c811c8537bc60bb8db29dd988c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="e443b-102">ICorDebugThread::CreateEval (Método)</span><span class="sxs-lookup"><span data-stu-id="e443b-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="e443b-103">Crea un objeto ICorDebugEval que recopila y expone la funcionalidad de este ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="e443b-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e443b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e443b-104">Syntax</span></span>  
  
```  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e443b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e443b-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="e443b-106">[out] Un puntero a la dirección de un `ICorDebugEval` objeto que recopila y expone la funcionalidad de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="e443b-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e443b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e443b-107">Remarks</span></span>  
 <span data-ttu-id="e443b-108">El objeto de evaluación insertará una nueva cadena en el subproceso antes de realizar el cálculo.</span><span class="sxs-lookup"><span data-stu-id="e443b-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="e443b-109">Esto interrumpe el cálculo que está realizando actualmente en el subproceso hasta que se complete la evaluación.</span><span class="sxs-lookup"><span data-stu-id="e443b-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e443b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e443b-110">Requirements</span></span>  
 <span data-ttu-id="e443b-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e443b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e443b-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e443b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e443b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e443b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e443b-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e443b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
