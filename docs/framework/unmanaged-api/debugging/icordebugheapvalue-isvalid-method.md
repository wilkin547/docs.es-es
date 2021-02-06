---
description: 'Más información acerca de: ICorDebugHeapValue:: IsValid (método)'
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
ms.openlocfilehash: 27eca844170b31934cd32dad5cf5fccc0b0e324e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660796"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="9c08b-103">ICorDebugHeapValue::IsValid (Método)</span><span class="sxs-lookup"><span data-stu-id="9c08b-103">ICorDebugHeapValue::IsValid Method</span></span>

<span data-ttu-id="9c08b-104">Obtiene un valor que indica si el objeto representado por este ICorDebugHeapValue es válido.</span><span class="sxs-lookup"><span data-stu-id="9c08b-104">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="9c08b-105">Este método está en desuso en la versión .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="9c08b-105">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c08b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c08b-106">Syntax</span></span>  
  
```cpp  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c08b-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9c08b-107">Parameters</span></span>  

 `pbValid`  
 <span data-ttu-id="9c08b-108">enuncia Un puntero a un valor booleano que indica si este valor en el montón es válido.</span><span class="sxs-lookup"><span data-stu-id="9c08b-108">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c08b-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9c08b-109">Remarks</span></span>  

 <span data-ttu-id="9c08b-110">El valor no es válido si lo ha reclamado el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="9c08b-110">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="9c08b-111">Este método está en desuso.</span><span class="sxs-lookup"><span data-stu-id="9c08b-111">This method has been deprecated.</span></span> <span data-ttu-id="9c08b-112">En el .NET Framework 2,0, todos los valores son válidos hasta que se llama a [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) , momento en el que se invalidan los valores.</span><span class="sxs-lookup"><span data-stu-id="9c08b-112">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c08b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c08b-113">Requirements</span></span>  

 <span data-ttu-id="9c08b-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c08b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c08b-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c08b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c08b-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c08b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c08b-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c08b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
