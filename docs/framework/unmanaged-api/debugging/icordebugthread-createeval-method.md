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
ms.openlocfilehash: 1c0037530ae4f40be5bef4da8f398afe5f2bbb91
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688294"
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="54683-102">ICorDebugThread::CreateEval (Método)</span><span class="sxs-lookup"><span data-stu-id="54683-102">ICorDebugThread::CreateEval Method</span></span>

<span data-ttu-id="54683-103">Crea un objeto ICorDebugEval que recopila y expone la funcionalidad de esta expresión ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="54683-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54683-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54683-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54683-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="54683-105">Parameters</span></span>  

 `ppEval`  
 <span data-ttu-id="54683-106">enuncia Puntero a la dirección de un `ICorDebugEval` objeto que recopila y expone la funcionalidad de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="54683-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54683-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="54683-107">Remarks</span></span>  

 <span data-ttu-id="54683-108">El objeto de evaluación hará que se inserte una nueva cadena en el subproceso antes de realizar su cálculo.</span><span class="sxs-lookup"><span data-stu-id="54683-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="54683-109">Esto interrumpe el cálculo que se está llevando a cabo en el subproceso hasta que se completa la evaluación.</span><span class="sxs-lookup"><span data-stu-id="54683-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54683-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54683-110">Requirements</span></span>  

 <span data-ttu-id="54683-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54683-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54683-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54683-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54683-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54683-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54683-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54683-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
