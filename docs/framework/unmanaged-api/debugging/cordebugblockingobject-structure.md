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
ms.openlocfilehash: ed7db321b32657087b791758096c692f25f3d7f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407841"
---
# <a name="cordebugblockingobject-structure"></a><span data-ttu-id="223f9-102">CorDebugBlockingObject (Estructura)</span><span class="sxs-lookup"><span data-stu-id="223f9-102">CorDebugBlockingObject Structure</span></span>
<span data-ttu-id="223f9-103">Define un objeto que está bloqueando un subproceso y la razón concreta por la que el subproceso está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="223f9-103">Defines an object that is blocking a thread and the specific reason that the thread is blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="223f9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="223f9-104">Syntax</span></span>  
  
```  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a><span data-ttu-id="223f9-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="223f9-105">Members</span></span>  
  
|<span data-ttu-id="223f9-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="223f9-106">Member</span></span>|<span data-ttu-id="223f9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="223f9-107">Description</span></span>|  
|------------|-----------------|  
|`pBlockingObject`|<span data-ttu-id="223f9-108">El objeto en el que está bloqueando el subproceso.</span><span class="sxs-lookup"><span data-stu-id="223f9-108">The object on which the thread is blocking.</span></span> <span data-ttu-id="223f9-109">Este objeto es válido solo durante el tiempo que dure el estado sincronizado actual.</span><span class="sxs-lookup"><span data-stu-id="223f9-109">This object is valid only for the duration of the current synchronized state.</span></span> <span data-ttu-id="223f9-110">Si dos subprocesos bloqueados en el mismo objeto en el mismo estado sincronizado, puede esperar el [ICorDebugValue:: GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) método para devolver el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="223f9-110">If two threads are blocking on the same object within the same synchronized state, you may expect the [ICorDebugValue::GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) method to return the same value.</span></span> <span data-ttu-id="223f9-111">Sin embargo, las interfaces pueden o no ser puntero equivalente.</span><span class="sxs-lookup"><span data-stu-id="223f9-111">However, the interfaces may or may not be pointer equivalent.</span></span>|  
|`dwTimeout`|<span data-ttu-id="223f9-112">El número de milisegundos que transcurren antes de la operación de bloqueo mostrará el tiempo de espera, o el valor INFINITE, que indica que agotará el tiempo de espera. El valor de tiempo de espera especifica la longitud total de tiempo para la operación de bloqueo, no el tiempo que queda todavía.</span><span class="sxs-lookup"><span data-stu-id="223f9-112">The number of milliseconds before the blocking operation will time out, or the value INFINITE, which indicates that it will not time out. The time-out value specifies the total length of time for the blocking operation, not the time that is still remaining.</span></span>|  
|`blockingReason`|<span data-ttu-id="223f9-113">La razón de que el subproceso está bloqueado en este objeto.</span><span class="sxs-lookup"><span data-stu-id="223f9-113">The reason that the thread is blocked on this object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="223f9-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="223f9-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="223f9-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="223f9-115">Requirements</span></span>  
 <span data-ttu-id="223f9-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="223f9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="223f9-117">**Encabezado:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="223f9-117">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="223f9-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="223f9-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="223f9-119">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="223f9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="223f9-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="223f9-120">See Also</span></span>  
 [<span data-ttu-id="223f9-121">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="223f9-121">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="223f9-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="223f9-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
