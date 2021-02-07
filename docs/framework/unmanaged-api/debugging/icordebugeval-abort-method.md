---
description: 'Más información acerca de: ICorDebugEval:: ABORT (método)'
title: ICorDebugEval::Abort (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.Abort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::Abort
helpviewer_keywords:
- Abort method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::Abort method [.NET Framework debugging]
ms.assetid: 7070b6d0-f2e0-44ff-b124-0944cd807e69
topic_type:
- apiref
ms.openlocfilehash: d61cb0d696a8a134d992bc8dbbfdb61103ef469f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694323"
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="5d276-103">ICorDebugEval::Abort (Método)</span><span class="sxs-lookup"><span data-stu-id="5d276-103">ICorDebugEval::Abort Method</span></span>

<span data-ttu-id="5d276-104">Anula el cálculo que este objeto ICorDebugEval está realizando actualmente.</span><span class="sxs-lookup"><span data-stu-id="5d276-104">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d276-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d276-105">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="5d276-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5d276-106">Remarks</span></span>  

 <span data-ttu-id="5d276-107">Si la evaluación está anidada y no es la más reciente, `Abort` puede producirse un error en el método.</span><span class="sxs-lookup"><span data-stu-id="5d276-107">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d276-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d276-108">Requirements</span></span>  

 <span data-ttu-id="5d276-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d276-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d276-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d276-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d276-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d276-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d276-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d276-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
