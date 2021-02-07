---
description: 'Más información sobre: enumeración CorDebugBlockingReason ('
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
ms.openlocfilehash: c2d9c805549d046fe40ab5ea00f30e2fd0a680a3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747117"
---
# <a name="cordebugblockingreason-enumeration"></a><span data-ttu-id="abcba-103">CorDebugBlockingReason (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="abcba-103">CorDebugBlockingReason Enumeration</span></span>

<span data-ttu-id="abcba-104">Especifica los motivos por lo que un subproceso se puede bloquear en un objeto determinado.</span><span class="sxs-lookup"><span data-stu-id="abcba-104">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abcba-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="abcba-105">Syntax</span></span>  
  
```cpp  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a><span data-ttu-id="abcba-106">Members</span><span class="sxs-lookup"><span data-stu-id="abcba-106">Members</span></span>  
  
|<span data-ttu-id="abcba-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="abcba-107">Member</span></span>|<span data-ttu-id="abcba-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="abcba-108">Description</span></span>|  
|------------|-----------------|  
|`BLOCKING_NONE`|<span data-ttu-id="abcba-109">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="abcba-109">Internal use only.</span></span>|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|<span data-ttu-id="abcba-110">Un subproceso está intentando adquirir la sección crítica asociada al bloqueo de monitor en un objeto.</span><span class="sxs-lookup"><span data-stu-id="abcba-110">A thread is trying to acquire the critical section that is associated with the monitor lock on an object.</span></span> <span data-ttu-id="abcba-111">Normalmente, esto sucede cuando se llama a uno de <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> los <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> métodos o.</span><span class="sxs-lookup"><span data-stu-id="abcba-111">Typically, this occurs when you call one of the <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> or <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> methods.</span></span>|  
|`BLOCKING_MONITOR_EVENT`|<span data-ttu-id="abcba-112">Un subproceso está esperando en el evento que está asociado a un bloqueo de monitor para un objeto.</span><span class="sxs-lookup"><span data-stu-id="abcba-112">A thread is waiting on the event that is associated with a monitor lock for an object.</span></span> <span data-ttu-id="abcba-113">Normalmente, esto sucede cuando se llama a uno de los <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` métodos.</span><span class="sxs-lookup"><span data-stu-id="abcba-113">Typically, this occurs when you call one of the <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` methods.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abcba-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="abcba-114">Remarks</span></span>  

 <span data-ttu-id="abcba-115">Cuando el `BLOCKING_MONITOR_CRITICAL_SECTION` `BLOCKING_MONITOR_EVENT` miembro o se usa en una estructura [CorDebugBlockingObject](cordebugblockingobject-structure.md) , el `pBlockingObject` miembro de la estructura apunta a una interfaz "ICorDebugValue" que representa el objeto que se va a especificar.</span><span class="sxs-lookup"><span data-stu-id="abcba-115">When the `BLOCKING_MONITOR_CRITICAL_SECTION` or `BLOCKING_MONITOR_EVENT` member is used in a [CorDebugBlockingObject](cordebugblockingobject-structure.md) structure, the `pBlockingObject` member of the structure points to an "ICorDebugValue" interface that represents the object that is being entered.</span></span> <span data-ttu-id="abcba-116">También se garantiza la implementación de la interfaz [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="abcba-116">It is also guaranteed to implement the [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abcba-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="abcba-117">Requirements</span></span>  

 <span data-ttu-id="abcba-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abcba-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abcba-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="abcba-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="abcba-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="abcba-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="abcba-121">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abcba-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abcba-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="abcba-122">See also</span></span>

- [<span data-ttu-id="abcba-123">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="abcba-123">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="abcba-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="abcba-124">Debugging</span></span>](index.md)
