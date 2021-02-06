---
description: 'Más información sobre: enumeración CorDebugStateChange'
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
ms.openlocfilehash: 1900baa77432daa10d0f1a32dd9cb25198b86ed1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661823"
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="57478-103">Enumeración CorDebugStateChange</span><span class="sxs-lookup"><span data-stu-id="57478-103">CorDebugStateChange Enumeration</span></span>

<span data-ttu-id="57478-104">Describe la cantidad de datos almacenados en caché que se debe descartar según los cambios en el proceso.</span><span class="sxs-lookup"><span data-stu-id="57478-104">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>

## <a name="syntax"></a><span data-ttu-id="57478-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57478-105">Syntax</span></span>

```cpp
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a><span data-ttu-id="57478-106">Members</span><span class="sxs-lookup"><span data-stu-id="57478-106">Members</span></span>

| <span data-ttu-id="57478-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="57478-107">Member</span></span>            | <span data-ttu-id="57478-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="57478-108">Description</span></span>                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | <span data-ttu-id="57478-109">El proceso alcanzó un nuevo estado de memoria por ejecución directa.</span><span class="sxs-lookup"><span data-stu-id="57478-109">The process reached a new memory state via forward execution.</span></span>            |
| `FLUSH_ALL`       | <span data-ttu-id="57478-110">La memoria del proceso puede ser diferente de forma arbitraria de lo que era anteriormente.</span><span class="sxs-lookup"><span data-stu-id="57478-110">The process' memory may be arbitrarily different than it was previously.</span></span> |

## <a name="remarks"></a><span data-ttu-id="57478-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="57478-111">Remarks</span></span>

 <span data-ttu-id="57478-112">Un miembro de la `CorDebugStateChange` enumeración se proporciona como argumento cuando el depurador llama al `ProcessStateChanged` método con [ICorDebugProcess4::P rocessstatechanged](icordebugprocess4-processstatechanged-method.md) o [método icordebugprocess6::P rocessstatechanged](icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="57478-112">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the `ProcessStateChanged` method either with [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) or [ICorDebugProcess6::ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span></span>

## <a name="requirements"></a><span data-ttu-id="57478-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57478-113">Requirements</span></span>

 <span data-ttu-id="57478-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57478-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="57478-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57478-115">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="57478-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57478-116">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="57478-117">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57478-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="57478-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="57478-118">See also</span></span>

- [<span data-ttu-id="57478-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="57478-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="57478-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="57478-120">Debugging</span></span>](index.md)
