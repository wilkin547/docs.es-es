---
title: CorDebugBlockingObject (Estructura)
ms.date: 03/30/2017
api_name:
- CorDebugBlockingObject Structure
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingObject
helpviewer_keywords:
- CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83dac3b9b2ac396cdef19695fcce0f7e20485a50
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740399"
---
# <a name="cordebugblockingobject-structure"></a><span data-ttu-id="75e66-102">CorDebugBlockingObject (Estructura)</span><span class="sxs-lookup"><span data-stu-id="75e66-102">CorDebugBlockingObject Structure</span></span>
<span data-ttu-id="75e66-103">Define un objeto que está bloqueando un subproceso y el motivo específico que el subproceso está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="75e66-103">Defines an object that is blocking a thread and the specific reason that the thread is blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75e66-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75e66-104">Syntax</span></span>  
  
```cpp  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a><span data-ttu-id="75e66-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="75e66-105">Members</span></span>  
  
|<span data-ttu-id="75e66-106">Member</span><span class="sxs-lookup"><span data-stu-id="75e66-106">Member</span></span>|<span data-ttu-id="75e66-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="75e66-107">Description</span></span>|  
|------------|-----------------|  
|`pBlockingObject`|<span data-ttu-id="75e66-108">El objeto en el que está bloqueando el subproceso.</span><span class="sxs-lookup"><span data-stu-id="75e66-108">The object on which the thread is blocking.</span></span> <span data-ttu-id="75e66-109">Este objeto es válido solo durante el tiempo que dure el estado sincronizado actual.</span><span class="sxs-lookup"><span data-stu-id="75e66-109">This object is valid only for the duration of the current synchronized state.</span></span> <span data-ttu-id="75e66-110">Si dos subprocesos bloqueados en el mismo objeto dentro del mismo estado sincronizado, es posible que espera el [GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) método para devolver el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="75e66-110">If two threads are blocking on the same object within the same synchronized state, you may expect the [ICorDebugValue::GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) method to return the same value.</span></span> <span data-ttu-id="75e66-111">Sin embargo, las interfaces pueden o no sea el equivalente de puntero.</span><span class="sxs-lookup"><span data-stu-id="75e66-111">However, the interfaces may or may not be pointer equivalent.</span></span>|  
|`dwTimeout`|<span data-ttu-id="75e66-112">El número de milisegundos antes de la operación de bloqueo superará el tiempo de espera o el valor infinito, lo que indica que superará el tiempo de espera. El valor de tiempo de espera especifica la longitud total de tiempo para la operación de bloqueo, no el tiempo que queda todavía.</span><span class="sxs-lookup"><span data-stu-id="75e66-112">The number of milliseconds before the blocking operation will time out, or the value INFINITE, which indicates that it will not time out. The time-out value specifies the total length of time for the blocking operation, not the time that is still remaining.</span></span>|  
|`blockingReason`|<span data-ttu-id="75e66-113">El motivo de que el subproceso está bloqueado en este objeto.</span><span class="sxs-lookup"><span data-stu-id="75e66-113">The reason that the thread is blocked on this object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75e66-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="75e66-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75e66-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75e66-115">Requirements</span></span>  
 <span data-ttu-id="75e66-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75e66-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75e66-117">**Encabezado**: CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="75e66-117">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="75e66-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75e66-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75e66-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75e66-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75e66-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="75e66-120">See also</span></span>

- [<span data-ttu-id="75e66-121">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="75e66-121">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="75e66-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="75e66-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
