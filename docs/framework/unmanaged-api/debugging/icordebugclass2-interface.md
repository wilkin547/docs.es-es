---
title: Interfaz ICorDebugClass2
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 015085cff23028814937dfef9aea19af7438b4f5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750610"
---
# <a name="icordebugclass2-interface"></a><span data-ttu-id="c3bc3-102">Interfaz ICorDebugClass2</span><span class="sxs-lookup"><span data-stu-id="c3bc3-102">ICorDebugClass2 Interface</span></span>

<span data-ttu-id="c3bc3-103">Representa una clase genérica o una clase con un parámetro de método de tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="c3bc3-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="c3bc3-104">Esta interfaz extiende [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span><span class="sxs-lookup"><span data-stu-id="c3bc3-104">This interface extends [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c3bc3-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="c3bc3-105">Methods</span></span>  
  
|<span data-ttu-id="c3bc3-106">Método</span><span class="sxs-lookup"><span data-stu-id="c3bc3-106">Method</span></span>|<span data-ttu-id="c3bc3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3bc3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c3bc3-108">GetParameterizedType (método)</span><span class="sxs-lookup"><span data-stu-id="c3bc3-108">GetParameterizedType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="c3bc3-109">Obtiene la declaración de tipos para esta clase.</span><span class="sxs-lookup"><span data-stu-id="c3bc3-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="c3bc3-110">SetJMCStatus (método)</span><span class="sxs-lookup"><span data-stu-id="c3bc3-110">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="c3bc3-111">Para cada método de esta clase, establece un valor que indica si el método es código definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c3bc3-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3bc3-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c3bc3-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3bc3-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="c3bc3-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3bc3-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3bc3-114">Requirements</span></span>  
 <span data-ttu-id="c3bc3-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3bc3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3bc3-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3bc3-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3bc3-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3bc3-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3bc3-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3bc3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3bc3-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3bc3-119">See also</span></span>

- [<span data-ttu-id="c3bc3-120">ICorDebugClass (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c3bc3-120">ICorDebugClass Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)
- [<span data-ttu-id="c3bc3-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c3bc3-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
