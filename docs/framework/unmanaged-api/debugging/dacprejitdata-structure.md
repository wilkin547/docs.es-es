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
ms.openlocfilehash: 46031f29da6916eeaeea863ebef6924a720d7155
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793812"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="134bb-102">Estructura DacpReJitData</span><span class="sxs-lookup"><span data-stu-id="134bb-102">DacpReJitData Structure</span></span>

<span data-ttu-id="134bb-103">Define la información básica sobre un método instrumentado del generador de perfiles determinado.</span><span class="sxs-lookup"><span data-stu-id="134bb-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="134bb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="134bb-104">Syntax</span></span>

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

## <a name="members"></a><span data-ttu-id="134bb-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="134bb-105">Members</span></span>

| <span data-ttu-id="134bb-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="134bb-106">Member</span></span>           | <span data-ttu-id="134bb-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="134bb-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="134bb-108">El número de revisión de ReJit para un método.</span><span class="sxs-lookup"><span data-stu-id="134bb-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="134bb-109">Marca que indica el estado actual de la instrumentación ReJit del método para la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="134bb-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="134bb-110">Dirección base de la implementación de rejitted del método.</span><span class="sxs-lookup"><span data-stu-id="134bb-110">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="134bb-111">Notas</span><span class="sxs-lookup"><span data-stu-id="134bb-111">Remarks</span></span>

<span data-ttu-id="134bb-112">Esta estructura reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="134bb-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="134bb-113">Para usarlo, defina la estructura tal y como se especificó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="134bb-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="134bb-114">La estructura también se debe definir utilizando `ms_struct` Packing si no se usan los compiladores de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="134bb-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="134bb-115">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="134bb-115">Requirements</span></span>
<span data-ttu-id="134bb-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="134bb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="134bb-117">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="134bb-117">**Header:** None</span></span>  
<span data-ttu-id="134bb-118">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="134bb-118">**Library:** None</span></span>  
<span data-ttu-id="134bb-119">**.NET Framework versiones:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="134bb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="134bb-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="134bb-120">See also</span></span>

- [<span data-ttu-id="134bb-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="134bb-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="134bb-122">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="134bb-122">Debugging Structures</span></span>](debugging-structures.md)
