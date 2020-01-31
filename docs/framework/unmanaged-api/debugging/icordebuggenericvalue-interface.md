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
ms.openlocfilehash: e60d4b128bf03ff81863e0c95815b2c204807583
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794467"
---
# <a name="icordebuggenericvalue-interface"></a><span data-ttu-id="e2ff5-102">Interfaz ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="e2ff5-102">ICorDebugGenericValue Interface</span></span>

<span data-ttu-id="e2ff5-103">Una subclase de "ICorDebugValue" que se aplica a todos los valores.</span><span class="sxs-lookup"><span data-stu-id="e2ff5-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="e2ff5-104">Esta interfaz proporciona métodos Get y Set para el valor.</span><span class="sxs-lookup"><span data-stu-id="e2ff5-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e2ff5-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e2ff5-105">Methods</span></span>  
  
|<span data-ttu-id="e2ff5-106">Método</span><span class="sxs-lookup"><span data-stu-id="e2ff5-106">Method</span></span>|<span data-ttu-id="e2ff5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2ff5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e2ff5-108">GetValue (método)</span><span class="sxs-lookup"><span data-stu-id="e2ff5-108">GetValue Method</span></span>](icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="e2ff5-109">Copia el valor en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="e2ff5-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="e2ff5-110">SetValue (método)</span><span class="sxs-lookup"><span data-stu-id="e2ff5-110">SetValue Method</span></span>](icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="e2ff5-111">Copia un nuevo valor del búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="e2ff5-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2ff5-112">Notas</span><span class="sxs-lookup"><span data-stu-id="e2ff5-112">Remarks</span></span>  
 <span data-ttu-id="e2ff5-113">`ICorDebugGenericValue` es una subinterfaz porque no es remota.</span><span class="sxs-lookup"><span data-stu-id="e2ff5-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="e2ff5-114">En el caso de los tipos de referencia, el valor es la referencia en lugar del contenido de la referencia.</span><span class="sxs-lookup"><span data-stu-id="e2ff5-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="e2ff5-115">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="e2ff5-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2ff5-116">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="e2ff5-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2ff5-117">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="e2ff5-117">Requirements</span></span>  
 <span data-ttu-id="e2ff5-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2ff5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2ff5-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2ff5-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2ff5-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2ff5-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2ff5-121">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2ff5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2ff5-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2ff5-122">See also</span></span>

- [<span data-ttu-id="e2ff5-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e2ff5-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
