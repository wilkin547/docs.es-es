---
description: 'Más información acerca de: interfaz ICorDebugGenericValue'
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
ms.openlocfilehash: 7c81855849d7b72bc509d20072b96bb64f5d395a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692042"
---
# <a name="icordebuggenericvalue-interface"></a><span data-ttu-id="a9db3-103">Interfaz ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="a9db3-103">ICorDebugGenericValue Interface</span></span>

<span data-ttu-id="a9db3-104">Una subclase de "ICorDebugValue" que se aplica a todos los valores.</span><span class="sxs-lookup"><span data-stu-id="a9db3-104">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="a9db3-105">Esta interfaz proporciona métodos Get y Set para el valor.</span><span class="sxs-lookup"><span data-stu-id="a9db3-105">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a9db3-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="a9db3-106">Methods</span></span>  
  
|<span data-ttu-id="a9db3-107">Método</span><span class="sxs-lookup"><span data-stu-id="a9db3-107">Method</span></span>|<span data-ttu-id="a9db3-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9db3-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a9db3-109">Método GetValue</span><span class="sxs-lookup"><span data-stu-id="a9db3-109">GetValue Method</span></span>](icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="a9db3-110">Copia el valor en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="a9db3-110">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="a9db3-111">Método SetValue</span><span class="sxs-lookup"><span data-stu-id="a9db3-111">SetValue Method</span></span>](icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="a9db3-112">Copia un nuevo valor del búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="a9db3-112">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9db3-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a9db3-113">Remarks</span></span>  

 <span data-ttu-id="a9db3-114">`ICorDebugGenericValue` es una subinterfaz porque no es remota.</span><span class="sxs-lookup"><span data-stu-id="a9db3-114">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="a9db3-115">En el caso de los tipos de referencia, el valor es la referencia en lugar del contenido de la referencia.</span><span class="sxs-lookup"><span data-stu-id="a9db3-115">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="a9db3-116">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="a9db3-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a9db3-117">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="a9db3-117">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9db3-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9db3-118">Requirements</span></span>  

 <span data-ttu-id="a9db3-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9db3-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9db3-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9db3-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9db3-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9db3-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9db3-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9db3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9db3-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9db3-123">See also</span></span>

- [<span data-ttu-id="a9db3-124">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a9db3-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
