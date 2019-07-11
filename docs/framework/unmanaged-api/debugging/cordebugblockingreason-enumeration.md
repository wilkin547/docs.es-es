---
title: CorDebugBlockingReason (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugBlockingReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingReason
helpviewer_keywords:
- CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ea71439c9a6c494c218a7cfc18508f4f8173b03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740387"
---
# <a name="cordebugblockingreason-enumeration"></a><span data-ttu-id="dd87e-102">CorDebugBlockingReason (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="dd87e-102">CorDebugBlockingReason Enumeration</span></span>
<span data-ttu-id="dd87e-103">Especifica los motivos por lo que un subproceso se puede bloquear en un objeto determinado.</span><span class="sxs-lookup"><span data-stu-id="dd87e-103">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd87e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd87e-104">Syntax</span></span>  
  
```cpp  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a><span data-ttu-id="dd87e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="dd87e-105">Members</span></span>  
  
|<span data-ttu-id="dd87e-106">Member</span><span class="sxs-lookup"><span data-stu-id="dd87e-106">Member</span></span>|<span data-ttu-id="dd87e-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="dd87e-107">Description</span></span>|  
|------------|-----------------|  
|`BLOCKING_NONE`|<span data-ttu-id="dd87e-108">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="dd87e-108">Internal use only.</span></span>|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|<span data-ttu-id="dd87e-109">Un subproceso está intentando adquirir la sección crítica que está asociada con el bloqueo de monitor en un objeto.</span><span class="sxs-lookup"><span data-stu-id="dd87e-109">A thread is trying to acquire the critical section that is associated with the monitor lock on an object.</span></span> <span data-ttu-id="dd87e-110">Normalmente, esto se produce cuando se llama a uno de los <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> o <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> métodos.</span><span class="sxs-lookup"><span data-stu-id="dd87e-110">Typically, this occurs when you call one of the <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> or <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> methods.</span></span>|  
|`BLOCKING_MONITOR_EVENT`|<span data-ttu-id="dd87e-111">Un subproceso está esperando el evento que está asociado a un bloqueo de monitor para un objeto.</span><span class="sxs-lookup"><span data-stu-id="dd87e-111">A thread is waiting on the event that is associated with a monitor lock for an object.</span></span> <span data-ttu-id="dd87e-112">Normalmente, esto se produce cuando se llama a uno de los <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` métodos.</span><span class="sxs-lookup"><span data-stu-id="dd87e-112">Typically, this occurs when you call one of the <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` methods.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd87e-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dd87e-113">Remarks</span></span>  
 <span data-ttu-id="dd87e-114">Cuando el `BLOCKING_MONITOR_CRITICAL_SECTION` o `BLOCKING_MONITOR_EVENT` miembro se utiliza en un [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) estructura, el `pBlockingObject` miembro de la estructura que señala a una interfaz "ICorDebugValue" que representa el objeto que se está entrando en .</span><span class="sxs-lookup"><span data-stu-id="dd87e-114">When the `BLOCKING_MONITOR_CRITICAL_SECTION` or `BLOCKING_MONITOR_EVENT` member is used in a [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure, the `pBlockingObject` member of the structure points to an "ICorDebugValue" interface that represents the object that is being entered.</span></span> <span data-ttu-id="dd87e-115">También se garantiza para implementar la [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="dd87e-115">It is also guaranteed to implement the [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd87e-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd87e-116">Requirements</span></span>  
 <span data-ttu-id="dd87e-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd87e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd87e-118">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd87e-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd87e-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd87e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd87e-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd87e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd87e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd87e-121">See also</span></span>

- [<span data-ttu-id="dd87e-122">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="dd87e-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="dd87e-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="dd87e-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
