---
title: ICorDebugHeapValue::IsValid (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue.IsValid
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type:
- apiref
ms.openlocfilehash: 7685d1b6d5458a4405fc5a4abdb2f3134618f01c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794397"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="4eda9-102">ICorDebugHeapValue::IsValid (Método)</span><span class="sxs-lookup"><span data-stu-id="4eda9-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="4eda9-103">Obtiene un valor que indica si el objeto representado por este ICorDebugHeapValue es válido.</span><span class="sxs-lookup"><span data-stu-id="4eda9-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="4eda9-104">Este método está en desuso en la versión .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="4eda9-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4eda9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4eda9-105">Syntax</span></span>  
  
```cpp  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4eda9-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="4eda9-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="4eda9-107">enuncia Un puntero a un valor booleano que indica si este valor en el montón es válido.</span><span class="sxs-lookup"><span data-stu-id="4eda9-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4eda9-108">Notas</span><span class="sxs-lookup"><span data-stu-id="4eda9-108">Remarks</span></span>  
 <span data-ttu-id="4eda9-109">El valor no es válido si lo ha reclamado el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="4eda9-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="4eda9-110">Este método está en desuso.</span><span class="sxs-lookup"><span data-stu-id="4eda9-110">This method has been deprecated.</span></span> <span data-ttu-id="4eda9-111">En el .NET Framework 2,0, todos los valores son válidos hasta que se llama a [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) , momento en el que se invalidan los valores.</span><span class="sxs-lookup"><span data-stu-id="4eda9-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4eda9-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="4eda9-112">Requirements</span></span>  
 <span data-ttu-id="4eda9-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4eda9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4eda9-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4eda9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4eda9-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4eda9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4eda9-116">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4eda9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
