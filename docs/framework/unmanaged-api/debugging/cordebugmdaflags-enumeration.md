---
description: 'Más información sobre: enumeración CorDebugMDAFlags ('
title: CorDebugMDAFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugMDAFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMDAFlags
helpviewer_keywords:
- CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type:
- apiref
ms.openlocfilehash: d7e9178d76286b112035729e997b1f68e2a93fb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661940"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="91f4d-103">CorDebugMDAFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="91f4d-103">CorDebugMDAFlags Enumeration</span></span>

<span data-ttu-id="91f4d-104">Especifica el estado del subproceso en el que se activa el asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="91f4d-104">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91f4d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91f4d-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="91f4d-106">Members</span><span class="sxs-lookup"><span data-stu-id="91f4d-106">Members</span></span>  
  
|<span data-ttu-id="91f4d-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="91f4d-107">Member</span></span>|<span data-ttu-id="91f4d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="91f4d-108">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="91f4d-109">El subproceso en el que se ha desencadenado el MDA se ha retrasado desde que se activó el MDA.</span><span class="sxs-lookup"><span data-stu-id="91f4d-109">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91f4d-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="91f4d-110">Remarks</span></span>  

 <span data-ttu-id="91f4d-111">Cuando la pila de llamadas ya no describe dónde se generó originalmente el MDA, se considera que el subproceso se ha *retrasado*.</span><span class="sxs-lookup"><span data-stu-id="91f4d-111">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="91f4d-112">Se trata de una circunstancia inusual realizada por la ejecución del subproceso de una operación no válida al salir.</span><span class="sxs-lookup"><span data-stu-id="91f4d-112">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91f4d-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91f4d-113">Requirements</span></span>  

 <span data-ttu-id="91f4d-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91f4d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91f4d-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91f4d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91f4d-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91f4d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91f4d-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91f4d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91f4d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="91f4d-118">See also</span></span>

- [<span data-ttu-id="91f4d-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="91f4d-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
