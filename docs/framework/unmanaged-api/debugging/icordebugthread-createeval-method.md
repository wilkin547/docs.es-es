---
description: 'Más información acerca de: ICorDebugThread:: Createeval ((método)'
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
ms.openlocfilehash: a789840e099a14b584e5713bee12f5c4b0717fe7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659392"
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="9955a-103">ICorDebugThread::CreateEval (Método)</span><span class="sxs-lookup"><span data-stu-id="9955a-103">ICorDebugThread::CreateEval Method</span></span>

<span data-ttu-id="9955a-104">Crea un objeto ICorDebugEval que recopila y expone la funcionalidad de esta expresión ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="9955a-104">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9955a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9955a-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9955a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9955a-106">Parameters</span></span>  

 `ppEval`  
 <span data-ttu-id="9955a-107">enuncia Puntero a la dirección de un `ICorDebugEval` objeto que recopila y expone la funcionalidad de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="9955a-107">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9955a-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9955a-108">Remarks</span></span>  

 <span data-ttu-id="9955a-109">El objeto de evaluación hará que se inserte una nueva cadena en el subproceso antes de realizar su cálculo.</span><span class="sxs-lookup"><span data-stu-id="9955a-109">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="9955a-110">Esto interrumpe el cálculo que se está llevando a cabo en el subproceso hasta que se completa la evaluación.</span><span class="sxs-lookup"><span data-stu-id="9955a-110">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9955a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9955a-111">Requirements</span></span>  

 <span data-ttu-id="9955a-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9955a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9955a-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9955a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9955a-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9955a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9955a-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9955a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
