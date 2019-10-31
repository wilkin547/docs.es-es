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
ms.openlocfilehash: 78402e5e099815fe309618e692285de91b8b29f7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124237"
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="f7729-102">ICorDebugEval::Abort (Método)</span><span class="sxs-lookup"><span data-stu-id="f7729-102">ICorDebugEval::Abort Method</span></span>
<span data-ttu-id="f7729-103">Anula el cálculo que este objeto ICorDebugEval está realizando actualmente.</span><span class="sxs-lookup"><span data-stu-id="f7729-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7729-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7729-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="f7729-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7729-105">Remarks</span></span>  
 <span data-ttu-id="f7729-106">Si la evaluación está anidada y no es la más reciente, puede producirse un error en el método `Abort`.</span><span class="sxs-lookup"><span data-stu-id="f7729-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7729-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7729-107">Requirements</span></span>  
 <span data-ttu-id="f7729-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7729-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7729-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7729-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7729-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7729-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7729-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7729-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
