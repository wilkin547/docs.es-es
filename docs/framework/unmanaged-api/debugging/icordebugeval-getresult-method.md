---
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
ms.openlocfilehash: 52bfe669d3b078657916554255a11cecfc07d484
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085088"
---
# <a name="icordebugevalgetresult-method"></a><span data-ttu-id="17c12-102">ICorDebugEval::GetResult (Método)</span><span class="sxs-lookup"><span data-stu-id="17c12-102">ICorDebugEval::GetResult Method</span></span>
<span data-ttu-id="17c12-103">Obtiene los resultados de esta evaluación.</span><span class="sxs-lookup"><span data-stu-id="17c12-103">Gets the results of this evaluation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17c12-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17c12-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17c12-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="17c12-105">Parameters</span></span>  
 `ppResult`  
 <span data-ttu-id="17c12-106">enuncia Puntero a la dirección de un objeto ICorDebugValue que representa los resultados de esta evaluación, si la evaluación se completa con normalidad.</span><span class="sxs-lookup"><span data-stu-id="17c12-106">[out] Pointer to the address of an ICorDebugValue object that represents the results of this evaluation, if the evaluation completes normally.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17c12-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="17c12-107">Remarks</span></span>  
 <span data-ttu-id="17c12-108">El método `GetResult` es válido solo después de que se complete la evaluación.</span><span class="sxs-lookup"><span data-stu-id="17c12-108">The `GetResult` method is valid only after the evaluation is completed.</span></span>  
  
 <span data-ttu-id="17c12-109">Si la evaluación se completa normalmente, `ppResult` especifica los resultados.</span><span class="sxs-lookup"><span data-stu-id="17c12-109">If the evaluation completes normally, `ppResult` specifies the results.</span></span> <span data-ttu-id="17c12-110">Si finaliza con una excepción, el resultado es la excepción que se produce.</span><span class="sxs-lookup"><span data-stu-id="17c12-110">If it terminates with an exception, the result is the exception thrown.</span></span> <span data-ttu-id="17c12-111">Si la evaluación era para un nuevo objeto, el resultado es la referencia al nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="17c12-111">If the evaluation was for a new object, the result is the reference to the new object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17c12-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17c12-112">Requirements</span></span>  
 <span data-ttu-id="17c12-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17c12-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17c12-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17c12-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17c12-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17c12-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17c12-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17c12-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
