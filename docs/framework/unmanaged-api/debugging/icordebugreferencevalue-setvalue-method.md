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
ms.openlocfilehash: 892471e7b35b4f4093df3f86d4777947b6e484e0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378304"
---
# <a name="icordebugreferencevaluesetvalue-method"></a><span data-ttu-id="fcaba-102">ICorDebugReferenceValue::SetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="fcaba-102">ICorDebugReferenceValue::SetValue Method</span></span>
<span data-ttu-id="fcaba-103">Establece la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="fcaba-103">Sets the specified memory address.</span></span> <span data-ttu-id="fcaba-104">Es decir, este método establece este ICorDebugReferenceValue para que apunte a un objeto.</span><span class="sxs-lookup"><span data-stu-id="fcaba-104">That is, this method sets this ICorDebugReferenceValue to point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcaba-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fcaba-105">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] CORDB_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcaba-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fcaba-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="fcaba-107">de `CORDB_ADDRESS`Valor que especifica la dirección del objeto al que `ICorDebugReferenceValue` señala este.</span><span class="sxs-lookup"><span data-stu-id="fcaba-107">[in] A `CORDB_ADDRESS` value that specifies the address of the object to which this `ICorDebugReferenceValue` points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcaba-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fcaba-108">Requirements</span></span>  
 <span data-ttu-id="fcaba-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcaba-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcaba-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fcaba-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fcaba-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcaba-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcaba-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcaba-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
