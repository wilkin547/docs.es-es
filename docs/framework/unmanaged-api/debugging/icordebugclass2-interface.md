---
title: ICorDebugClass2 Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass2
helpviewer_keywords: ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5053ea14ac7a8af33319bbbb289db01dbbc86169
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugclass2-interface1"></a><span data-ttu-id="8d1b6-102">ICorDebugClass2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="8d1b6-102">ICorDebugClass2 Interface1</span></span>
<span data-ttu-id="8d1b6-103">Representa una clase genérica o una clase con un parámetro de método de tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="8d1b6-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="8d1b6-104">Esta interfaz extiende [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span><span class="sxs-lookup"><span data-stu-id="8d1b6-104">This interface extends [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8d1b6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="8d1b6-105">Methods</span></span>  
  
|<span data-ttu-id="8d1b6-106">Método</span><span class="sxs-lookup"><span data-stu-id="8d1b6-106">Method</span></span>|<span data-ttu-id="8d1b6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d1b6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8d1b6-108">GetParameterizedType (método)</span><span class="sxs-lookup"><span data-stu-id="8d1b6-108">GetParameterizedType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="8d1b6-109">Obtiene la declaración de tipo para esta clase.</span><span class="sxs-lookup"><span data-stu-id="8d1b6-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="8d1b6-110">SetJMCStatus (método)</span><span class="sxs-lookup"><span data-stu-id="8d1b6-110">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="8d1b6-111">Para cada método de esta clase, establece un valor que indica si el método es código definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="8d1b6-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d1b6-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8d1b6-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d1b6-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="8d1b6-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d1b6-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d1b6-114">Requirements</span></span>  
 <span data-ttu-id="8d1b6-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d1b6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d1b6-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d1b6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d1b6-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d1b6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d1b6-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d1b6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d1b6-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d1b6-119">See Also</span></span>  
 [<span data-ttu-id="8d1b6-120">ICorDebugClass (interfaz1)</span><span class="sxs-lookup"><span data-stu-id="8d1b6-120">ICorDebugClass Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)  
 [<span data-ttu-id="8d1b6-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="8d1b6-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
