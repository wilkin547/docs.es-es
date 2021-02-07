---
description: 'Más información acerca de: CorDebugBlockingObject (estructura)'
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
ms.openlocfilehash: 2b16af5eecb01067c2ee6811613f964af391f345
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712225"
---
# <a name="cordebugblockingobject-structure"></a><span data-ttu-id="02d11-103">CorDebugBlockingObject (Estructura)</span><span class="sxs-lookup"><span data-stu-id="02d11-103">CorDebugBlockingObject Structure</span></span>

<span data-ttu-id="02d11-104">Define un objeto que está bloqueando un subproceso y el motivo concreto por el que el subproceso está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="02d11-104">Defines an object that is blocking a thread and the specific reason that the thread is blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02d11-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02d11-105">Syntax</span></span>  
  
```cpp  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a><span data-ttu-id="02d11-106">Members</span><span class="sxs-lookup"><span data-stu-id="02d11-106">Members</span></span>  
  
|<span data-ttu-id="02d11-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="02d11-107">Member</span></span>|<span data-ttu-id="02d11-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="02d11-108">Description</span></span>|  
|------------|-----------------|  
|`pBlockingObject`|<span data-ttu-id="02d11-109">Objeto en el que el subproceso está bloqueando.</span><span class="sxs-lookup"><span data-stu-id="02d11-109">The object on which the thread is blocking.</span></span> <span data-ttu-id="02d11-110">Este objeto solo es válido para la duración del estado sincronizado actual.</span><span class="sxs-lookup"><span data-stu-id="02d11-110">This object is valid only for the duration of the current synchronized state.</span></span> <span data-ttu-id="02d11-111">Si dos subprocesos se bloquean en el mismo objeto dentro del mismo estado sincronizado, puede esperar que el método [ICorDebugValue:: GetAddress](icordebugvalue-getaddress-method.md) devuelva el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="02d11-111">If two threads are blocking on the same object within the same synchronized state, you may expect the [ICorDebugValue::GetAddress](icordebugvalue-getaddress-method.md) method to return the same value.</span></span> <span data-ttu-id="02d11-112">Sin embargo, las interfaces pueden o no ser equivalentes del puntero.</span><span class="sxs-lookup"><span data-stu-id="02d11-112">However, the interfaces may or may not be pointer equivalent.</span></span>|  
|`dwTimeout`|<span data-ttu-id="02d11-113">El número de milisegundos antes de que se agote el tiempo de espera de la operación de bloqueo o el valor infinito, lo que indica que no se agotará el tiempo de espera. El valor de tiempo de espera especifica la duración total de la operación de bloqueo, no el tiempo que todavía permanece.</span><span class="sxs-lookup"><span data-stu-id="02d11-113">The number of milliseconds before the blocking operation will time out, or the value INFINITE, which indicates that it will not time out. The time-out value specifies the total length of time for the blocking operation, not the time that is still remaining.</span></span>|  
|`blockingReason`|<span data-ttu-id="02d11-114">Motivo por el que el subproceso está bloqueado en este objeto.</span><span class="sxs-lookup"><span data-stu-id="02d11-114">The reason that the thread is blocked on this object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02d11-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="02d11-115">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02d11-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02d11-116">Requirements</span></span>  

 <span data-ttu-id="02d11-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02d11-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02d11-118">**Encabezado:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="02d11-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="02d11-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02d11-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02d11-120">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02d11-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d11-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="02d11-121">See also</span></span>

- [<span data-ttu-id="02d11-122">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="02d11-122">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="02d11-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="02d11-123">Debugging</span></span>](index.md)
