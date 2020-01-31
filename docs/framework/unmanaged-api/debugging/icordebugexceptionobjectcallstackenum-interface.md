---
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
ms.openlocfilehash: 9d98bccdfb83cec547b185693c28f25017d3225f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782804"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="5018f-102">ICorDebugExceptionObjectCallStackEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5018f-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>
<span data-ttu-id="5018f-103">Proporciona un enumerador para la información de la pila de llamadas que está incrustada en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="5018f-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="5018f-104">Esta interfaz es una subclase de la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="5018f-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5018f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="5018f-105">Methods</span></span>  
  
|<span data-ttu-id="5018f-106">Método</span><span class="sxs-lookup"><span data-stu-id="5018f-106">Method</span></span>|<span data-ttu-id="5018f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5018f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5018f-108">ICorDebugExceptionObjectCallStackEnum::Next</span><span class="sxs-lookup"><span data-stu-id="5018f-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="5018f-109">Obtiene un número especificado de objetos [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) que contienen información sobre la pila de llamadas de un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="5018f-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5018f-110">Notas</span><span class="sxs-lookup"><span data-stu-id="5018f-110">Remarks</span></span>  
 <span data-ttu-id="5018f-111">La interfaz de `ICorDebugExceptionObjectCallStackEnum` implementa la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="5018f-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="5018f-112">Una instancia de `ICorDebugExceptionObjectCallStackEnum` se rellena con objetos [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) llamando al método [Icordebugexceptionobjectvalue (:: enumerateexceptioncallstack (](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5018f-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="5018f-113">Los elementos de la pila de llamadas de la colección se pueden enumerar llamando al método [icordebugexceptionobjectcallstackenum (:: Next](icordebugexceptionobjectcallstackenum-next-method.md)</span><span class="sxs-lookup"><span data-stu-id="5018f-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5018f-114">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="5018f-114">Requirements</span></span>  
 <span data-ttu-id="5018f-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5018f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5018f-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5018f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5018f-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5018f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5018f-118">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5018f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5018f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5018f-119">See also</span></span>

- [<span data-ttu-id="5018f-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="5018f-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5018f-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="5018f-121">Debugging</span></span>](index.md)
