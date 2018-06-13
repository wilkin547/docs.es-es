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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e160eddf667b542929c8dd3790de666a8e8bb77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413064"
---
# <a name="icordebugevalgetresult-method"></a><span data-ttu-id="fa78f-102">ICorDebugEval::GetResult (Método)</span><span class="sxs-lookup"><span data-stu-id="fa78f-102">ICorDebugEval::GetResult Method</span></span>
<span data-ttu-id="fa78f-103">Obtiene los resultados de esta evaluación.</span><span class="sxs-lookup"><span data-stu-id="fa78f-103">Gets the results of this evaluation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa78f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa78f-104">Syntax</span></span>  
  
```  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa78f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fa78f-105">Parameters</span></span>  
 `ppResult`  
 <span data-ttu-id="fa78f-106">[out] Puntero a la dirección de un objeto ICorDebugValue que representa los resultados de esta evaluación, si la evaluación se completa con normalidad.</span><span class="sxs-lookup"><span data-stu-id="fa78f-106">[out] Pointer to the address of an ICorDebugValue object that represents the results of this evaluation, if the evaluation completes normally.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa78f-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fa78f-107">Remarks</span></span>  
 <span data-ttu-id="fa78f-108">El `GetResult` método es válido solo una vez completada la evaluación.</span><span class="sxs-lookup"><span data-stu-id="fa78f-108">The `GetResult` method is valid only after the evaluation is completed.</span></span>  
  
 <span data-ttu-id="fa78f-109">Si la evaluación se completa con normalidad, `ppResult` especifica los resultados.</span><span class="sxs-lookup"><span data-stu-id="fa78f-109">If the evaluation completes normally, `ppResult` specifies the results.</span></span> <span data-ttu-id="fa78f-110">Si finaliza con una excepción, el resultado es la excepción producida.</span><span class="sxs-lookup"><span data-stu-id="fa78f-110">If it terminates with an exception, the result is the exception thrown.</span></span> <span data-ttu-id="fa78f-111">Si la evaluación era para un nuevo objeto, el resultado es la referencia al nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="fa78f-111">If the evaluation was for a new object, the result is the reference to the new object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa78f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa78f-112">Requirements</span></span>  
 <span data-ttu-id="fa78f-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa78f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa78f-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa78f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa78f-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa78f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa78f-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa78f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
