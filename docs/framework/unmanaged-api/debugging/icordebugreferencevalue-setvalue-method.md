---
title: ICorDebugReferenceValue::SetValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::SetValue
helpviewer_keywords:
- SetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::SetValue method [.NET Framework debugging]
ms.assetid: 3d3f6eec-d772-401f-a028-1a2ecdc31e95
topic_type:
- apiref
ms.openlocfilehash: 3fdd3180a01e4609ac40fd358879c0d2569234ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728386"
---
# <a name="icordebugreferencevaluesetvalue-method"></a><span data-ttu-id="8e6f8-102">ICorDebugReferenceValue::SetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="8e6f8-102">ICorDebugReferenceValue::SetValue Method</span></span>

<span data-ttu-id="8e6f8-103">Establece la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="8e6f8-103">Sets the specified memory address.</span></span> <span data-ttu-id="8e6f8-104">Es decir, este método establece este ICorDebugReferenceValue para que apunte a un objeto.</span><span class="sxs-lookup"><span data-stu-id="8e6f8-104">That is, this method sets this ICorDebugReferenceValue to point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e6f8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e6f8-105">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] CORDB_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e6f8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8e6f8-106">Parameters</span></span>  

 `value`  
 <span data-ttu-id="8e6f8-107">de `CORDB_ADDRESS` Valor que especifica la dirección del objeto al que `ICorDebugReferenceValue` señala este.</span><span class="sxs-lookup"><span data-stu-id="8e6f8-107">[in] A `CORDB_ADDRESS` value that specifies the address of the object to which this `ICorDebugReferenceValue` points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e6f8-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e6f8-108">Requirements</span></span>  

 <span data-ttu-id="8e6f8-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e6f8-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e6f8-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e6f8-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e6f8-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e6f8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e6f8-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e6f8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
