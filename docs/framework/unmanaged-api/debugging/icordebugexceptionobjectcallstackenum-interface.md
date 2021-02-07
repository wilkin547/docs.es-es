---
description: 'Más información acerca de: interfaz Icordebugexceptionobjectcallstackenum ('
title: ICorDebugExceptionObjectCallStackEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 39dffa18-c71b-48c4-b11d-e814631ab1e9
topic_type:
- apiref
ms.openlocfilehash: c72f4299bf3ebc5de2d2ed196801d93ff5fe4356
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693361"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="88450-103">ICorDebugExceptionObjectCallStackEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="88450-103">ICorDebugExceptionObjectCallStackEnum Interface</span></span>

<span data-ttu-id="88450-104">Proporciona un enumerador para la información de la pila de llamadas que está incrustada en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="88450-104">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="88450-105">Esta interfaz es una subclase de la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="88450-105">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="88450-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="88450-106">Methods</span></span>  
  
|<span data-ttu-id="88450-107">Método</span><span class="sxs-lookup"><span data-stu-id="88450-107">Method</span></span>|<span data-ttu-id="88450-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="88450-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="88450-109">Icordebugexceptionobjectcallstackenum (:: Next</span><span class="sxs-lookup"><span data-stu-id="88450-109">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="88450-110">Obtiene un número especificado de objetos [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) que contienen información sobre la pila de llamadas de un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="88450-110">Gets a specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88450-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="88450-111">Remarks</span></span>  

 <span data-ttu-id="88450-112">La `ICorDebugExceptionObjectCallStackEnum` interfaz implementa la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="88450-112">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="88450-113">Una `ICorDebugExceptionObjectCallStackEnum` instancia se rellena con objetos [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) llamando al método [icordebugexceptionobjectvalue (:: enumerateexceptioncallstack (](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) .</span><span class="sxs-lookup"><span data-stu-id="88450-113">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="88450-114">Los elementos de la pila de llamadas de la colección se pueden enumerar llamando al método [icordebugexceptionobjectcallstackenum (:: Next](icordebugexceptionobjectcallstackenum-next-method.md)</span><span class="sxs-lookup"><span data-stu-id="88450-114">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88450-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88450-115">Requirements</span></span>  

 <span data-ttu-id="88450-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88450-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88450-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="88450-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="88450-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88450-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88450-119">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88450-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88450-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="88450-120">See also</span></span>

- [<span data-ttu-id="88450-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="88450-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="88450-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="88450-122">Debugging</span></span>](index.md)
