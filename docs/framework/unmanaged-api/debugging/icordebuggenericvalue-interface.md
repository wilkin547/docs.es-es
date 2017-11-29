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
ms.openlocfilehash: 61c159e30efb33dca4043e5b5306c9544acd614a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebuggenericvalue-interface1"></a><span data-ttu-id="8bf80-102">ICorDebugGenericValue Interfaz1</span><span class="sxs-lookup"><span data-stu-id="8bf80-102">ICorDebugGenericValue Interface1</span></span>
<span data-ttu-id="8bf80-103">Una subclase de "ICorDebugValue" que se aplica a todos los valores.</span><span class="sxs-lookup"><span data-stu-id="8bf80-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="8bf80-104">Esta interfaz proporciona métodos Get y Set para el valor.</span><span class="sxs-lookup"><span data-stu-id="8bf80-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8bf80-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="8bf80-105">Methods</span></span>  
  
|<span data-ttu-id="8bf80-106">Método</span><span class="sxs-lookup"><span data-stu-id="8bf80-106">Method</span></span>|<span data-ttu-id="8bf80-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8bf80-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8bf80-108">GetValue (método)</span><span class="sxs-lookup"><span data-stu-id="8bf80-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="8bf80-109">Copia el valor en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="8bf80-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="8bf80-110">SetValue (método)</span><span class="sxs-lookup"><span data-stu-id="8bf80-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="8bf80-111">Copia un nuevo valor del búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="8bf80-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bf80-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8bf80-112">Remarks</span></span>  
 <span data-ttu-id="8bf80-113">`ICorDebugGenericValue`es una interfaz secundaria porque es no son utilizables de forma remota.</span><span class="sxs-lookup"><span data-stu-id="8bf80-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="8bf80-114">Para los tipos de referencia, el valor es la referencia en lugar de con el contenido de la referencia.</span><span class="sxs-lookup"><span data-stu-id="8bf80-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="8bf80-115">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="8bf80-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8bf80-116">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="8bf80-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bf80-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8bf80-117">Requirements</span></span>  
 <span data-ttu-id="8bf80-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bf80-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bf80-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8bf80-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8bf80-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bf80-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bf80-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bf80-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bf80-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bf80-122">See Also</span></span>  
    
 [<span data-ttu-id="8bf80-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="8bf80-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
