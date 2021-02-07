---
description: 'Más información acerca de: ICorDebugEval:: GetResult (método)'
title: ICorDebugEval::GetResult (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetResult
helpviewer_keywords:
- ICorDebugEval::GetResult method [.NET Framework debugging]
- GetResult method [.NET Framework debugging]
ms.assetid: 50dbb9af-58a1-41f4-b56d-3da20011884f
topic_type:
- apiref
ms.openlocfilehash: 03ab00f5c9a538e11a2046da9cbfd5ad7225231c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694245"
---
# <a name="icordebugevalgetresult-method"></a><span data-ttu-id="8a2a3-103">ICorDebugEval::GetResult (Método)</span><span class="sxs-lookup"><span data-stu-id="8a2a3-103">ICorDebugEval::GetResult Method</span></span>

<span data-ttu-id="8a2a3-104">Obtiene los resultados de esta evaluación.</span><span class="sxs-lookup"><span data-stu-id="8a2a3-104">Gets the results of this evaluation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a2a3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a2a3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a2a3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8a2a3-106">Parameters</span></span>  

 `ppResult`  
 <span data-ttu-id="8a2a3-107">enuncia Puntero a la dirección de un objeto ICorDebugValue que representa los resultados de esta evaluación, si la evaluación se completa con normalidad.</span><span class="sxs-lookup"><span data-stu-id="8a2a3-107">[out] Pointer to the address of an ICorDebugValue object that represents the results of this evaluation, if the evaluation completes normally.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a2a3-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8a2a3-108">Remarks</span></span>  

 <span data-ttu-id="8a2a3-109">El `GetResult` método es válido solo después de que se complete la evaluación.</span><span class="sxs-lookup"><span data-stu-id="8a2a3-109">The `GetResult` method is valid only after the evaluation is completed.</span></span>  
  
 <span data-ttu-id="8a2a3-110">Si la evaluación se completa normalmente, `ppResult` especifica los resultados.</span><span class="sxs-lookup"><span data-stu-id="8a2a3-110">If the evaluation completes normally, `ppResult` specifies the results.</span></span> <span data-ttu-id="8a2a3-111">Si finaliza con una excepción, el resultado es la excepción que se produce.</span><span class="sxs-lookup"><span data-stu-id="8a2a3-111">If it terminates with an exception, the result is the exception thrown.</span></span> <span data-ttu-id="8a2a3-112">Si la evaluación era para un nuevo objeto, el resultado es la referencia al nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="8a2a3-112">If the evaluation was for a new object, the result is the reference to the new object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a2a3-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a2a3-113">Requirements</span></span>  

 <span data-ttu-id="8a2a3-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a2a3-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a2a3-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a2a3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a2a3-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a2a3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a2a3-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a2a3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
