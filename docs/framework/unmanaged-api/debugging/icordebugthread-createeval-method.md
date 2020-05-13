---
title: ICorDebugThread::CreateEval (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type:
- apiref
ms.openlocfilehash: f66ef88646c314502dcb610cec8ce822cab1fca2
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379280"
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="52b75-102">ICorDebugThread::CreateEval (Método)</span><span class="sxs-lookup"><span data-stu-id="52b75-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="52b75-103">Crea un objeto ICorDebugEval que recopila y expone la funcionalidad de esta expresión ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="52b75-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52b75-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52b75-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52b75-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52b75-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="52b75-106">enuncia Puntero a la dirección de un `ICorDebugEval` objeto que recopila y expone la funcionalidad de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="52b75-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52b75-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="52b75-107">Remarks</span></span>  
 <span data-ttu-id="52b75-108">El objeto de evaluación hará que se inserte una nueva cadena en el subproceso antes de realizar su cálculo.</span><span class="sxs-lookup"><span data-stu-id="52b75-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="52b75-109">Esto interrumpe el cálculo que se está llevando a cabo en el subproceso hasta que se completa la evaluación.</span><span class="sxs-lookup"><span data-stu-id="52b75-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52b75-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52b75-110">Requirements</span></span>  
 <span data-ttu-id="52b75-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52b75-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52b75-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52b75-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52b75-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52b75-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52b75-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52b75-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
