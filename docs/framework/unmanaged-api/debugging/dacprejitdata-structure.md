---
description: 'Más información acerca de: estructura DacpReJitData'
title: Estructura DacpReJitData
ms.date: 02/01/2019
api.name:
- DacpReJitData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpReJitData Structure
helpviewer.keywords:
- DacpReJitData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 8e8d506856dbc6579ac6ea0eee2b2088a980a315
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801441"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="e16c0-103">Estructura DacpReJitData</span><span class="sxs-lookup"><span data-stu-id="e16c0-103">DacpReJitData Structure</span></span>

<span data-ttu-id="e16c0-104">Define la información básica sobre un método instrumentado del generador de perfiles determinado.</span><span class="sxs-lookup"><span data-stu-id="e16c0-104">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e16c0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e16c0-105">Syntax</span></span>

```cpp
struct MSLAYOUT DacpReJitData
{
    enum Flags
    {
        kUnknown,
        kRequested,
        kActive,
        kReverted,
    };

    CLRDATA_ADDRESS                 rejitID;
    Flags                           flags;
    CLRDATA_ADDRESS                 NativeCodeAddr;
};
```

## <a name="members"></a><span data-ttu-id="e16c0-106">Members</span><span class="sxs-lookup"><span data-stu-id="e16c0-106">Members</span></span>

| <span data-ttu-id="e16c0-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="e16c0-107">Member</span></span>           | <span data-ttu-id="e16c0-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e16c0-108">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="e16c0-109">El número de revisión de ReJit para un método.</span><span class="sxs-lookup"><span data-stu-id="e16c0-109">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="e16c0-110">Marca que indica el estado actual de la instrumentación ReJit del método para la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="e16c0-110">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="e16c0-111">Dirección base de la implementación de rejitted del método.</span><span class="sxs-lookup"><span data-stu-id="e16c0-111">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="e16c0-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e16c0-112">Remarks</span></span>

<span data-ttu-id="e16c0-113">Esta estructura reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="e16c0-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="e16c0-114">Para usarlo, defina la estructura tal y como se especificó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e16c0-114">To use it, define the structure as specified above.</span></span> <span data-ttu-id="e16c0-115">La estructura también debe definirse mediante `ms_struct` Packing si no se usan los compiladores de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e16c0-115">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="e16c0-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e16c0-116">Requirements</span></span>

<span data-ttu-id="e16c0-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e16c0-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e16c0-118">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="e16c0-118">**Header:** None</span></span>  
<span data-ttu-id="e16c0-119">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="e16c0-119">**Library:** None</span></span>  
<span data-ttu-id="e16c0-120">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e16c0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e16c0-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e16c0-121">See also</span></span>

- [<span data-ttu-id="e16c0-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="e16c0-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="e16c0-123">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="e16c0-123">Debugging Structures</span></span>](debugging-structures.md)
