---
title: Interfaz ICorDebugGenericValue
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
ms.openlocfilehash: 7c5359ddf2c021f77ad1ea0a8579316c3c773fd5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209791"
---
# <a name="icordebuggenericvalue-interface"></a><span data-ttu-id="8000b-102">Interfaz ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="8000b-102">ICorDebugGenericValue Interface</span></span>

<span data-ttu-id="8000b-103">Una subclase de "ICorDebugValue" que se aplica a todos los valores.</span><span class="sxs-lookup"><span data-stu-id="8000b-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="8000b-104">Esta interfaz proporciona métodos Get y Set para el valor.</span><span class="sxs-lookup"><span data-stu-id="8000b-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8000b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="8000b-105">Methods</span></span>  
  
|<span data-ttu-id="8000b-106">Método</span><span class="sxs-lookup"><span data-stu-id="8000b-106">Method</span></span>|<span data-ttu-id="8000b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8000b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8000b-108">Método GetValue</span><span class="sxs-lookup"><span data-stu-id="8000b-108">GetValue Method</span></span>](icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="8000b-109">Copia el valor en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="8000b-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="8000b-110">Método SetValue</span><span class="sxs-lookup"><span data-stu-id="8000b-110">SetValue Method</span></span>](icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="8000b-111">Copia un nuevo valor del búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="8000b-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8000b-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8000b-112">Remarks</span></span>  
 <span data-ttu-id="8000b-113">`ICorDebugGenericValue`es una subinterfaz porque no es remota.</span><span class="sxs-lookup"><span data-stu-id="8000b-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="8000b-114">En el caso de los tipos de referencia, el valor es la referencia en lugar del contenido de la referencia.</span><span class="sxs-lookup"><span data-stu-id="8000b-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="8000b-115">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="8000b-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8000b-116">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="8000b-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8000b-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8000b-117">Requirements</span></span>  
 <span data-ttu-id="8000b-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8000b-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8000b-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8000b-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8000b-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8000b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8000b-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8000b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8000b-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8000b-122">See also</span></span>

- [<span data-ttu-id="8000b-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="8000b-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
