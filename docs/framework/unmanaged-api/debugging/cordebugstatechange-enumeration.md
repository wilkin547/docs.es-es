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
ms.openlocfilehash: 239e3a82df0e6010278669f9f429bfad0d163319
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133725"
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="a333b-102">Enumeración CorDebugStateChange</span><span class="sxs-lookup"><span data-stu-id="a333b-102">CorDebugStateChange Enumeration</span></span>

<span data-ttu-id="a333b-103">Describe la cantidad de datos almacenados en caché que se debe descartar según los cambios en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a333b-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>

## <a name="syntax"></a><span data-ttu-id="a333b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a333b-104">Syntax</span></span>

```cpp
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a><span data-ttu-id="a333b-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a333b-105">Members</span></span>

| <span data-ttu-id="a333b-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a333b-106">Member</span></span>            | <span data-ttu-id="a333b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a333b-107">Description</span></span>                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | <span data-ttu-id="a333b-108">El proceso alcanzó un nuevo estado de memoria por ejecución directa.</span><span class="sxs-lookup"><span data-stu-id="a333b-108">The process reached a new memory state via forward execution.</span></span>            |
| `FLUSH_ALL`       | <span data-ttu-id="a333b-109">La memoria del proceso puede ser diferente de forma arbitraria de lo que era anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a333b-109">The process' memory may be arbitrarily different than it was previously.</span></span> |

## <a name="remarks"></a><span data-ttu-id="a333b-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a333b-110">Remarks</span></span>

 <span data-ttu-id="a333b-111">Un miembro de la enumeración `CorDebugStateChange` se proporciona como argumento cuando el depurador llama al método `ProcessStateChanged` con [ICorDebugProcess4::P rocessstatechanged](icordebugprocess4-processstatechanged-method.md) o [método icordebugprocess6::P rocessstatechanged](icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="a333b-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the `ProcessStateChanged` method either with [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) or [ICorDebugProcess6::ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span></span>

## <a name="requirements"></a><span data-ttu-id="a333b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a333b-112">Requirements</span></span>

 <span data-ttu-id="a333b-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a333b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="a333b-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a333b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="a333b-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a333b-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="a333b-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a333b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a333b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a333b-117">See also</span></span>

- [<span data-ttu-id="a333b-118">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="a333b-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="a333b-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="a333b-119">Debugging</span></span>](index.md)
