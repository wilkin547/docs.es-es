---
description: 'Más información acerca de: ICorDebugEval:: IsActive (método)'
title: ICorDebugEval::IsActive (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::IsActive method [.NET Framework debugging]
ms.assetid: bf2bba24-d278-43bd-b1c5-35680e748d3e
topic_type:
- apiref
ms.openlocfilehash: 2314814f8979f460063017ebdf46beb512417395
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694063"
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="3d5f1-103">ICorDebugEval::IsActive (Método)</span><span class="sxs-lookup"><span data-stu-id="3d5f1-103">ICorDebugEval::IsActive Method</span></span>

<span data-ttu-id="3d5f1-104">Obtiene un valor que indica si este objeto ICorDebugEval se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="3d5f1-104">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d5f1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d5f1-105">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d5f1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3d5f1-106">Parameters</span></span>  

 `pbActive`  
 <span data-ttu-id="3d5f1-107">enuncia Puntero a un valor que indica si esta evaluación está activa.</span><span class="sxs-lookup"><span data-stu-id="3d5f1-107">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d5f1-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d5f1-108">Requirements</span></span>  

 <span data-ttu-id="3d5f1-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d5f1-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d5f1-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d5f1-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d5f1-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d5f1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d5f1-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d5f1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
