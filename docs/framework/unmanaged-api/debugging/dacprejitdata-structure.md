---
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
ms.openlocfilehash: 46708acc77dad00727ee35e7d06e4228eacbd502
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723043"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="e8a89-102">Estructura DacpReJitData</span><span class="sxs-lookup"><span data-stu-id="e8a89-102">DacpReJitData Structure</span></span>

<span data-ttu-id="e8a89-103">Define la información básica sobre un método instrumentado del generador de perfiles determinado.</span><span class="sxs-lookup"><span data-stu-id="e8a89-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e8a89-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8a89-104">Syntax</span></span>

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

## <a name="members"></a><span data-ttu-id="e8a89-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e8a89-105">Members</span></span>

| <span data-ttu-id="e8a89-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e8a89-106">Member</span></span>           | <span data-ttu-id="e8a89-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8a89-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="e8a89-108">El número de revisión de ReJit para un método.</span><span class="sxs-lookup"><span data-stu-id="e8a89-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="e8a89-109">Marca que indica el estado actual de la instrumentación ReJit del método para la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="e8a89-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="e8a89-110">Dirección base de la implementación de rejitted del método.</span><span class="sxs-lookup"><span data-stu-id="e8a89-110">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="e8a89-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e8a89-111">Remarks</span></span>

<span data-ttu-id="e8a89-112">Esta estructura reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="e8a89-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="e8a89-113">Para usarlo, defina la estructura tal y como se especificó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e8a89-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="e8a89-114">La estructura también debe definirse mediante `ms_struct` Packing si no se usan los compiladores de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e8a89-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="e8a89-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8a89-115">Requirements</span></span>

<span data-ttu-id="e8a89-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8a89-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e8a89-117">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="e8a89-117">**Header:** None</span></span>  
<span data-ttu-id="e8a89-118">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="e8a89-118">**Library:** None</span></span>  
<span data-ttu-id="e8a89-119">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e8a89-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e8a89-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e8a89-120">See also</span></span>

- [<span data-ttu-id="e8a89-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="e8a89-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="e8a89-122">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="e8a89-122">Debugging Structures</span></span>](debugging-structures.md)
