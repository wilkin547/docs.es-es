---
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
ms.openlocfilehash: bd10af53d7803964ed6e699ce5328aa8a860216c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085019"
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="740c2-102">ICorDebugEval::IsActive (Método)</span><span class="sxs-lookup"><span data-stu-id="740c2-102">ICorDebugEval::IsActive Method</span></span>
<span data-ttu-id="740c2-103">Obtiene un valor que indica si este objeto ICorDebugEval se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="740c2-103">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="740c2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="740c2-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="740c2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="740c2-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="740c2-106">enuncia Puntero a un valor que indica si esta evaluación está activa.</span><span class="sxs-lookup"><span data-stu-id="740c2-106">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="740c2-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="740c2-107">Requirements</span></span>  
 <span data-ttu-id="740c2-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="740c2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="740c2-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="740c2-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="740c2-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="740c2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="740c2-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="740c2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
