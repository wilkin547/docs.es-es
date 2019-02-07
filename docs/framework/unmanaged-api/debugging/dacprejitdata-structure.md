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
ms.openlocfilehash: 974b99da085a5cb969ab37cddb0f2f2c62010d14
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828690"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="c504a-102">Estructura DacpReJitData</span><span class="sxs-lookup"><span data-stu-id="c504a-102">DacpReJitData Structure</span></span>

<span data-ttu-id="c504a-103">Define la información básica sobre un determinado método del generador de perfiles instrumentada.</span><span class="sxs-lookup"><span data-stu-id="c504a-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="c504a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c504a-104">Syntax</span></span>

```
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

## <a name="members"></a><span data-ttu-id="c504a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c504a-105">Members</span></span>

| <span data-ttu-id="c504a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="c504a-106">Member</span></span>           | <span data-ttu-id="c504a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c504a-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="c504a-108">El número de revisión ReJit para un método.</span><span class="sxs-lookup"><span data-stu-id="c504a-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="c504a-109">Una marca que indica el estado actual de la instrumentación ReJit del método para la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="c504a-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="c504a-110">La dirección base de la implementación del método rejitted.</span><span class="sxs-lookup"><span data-stu-id="c504a-110">The base address of the method's rejitted implementation.</span></span>                                         |


## <a name="remarks"></a><span data-ttu-id="c504a-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c504a-111">Remarks</span></span>

<span data-ttu-id="c504a-112">Esta estructura reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="c504a-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="c504a-113">Para ello, defina la estructura según lo especificado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c504a-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="c504a-114">La estructura también debe definirse mediante `ms_struct` empaquetado si no se usan los compiladores de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c504a-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="c504a-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c504a-115">Requirements</span></span>
<span data-ttu-id="c504a-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c504a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="c504a-117">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="c504a-117">**Header:** None</span></span>  
<span data-ttu-id="c504a-118">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="c504a-118">**Library:** None</span></span>  
<span data-ttu-id="c504a-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c504a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="c504a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c504a-120">See also</span></span>
- [<span data-ttu-id="c504a-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="c504a-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="c504a-122">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="c504a-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
