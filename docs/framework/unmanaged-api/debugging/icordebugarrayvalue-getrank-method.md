---
description: 'Más información acerca de: ICorDebugArrayValue:: Getrank ((método)'
title: ICorDebugArrayValue::GetRank (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetRank
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetRank
helpviewer_keywords:
- ICorDebugArrayValue::GetRank method [.NET Framework debugging]
- GetRank method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 5e83c82c-593d-4691-90b0-383d218b415e
topic_type:
- apiref
ms.openlocfilehash: b84cc8fd49cbb7f7d4aa6fa7fa41b1c6cf8daf29
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723002"
---
# <a name="icordebugarrayvaluegetrank-method"></a><span data-ttu-id="95e3e-103">ICorDebugArrayValue::GetRank (Método)</span><span class="sxs-lookup"><span data-stu-id="95e3e-103">ICorDebugArrayValue::GetRank Method</span></span>

<span data-ttu-id="95e3e-104">Obtiene el número de dimensiones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="95e3e-104">Gets the number of dimensions in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95e3e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95e3e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95e3e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="95e3e-106">Parameters</span></span>  

 `pnRank`  
 <span data-ttu-id="95e3e-107">enuncia Puntero al número de dimensiones de este `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="95e3e-107">[out] A pointer to the number of dimensions in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95e3e-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="95e3e-108">Requirements</span></span>  

 <span data-ttu-id="95e3e-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95e3e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95e3e-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95e3e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95e3e-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95e3e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95e3e-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95e3e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
