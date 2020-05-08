---
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
ms.openlocfilehash: 98a9b285323bc3ad94b4f555e72a4b3242519801
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976296"
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="f1cc8-102">ICorDebugEval::Abort (Método)</span><span class="sxs-lookup"><span data-stu-id="f1cc8-102">ICorDebugEval::Abort Method</span></span>
<span data-ttu-id="f1cc8-103">Anula el cálculo que este objeto ICorDebugEval está realizando actualmente.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1cc8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1cc8-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="f1cc8-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f1cc8-105">Remarks</span></span>  
 <span data-ttu-id="f1cc8-106">Si la evaluación está anidada y no es la más reciente, puede producirse `Abort` un error en el método.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1cc8-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1cc8-107">Requirements</span></span>  
 <span data-ttu-id="f1cc8-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1cc8-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1cc8-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1cc8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1cc8-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1cc8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1cc8-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1cc8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
