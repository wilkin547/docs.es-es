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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be7dde136c5bc26148468d3d8031426b17f44292
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753118"
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="91078-102">ICorDebugEval::IsActive (Método)</span><span class="sxs-lookup"><span data-stu-id="91078-102">ICorDebugEval::IsActive Method</span></span>
<span data-ttu-id="91078-103">Obtiene un valor que indica si este objeto ICorDebugEval está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="91078-103">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91078-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91078-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91078-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="91078-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="91078-106">[out] Puntero a un valor que indica si esta evaluación está activa.</span><span class="sxs-lookup"><span data-stu-id="91078-106">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91078-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91078-107">Requirements</span></span>  
 <span data-ttu-id="91078-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91078-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91078-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91078-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91078-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91078-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91078-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91078-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
