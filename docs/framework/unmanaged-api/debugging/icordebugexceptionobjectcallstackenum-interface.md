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
ms.openlocfilehash: e6dd951b0f432d455d95bb60f4c42df64d5bee24
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975997"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="a149a-102">ICorDebugExceptionObjectCallStackEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a149a-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>
<span data-ttu-id="a149a-103">Proporciona un enumerador para la información de la pila de llamadas que está incrustada en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="a149a-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="a149a-104">Esta interfaz es una subclase de la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="a149a-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a149a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a149a-105">Methods</span></span>  
  
|<span data-ttu-id="a149a-106">Método</span><span class="sxs-lookup"><span data-stu-id="a149a-106">Method</span></span>|<span data-ttu-id="a149a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a149a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a149a-108">Icordebugexceptionobjectcallstackenum (:: Next</span><span class="sxs-lookup"><span data-stu-id="a149a-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="a149a-109">Obtiene un número especificado de objetos [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) que contienen información sobre la pila de llamadas de un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="a149a-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a149a-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a149a-110">Remarks</span></span>  
 <span data-ttu-id="a149a-111">La `ICorDebugExceptionObjectCallStackEnum` interfaz implementa la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="a149a-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="a149a-112">Una `ICorDebugExceptionObjectCallStackEnum` instancia se rellena con objetos [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) llamando al método [icordebugexceptionobjectvalue (:: enumerateexceptioncallstack (](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a149a-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="a149a-113">Los elementos de la pila de llamadas de la colección se pueden enumerar llamando al método [icordebugexceptionobjectcallstackenum (:: Next](icordebugexceptionobjectcallstackenum-next-method.md)</span><span class="sxs-lookup"><span data-stu-id="a149a-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a149a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a149a-114">Requirements</span></span>  
 <span data-ttu-id="a149a-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a149a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a149a-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a149a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a149a-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a149a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a149a-118">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a149a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a149a-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a149a-119">See also</span></span>

- [<span data-ttu-id="a149a-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a149a-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a149a-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="a149a-121">Debugging</span></span>](index.md)
