---
title: ICorDebugCode::GetFunction (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
ms.openlocfilehash: 217ca0a850926e5f697340cece264c6ed442a9bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125640"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="55da4-102">ICorDebugCode::GetFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="55da4-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="55da4-103">Obtiene el "ICorDebugFunction" asociado a este "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="55da4-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55da4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55da4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55da4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="55da4-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="55da4-106">enuncia Puntero a la dirección de la función.</span><span class="sxs-lookup"><span data-stu-id="55da4-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55da4-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="55da4-107">Remarks</span></span>  
 <span data-ttu-id="55da4-108">`ICorDebugCode` y `ICorDebugFunction` mantener una relación uno a uno.</span><span class="sxs-lookup"><span data-stu-id="55da4-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55da4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55da4-109">Requirements</span></span>  
 <span data-ttu-id="55da4-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55da4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55da4-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55da4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55da4-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55da4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55da4-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55da4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
