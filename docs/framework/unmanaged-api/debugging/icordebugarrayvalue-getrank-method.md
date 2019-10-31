---
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
ms.openlocfilehash: 9a4cf1f9ea1ccb174b5fb9336040d5e168653fb1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088287"
---
# <a name="icordebugarrayvaluegetrank-method"></a><span data-ttu-id="0c474-102">ICorDebugArrayValue::GetRank (Método)</span><span class="sxs-lookup"><span data-stu-id="0c474-102">ICorDebugArrayValue::GetRank Method</span></span>
<span data-ttu-id="0c474-103">Obtiene el número de dimensiones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="0c474-103">Gets the number of dimensions in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c474-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c474-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c474-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0c474-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="0c474-106">enuncia Puntero al número de dimensiones de este objeto `ICorDebugArrayValue`.</span><span class="sxs-lookup"><span data-stu-id="0c474-106">[out] A pointer to the number of dimensions in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c474-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c474-107">Requirements</span></span>  
 <span data-ttu-id="0c474-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c474-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c474-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c474-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c474-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c474-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c474-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c474-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
