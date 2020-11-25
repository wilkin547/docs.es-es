---
title: ICorDebugEval::GetThread (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::GetThread method [.NET Framework debugging]
ms.assetid: 57163b0d-c8a7-44af-9078-e7a895d29f9a
topic_type:
- apiref
ms.openlocfilehash: 0680c47e4390e876c5df99ee7eb200e7d187f0ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722198"
---
# <a name="icordebugevalgetthread-method"></a><span data-ttu-id="2d5e9-102">ICorDebugEval::GetThread (Método)</span><span class="sxs-lookup"><span data-stu-id="2d5e9-102">ICorDebugEval::GetThread Method</span></span>

<span data-ttu-id="2d5e9-103">Obtiene el subproceso en el que se ejecuta esta evaluación o que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="2d5e9-103">Gets the thread in which this evaluation is executing or will execute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d5e9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d5e9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread   **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d5e9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d5e9-105">Parameters</span></span>  

 `ppThread`  
 <span data-ttu-id="2d5e9-106">enuncia Puntero a la dirección de un objeto ICorDebugThread que representa el subproceso.</span><span class="sxs-lookup"><span data-stu-id="2d5e9-106">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d5e9-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d5e9-107">Requirements</span></span>  

 <span data-ttu-id="2d5e9-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d5e9-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d5e9-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d5e9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d5e9-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d5e9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d5e9-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d5e9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
