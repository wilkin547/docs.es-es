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
ms.openlocfilehash: aebabf12e6dcf12f0e1e1f24ec2ad69ea55ec86c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="9a50a-102">ICorDebugThread::CreateEval (Método)</span><span class="sxs-lookup"><span data-stu-id="9a50a-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="9a50a-103">Crea un objeto ICorDebugEval que recopila y expone la funcionalidad de este ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="9a50a-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a50a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a50a-104">Syntax</span></span>  
  
```  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a50a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9a50a-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="9a50a-106">[out] Un puntero a la dirección de un `ICorDebugEval` objeto que recopila y expone la funcionalidad de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="9a50a-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a50a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9a50a-107">Remarks</span></span>  
 <span data-ttu-id="9a50a-108">El objeto de evaluación insertará una nueva cadena en el subproceso antes de realizar el cálculo.</span><span class="sxs-lookup"><span data-stu-id="9a50a-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="9a50a-109">Esto interrumpe el cálculo que está realizando actualmente en el subproceso hasta que se complete la evaluación.</span><span class="sxs-lookup"><span data-stu-id="9a50a-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a50a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a50a-110">Requirements</span></span>  
 <span data-ttu-id="9a50a-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a50a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a50a-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a50a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a50a-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a50a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a50a-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a50a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
