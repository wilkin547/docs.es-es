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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 682d6684b6c86485530b9e5283d843f3b2eb7e46
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413809"
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="eb08c-102">ICorDebugEval::Abort (Método)</span><span class="sxs-lookup"><span data-stu-id="eb08c-102">ICorDebugEval::Abort Method</span></span>
<span data-ttu-id="eb08c-103">Anula el cálculo que está realizando este objeto ICorDebugEval.</span><span class="sxs-lookup"><span data-stu-id="eb08c-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb08c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb08c-104">Syntax</span></span>  
  
```  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="eb08c-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eb08c-105">Remarks</span></span>  
 <span data-ttu-id="eb08c-106">Si se anida la evaluación y no es el más reciente, la `Abort` método puede producir un error.</span><span class="sxs-lookup"><span data-stu-id="eb08c-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb08c-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eb08c-107">Requirements</span></span>  
 <span data-ttu-id="eb08c-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb08c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb08c-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb08c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb08c-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb08c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb08c-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb08c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
