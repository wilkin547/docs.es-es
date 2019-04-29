---
title: Enumeración CorDebugStateChange
ms.date: 02/07/2019
api_name:
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05a29022d3ebad37322aef9826f10689d2b5b06b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723074"
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="ae9ec-102">Enumeración CorDebugStateChange</span><span class="sxs-lookup"><span data-stu-id="ae9ec-102">CorDebugStateChange Enumeration</span></span>

<span data-ttu-id="ae9ec-103">Describe la cantidad de datos almacenados en caché que se debe descartar según los cambios en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>

## <a name="syntax"></a><span data-ttu-id="ae9ec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae9ec-104">Syntax</span></span>

```
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a><span data-ttu-id="ae9ec-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ae9ec-105">Members</span></span>

| <span data-ttu-id="ae9ec-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="ae9ec-106">Member</span></span>            | <span data-ttu-id="ae9ec-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae9ec-107">Description</span></span>                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | <span data-ttu-id="ae9ec-108">El proceso alcanzó un nuevo estado de memoria por ejecución directa.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-108">The process reached a new memory state via forward execution.</span></span>            |
| `FLUSH_ALL`       | <span data-ttu-id="ae9ec-109">La memoria del proceso puede ser diferente de forma arbitraria de lo que era anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-109">The process' memory may be arbitrarily different than it was previously.</span></span> |

## <a name="remarks"></a><span data-ttu-id="ae9ec-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ae9ec-110">Remarks</span></span>

 <span data-ttu-id="ae9ec-111">Un miembro de la `CorDebugStateChange` enumeración se proporciona como un argumento cuando el depurador llama a la `ProcessStateChanged` método con [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) o [ICorDebugProcess6:: ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="ae9ec-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the `ProcessStateChanged` method either with [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) or [ICorDebugProcess6::ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span></span>

## <a name="requirements"></a><span data-ttu-id="ae9ec-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae9ec-112">Requirements</span></span>

 <span data-ttu-id="ae9ec-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae9ec-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="ae9ec-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae9ec-114">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="ae9ec-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae9ec-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="ae9ec-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae9ec-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ae9ec-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae9ec-117">See also</span></span>

- [<span data-ttu-id="ae9ec-118">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="ae9ec-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="ae9ec-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="ae9ec-119">Debugging</span></span>](index.md)
