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
ms.openlocfilehash: ddd03d70656ad52fd9d577beedc60b51c7b305d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672856"
---
# <a name="cordebugblockingreason-enumeration"></a><span data-ttu-id="e3935-102">CorDebugBlockingReason (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e3935-102">CorDebugBlockingReason Enumeration</span></span>

<span data-ttu-id="e3935-103">Especifica los motivos por lo que un subproceso se puede bloquear en un objeto determinado.</span><span class="sxs-lookup"><span data-stu-id="e3935-103">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3935-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3935-104">Syntax</span></span>  
  
```cpp  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a><span data-ttu-id="e3935-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e3935-105">Members</span></span>  
  
|<span data-ttu-id="e3935-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e3935-106">Member</span></span>|<span data-ttu-id="e3935-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3935-107">Description</span></span>|  
|------------|-----------------|  
|`BLOCKING_NONE`|<span data-ttu-id="e3935-108">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e3935-108">Internal use only.</span></span>|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|<span data-ttu-id="e3935-109">Un subproceso está intentando adquirir la sección crítica asociada al bloqueo de monitor en un objeto.</span><span class="sxs-lookup"><span data-stu-id="e3935-109">A thread is trying to acquire the critical section that is associated with the monitor lock on an object.</span></span> <span data-ttu-id="e3935-110">Normalmente, esto sucede cuando se llama a uno de <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> los <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> métodos o.</span><span class="sxs-lookup"><span data-stu-id="e3935-110">Typically, this occurs when you call one of the <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> or <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> methods.</span></span>|  
|`BLOCKING_MONITOR_EVENT`|<span data-ttu-id="e3935-111">Un subproceso está esperando en el evento que está asociado a un bloqueo de monitor para un objeto.</span><span class="sxs-lookup"><span data-stu-id="e3935-111">A thread is waiting on the event that is associated with a monitor lock for an object.</span></span> <span data-ttu-id="e3935-112">Normalmente, esto sucede cuando se llama a uno de los <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` métodos.</span><span class="sxs-lookup"><span data-stu-id="e3935-112">Typically, this occurs when you call one of the <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` methods.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3935-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e3935-113">Remarks</span></span>  

 <span data-ttu-id="e3935-114">Cuando el `BLOCKING_MONITOR_CRITICAL_SECTION` `BLOCKING_MONITOR_EVENT` miembro o se usa en una estructura [CorDebugBlockingObject](cordebugblockingobject-structure.md) , el `pBlockingObject` miembro de la estructura apunta a una interfaz "ICorDebugValue" que representa el objeto que se va a especificar.</span><span class="sxs-lookup"><span data-stu-id="e3935-114">When the `BLOCKING_MONITOR_CRITICAL_SECTION` or `BLOCKING_MONITOR_EVENT` member is used in a [CorDebugBlockingObject](cordebugblockingobject-structure.md) structure, the `pBlockingObject` member of the structure points to an "ICorDebugValue" interface that represents the object that is being entered.</span></span> <span data-ttu-id="e3935-115">También se garantiza la implementación de la interfaz [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e3935-115">It is also guaranteed to implement the [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3935-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e3935-116">Requirements</span></span>  

 <span data-ttu-id="e3935-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3935-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3935-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3935-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3935-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3935-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3935-120">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3935-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3935-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e3935-121">See also</span></span>

- [<span data-ttu-id="e3935-122">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="e3935-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="e3935-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="e3935-123">Debugging</span></span>](index.md)
