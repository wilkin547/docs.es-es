---
title: ICorDebugClass2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugClass2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2
helpviewer_keywords:
- ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type:
- apiref
ms.openlocfilehash: cb2ab28824d209dd1eed627600e30e9ddb0d7c7a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125720"
---
# <a name="icordebugclass2-interface"></a><span data-ttu-id="aaf45-102">ICorDebugClass2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aaf45-102">ICorDebugClass2 Interface</span></span>

<span data-ttu-id="aaf45-103">Representa una clase genérica o una clase con un parámetro de método de tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="aaf45-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="aaf45-104">Esta interfaz extiende [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span><span class="sxs-lookup"><span data-stu-id="aaf45-104">This interface extends [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aaf45-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="aaf45-105">Methods</span></span>  
  
|<span data-ttu-id="aaf45-106">Método</span><span class="sxs-lookup"><span data-stu-id="aaf45-106">Method</span></span>|<span data-ttu-id="aaf45-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="aaf45-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aaf45-108">GetParameterizedType (método)</span><span class="sxs-lookup"><span data-stu-id="aaf45-108">GetParameterizedType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="aaf45-109">Obtiene la declaración de tipos para esta clase.</span><span class="sxs-lookup"><span data-stu-id="aaf45-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="aaf45-110">SetJMCStatus (método)</span><span class="sxs-lookup"><span data-stu-id="aaf45-110">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="aaf45-111">Para cada método de esta clase, establece un valor que indica si el método es código definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="aaf45-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aaf45-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aaf45-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aaf45-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="aaf45-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aaf45-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aaf45-114">Requirements</span></span>  
 <span data-ttu-id="aaf45-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aaf45-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aaf45-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aaf45-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aaf45-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aaf45-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aaf45-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aaf45-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaf45-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="aaf45-119">See also</span></span>

- [<span data-ttu-id="aaf45-120">ICorDebugClass (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aaf45-120">ICorDebugClass Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)
- [<span data-ttu-id="aaf45-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="aaf45-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
