---
title: ICorDebugGenericValue Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGenericValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGenericValue
helpviewer_keywords: ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d6c6fb4893edf0bcda9d6f7ddbeea7054f5b4fd5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuggenericvalue-interface1"></a><span data-ttu-id="4277a-102">ICorDebugGenericValue Interfaz1</span><span class="sxs-lookup"><span data-stu-id="4277a-102">ICorDebugGenericValue Interface1</span></span>
<span data-ttu-id="4277a-103">Una subclase de "ICorDebugValue" que se aplica a todos los valores.</span><span class="sxs-lookup"><span data-stu-id="4277a-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="4277a-104">Esta interfaz proporciona métodos Get y Set para el valor.</span><span class="sxs-lookup"><span data-stu-id="4277a-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4277a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="4277a-105">Methods</span></span>  
  
|<span data-ttu-id="4277a-106">Método</span><span class="sxs-lookup"><span data-stu-id="4277a-106">Method</span></span>|<span data-ttu-id="4277a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4277a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4277a-108">GetValue (método)</span><span class="sxs-lookup"><span data-stu-id="4277a-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="4277a-109">Copia el valor en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="4277a-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="4277a-110">SetValue (método)</span><span class="sxs-lookup"><span data-stu-id="4277a-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="4277a-111">Copia un nuevo valor del búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="4277a-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4277a-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4277a-112">Remarks</span></span>  
 <span data-ttu-id="4277a-113">`ICorDebugGenericValue`es una interfaz secundaria porque es no son utilizables de forma remota.</span><span class="sxs-lookup"><span data-stu-id="4277a-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="4277a-114">Para los tipos de referencia, el valor es la referencia en lugar de con el contenido de la referencia.</span><span class="sxs-lookup"><span data-stu-id="4277a-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="4277a-115">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="4277a-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4277a-116">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="4277a-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4277a-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4277a-117">Requirements</span></span>  
 <span data-ttu-id="4277a-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4277a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4277a-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4277a-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4277a-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4277a-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4277a-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4277a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4277a-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="4277a-122">See Also</span></span>  
    
 [<span data-ttu-id="4277a-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4277a-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
