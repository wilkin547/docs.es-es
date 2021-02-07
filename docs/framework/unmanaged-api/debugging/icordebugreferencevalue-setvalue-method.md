---
description: 'Más información acerca de: ICorDebugReferenceValue:: SetValue (método)'
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
ms.openlocfilehash: 44909962d2716ddb606d98a2f6b3804247c581cd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690917"
---
# <a name="icordebugreferencevaluesetvalue-method"></a><span data-ttu-id="d0ccd-103">ICorDebugReferenceValue::SetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="d0ccd-103">ICorDebugReferenceValue::SetValue Method</span></span>

<span data-ttu-id="d0ccd-104">Establece la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="d0ccd-104">Sets the specified memory address.</span></span> <span data-ttu-id="d0ccd-105">Es decir, este método establece este ICorDebugReferenceValue para que apunte a un objeto.</span><span class="sxs-lookup"><span data-stu-id="d0ccd-105">That is, this method sets this ICorDebugReferenceValue to point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0ccd-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0ccd-106">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] CORDB_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0ccd-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d0ccd-107">Parameters</span></span>  

 `value`  
 <span data-ttu-id="d0ccd-108">de `CORDB_ADDRESS` Valor que especifica la dirección del objeto al que `ICorDebugReferenceValue` señala este.</span><span class="sxs-lookup"><span data-stu-id="d0ccd-108">[in] A `CORDB_ADDRESS` value that specifies the address of the object to which this `ICorDebugReferenceValue` points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0ccd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0ccd-109">Requirements</span></span>  

 <span data-ttu-id="d0ccd-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0ccd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0ccd-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0ccd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0ccd-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0ccd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0ccd-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0ccd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
