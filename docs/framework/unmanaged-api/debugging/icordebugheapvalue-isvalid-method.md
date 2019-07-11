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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ca3b86e90dcb76c1fece44cf2c5ed68e073d8e7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757221"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="3bfbe-102">ICorDebugHeapValue::IsValid (Método)</span><span class="sxs-lookup"><span data-stu-id="3bfbe-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="3bfbe-103">Obtiene un valor que indica si el objeto representado por ICorDebugHeapValue es válido.</span><span class="sxs-lookup"><span data-stu-id="3bfbe-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="3bfbe-104">Este método está desusado en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="3bfbe-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bfbe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3bfbe-105">Syntax</span></span>  
  
```cpp  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bfbe-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3bfbe-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="3bfbe-107">[out] Un puntero a un valor booleano que indica si este valor en el montón es válido.</span><span class="sxs-lookup"><span data-stu-id="3bfbe-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3bfbe-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3bfbe-108">Remarks</span></span>  
 <span data-ttu-id="3bfbe-109">El valor no es válido si ha sido reclamado por el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3bfbe-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="3bfbe-110">Este método está en desuso.</span><span class="sxs-lookup"><span data-stu-id="3bfbe-110">This method has been deprecated.</span></span> <span data-ttu-id="3bfbe-111">En .NET Framework 2.0, todos los valores son válidos hasta [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) se denomina, en qué momento se invalidan los los valores.</span><span class="sxs-lookup"><span data-stu-id="3bfbe-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bfbe-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3bfbe-112">Requirements</span></span>  
 <span data-ttu-id="3bfbe-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bfbe-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bfbe-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3bfbe-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3bfbe-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3bfbe-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3bfbe-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bfbe-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
