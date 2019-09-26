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
ms.openlocfilehash: 57de11c1c40c05befcf3c99c31c2e07e1ecaec5a
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71273967"
---
# <a name="cordebugblockingobject-structure"></a><span data-ttu-id="76d3b-102">CorDebugBlockingObject (Estructura)</span><span class="sxs-lookup"><span data-stu-id="76d3b-102">CorDebugBlockingObject Structure</span></span>
<span data-ttu-id="76d3b-103">Define un objeto que está bloqueando un subproceso y el motivo concreto por el que el subproceso está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="76d3b-103">Defines an object that is blocking a thread and the specific reason that the thread is blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76d3b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76d3b-104">Syntax</span></span>  
  
```cpp  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a><span data-ttu-id="76d3b-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="76d3b-105">Members</span></span>  
  
|<span data-ttu-id="76d3b-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="76d3b-106">Member</span></span>|<span data-ttu-id="76d3b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="76d3b-107">Description</span></span>|  
|------------|-----------------|  
|`pBlockingObject`|<span data-ttu-id="76d3b-108">Objeto en el que el subproceso está bloqueando.</span><span class="sxs-lookup"><span data-stu-id="76d3b-108">The object on which the thread is blocking.</span></span> <span data-ttu-id="76d3b-109">Este objeto solo es válido para la duración del estado sincronizado actual.</span><span class="sxs-lookup"><span data-stu-id="76d3b-109">This object is valid only for the duration of the current synchronized state.</span></span> <span data-ttu-id="76d3b-110">Si dos subprocesos se bloquean en el mismo objeto dentro del mismo estado sincronizado, puede esperar que el método [ICorDebugValue:: GetAddress](icordebugvalue-getaddress-method.md) devuelva el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="76d3b-110">If two threads are blocking on the same object within the same synchronized state, you may expect the [ICorDebugValue::GetAddress](icordebugvalue-getaddress-method.md) method to return the same value.</span></span> <span data-ttu-id="76d3b-111">Sin embargo, las interfaces pueden o no ser equivalentes del puntero.</span><span class="sxs-lookup"><span data-stu-id="76d3b-111">However, the interfaces may or may not be pointer equivalent.</span></span>|  
|`dwTimeout`|<span data-ttu-id="76d3b-112">El número de milisegundos antes de que se agote el tiempo de espera de la operación de bloqueo o el valor infinito, lo que indica que no se agotará el tiempo de espera. El valor de tiempo de espera especifica la duración total de la operación de bloqueo, no el tiempo que todavía permanece.</span><span class="sxs-lookup"><span data-stu-id="76d3b-112">The number of milliseconds before the blocking operation will time out, or the value INFINITE, which indicates that it will not time out. The time-out value specifies the total length of time for the blocking operation, not the time that is still remaining.</span></span>|  
|`blockingReason`|<span data-ttu-id="76d3b-113">Motivo por el que el subproceso está bloqueado en este objeto.</span><span class="sxs-lookup"><span data-stu-id="76d3b-113">The reason that the thread is blocked on this object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76d3b-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="76d3b-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76d3b-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76d3b-115">Requirements</span></span>  
 <span data-ttu-id="76d3b-116">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76d3b-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76d3b-117">**Encabezado**: CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="76d3b-117">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="76d3b-118">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76d3b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76d3b-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76d3b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76d3b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="76d3b-120">See also</span></span>

- [<span data-ttu-id="76d3b-121">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="76d3b-121">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="76d3b-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="76d3b-122">Debugging</span></span>](index.md)
