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
ms.openlocfilehash: 1c45faecdb8b95af8d9e981962151c2c5d071a4f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731896"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="a3857-102">ICorDebugExceptionObjectCallStackEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3857-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>

<span data-ttu-id="a3857-103">Proporciona un enumerador para la información de la pila de llamadas que está incrustada en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="a3857-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="a3857-104">Esta interfaz es una subclase de la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="a3857-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a3857-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a3857-105">Methods</span></span>  
  
|<span data-ttu-id="a3857-106">Método</span><span class="sxs-lookup"><span data-stu-id="a3857-106">Method</span></span>|<span data-ttu-id="a3857-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3857-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a3857-108">Icordebugexceptionobjectcallstackenum (:: Next</span><span class="sxs-lookup"><span data-stu-id="a3857-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="a3857-109">Obtiene un número especificado de objetos [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) que contienen información sobre la pila de llamadas de un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="a3857-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3857-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a3857-110">Remarks</span></span>  

 <span data-ttu-id="a3857-111">La `ICorDebugExceptionObjectCallStackEnum` interfaz implementa la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="a3857-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="a3857-112">Una `ICorDebugExceptionObjectCallStackEnum` instancia se rellena con objetos [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) llamando al método [icordebugexceptionobjectvalue (:: enumerateexceptioncallstack (](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a3857-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="a3857-113">Los elementos de la pila de llamadas de la colección se pueden enumerar llamando al método [icordebugexceptionobjectcallstackenum (:: Next](icordebugexceptionobjectcallstackenum-next-method.md)</span><span class="sxs-lookup"><span data-stu-id="a3857-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3857-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3857-114">Requirements</span></span>  

 <span data-ttu-id="a3857-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3857-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3857-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3857-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3857-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3857-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3857-118">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3857-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3857-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3857-119">See also</span></span>

- [<span data-ttu-id="a3857-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a3857-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a3857-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="a3857-121">Debugging</span></span>](index.md)
