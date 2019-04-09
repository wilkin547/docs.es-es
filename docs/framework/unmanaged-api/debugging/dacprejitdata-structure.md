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
ms.openlocfilehash: a2850add9acb2f7c5297ac6956e349c9277be291
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122803"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="52ef3-102">Estructura DacpReJitData</span><span class="sxs-lookup"><span data-stu-id="52ef3-102">DacpReJitData Structure</span></span>

<span data-ttu-id="52ef3-103">Define la información básica sobre un determinado método del generador de perfiles instrumentada.</span><span class="sxs-lookup"><span data-stu-id="52ef3-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="52ef3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52ef3-104">Syntax</span></span>

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

## <a name="members"></a><span data-ttu-id="52ef3-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="52ef3-105">Members</span></span>

| <span data-ttu-id="52ef3-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="52ef3-106">Member</span></span>           | <span data-ttu-id="52ef3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="52ef3-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="52ef3-108">El número de revisión ReJit para un método.</span><span class="sxs-lookup"><span data-stu-id="52ef3-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="52ef3-109">Una marca que indica el estado actual de la instrumentación ReJit del método para la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="52ef3-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="52ef3-110">La dirección base de la implementación del método rejitted.</span><span class="sxs-lookup"><span data-stu-id="52ef3-110">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="52ef3-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="52ef3-111">Remarks</span></span>

<span data-ttu-id="52ef3-112">Esta estructura reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="52ef3-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="52ef3-113">Para ello, defina la estructura según lo especificado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="52ef3-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="52ef3-114">La estructura también debe definirse mediante `ms_struct` empaquetado si no se usan los compiladores de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="52ef3-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="52ef3-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52ef3-115">Requirements</span></span>
<span data-ttu-id="52ef3-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52ef3-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="52ef3-117">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="52ef3-117">**Header:** None</span></span>  
<span data-ttu-id="52ef3-118">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="52ef3-118">**Library:** None</span></span>  
**<span data-ttu-id="52ef3-119">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="52ef3-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="52ef3-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="52ef3-120">See also</span></span>

- [<span data-ttu-id="52ef3-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="52ef3-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="52ef3-122">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="52ef3-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
