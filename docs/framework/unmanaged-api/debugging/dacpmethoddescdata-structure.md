---
description: 'Más información acerca de: estructura DacpMethodDescData'
title: Estructura DacpMethodDescData
ms.date: 02/01/2019
api.name:
- DacpMethodDescData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpMethodDescData Structure
helpviewer.keywords:
- DacpMethodDescData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: fe5b09874b3f8e123cb2501fcb00e3351aa44757
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801467"
---
# <a name="dacpmethoddescdata-structure"></a><span data-ttu-id="70c48-103">Estructura DacpMethodDescData</span><span class="sxs-lookup"><span data-stu-id="70c48-103">DacpMethodDescData Structure</span></span>

<span data-ttu-id="70c48-104">Define un búfer de transporte para la información de tiempo de ejecución de un método.</span><span class="sxs-lookup"><span data-stu-id="70c48-104">Defines a transport buffer for a method's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="70c48-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70c48-105">Syntax</span></span>

```cpp
struct DacpMethodDescData
{
    int             bHasNativeCode;
    int             bIsDynamic;
    unsigned short  wSlotNumber;
    CLRDATA_ADDRESS NativeCodeAddr;
    CLRDATA_ADDRESS data;
    CLRDATA_ADDRESS MethodDescPtr;
    CLRDATA_ADDRESS nativeCodeInfo;
    CLRDATA_ADDRESS moduleInfo;
    mdToken         MDToken;
    CLRDATA_ADDRESS payloadGC;
    CLRDATA_ADDRESS payloadGC2;
    CLRDATA_ADDRESS managedDynamicMethodObject;
    CLRDATA_ADDRESS requestedIP;
    DacpReJitData   rejitDataCurrent;
    DacpReJitData   rejitDataRequested;
    unsigned long   cJittedRejitVersions;
};
```

## <a name="members"></a><span data-ttu-id="70c48-106">Members</span><span class="sxs-lookup"><span data-stu-id="70c48-106">Members</span></span>

| <span data-ttu-id="70c48-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="70c48-107">Member</span></span>                       | <span data-ttu-id="70c48-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="70c48-108">Description</span></span>                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | <span data-ttu-id="70c48-109">Indica si el tiempo de ejecución tiene código nativo disponible para la creación de instancias dada del método.</span><span class="sxs-lookup"><span data-stu-id="70c48-109">Indicates if the runtime has native code available for the given instantiation of the method.</span></span> |
| `bIsDynamic`                 | <span data-ttu-id="70c48-110">Indica si el método se genera dinámicamente a través de la generación de código ligero.</span><span class="sxs-lookup"><span data-stu-id="70c48-110">Indicates if the method is generated dynamically through lightweight code generation.</span></span>           |
| `wSlotNumber`                | <span data-ttu-id="70c48-111">El número de ranura del método en la tabla de métodos.</span><span class="sxs-lookup"><span data-stu-id="70c48-111">The method's slot number in the method table.</span></span>                                                   |
| `NativeCodeAddr`             | <span data-ttu-id="70c48-112">Dirección nativa inicial del método.</span><span class="sxs-lookup"><span data-stu-id="70c48-112">The method's initial native address.</span></span>                                                            |
| `data`                       | <span data-ttu-id="70c48-113">Puntero a un búfer utilizado internamente por el motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="70c48-113">Pointer to a buffer used internally by the runtime.</span></span>                                             |
| `MethodDescPtr`              | <span data-ttu-id="70c48-114">Puntero a `MethodDesc` en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="70c48-114">Pointer to the `MethodDesc` in the runtime.</span></span>                                                     |
| `nativeCodeInfo`             | <span data-ttu-id="70c48-115">Puntero a un búfer utilizado internamente por el motor en tiempo de ejecución para realizar el seguimiento de los métodos.</span><span class="sxs-lookup"><span data-stu-id="70c48-115">Pointer to a buffer used internally by the runtime to track methods.</span></span>                            |
| `moduleInfo`                 | <span data-ttu-id="70c48-116">Puntero a un búfer utilizado internamente por el motor en tiempo de ejecución para obtener información del módulo.</span><span class="sxs-lookup"><span data-stu-id="70c48-116">Pointer to a buffer used internally by the runtime for module information.</span></span>                      |
| `MDToken`                    | <span data-ttu-id="70c48-117">Token asociado al método especificado.</span><span class="sxs-lookup"><span data-stu-id="70c48-117">Token associated with the given method.</span></span>                                                         |
| `payloadGC`                  | <span data-ttu-id="70c48-118">Puntero a un búfer de recolección de elementos no utilizados que el Runtime usa internamente.</span><span class="sxs-lookup"><span data-stu-id="70c48-118">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `payloadGC2`                 | <span data-ttu-id="70c48-119">Puntero a un búfer de recolección de elementos no utilizados que el Runtime usa internamente.</span><span class="sxs-lookup"><span data-stu-id="70c48-119">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `managedDynamicMethodObject` | <span data-ttu-id="70c48-120">Si el método es dinámico, el motor en tiempo de ejecución utiliza este búfer internamente para realizar el seguimiento de la información.</span><span class="sxs-lookup"><span data-stu-id="70c48-120">If the method is dynamic, the runtime uses this buffer internally for information tracking.</span></span>     |
| `requestedIP`                | <span data-ttu-id="70c48-121">Se usa para rellenar la estructura por solicitud cuando se proporciona una dirección de código nativo.</span><span class="sxs-lookup"><span data-stu-id="70c48-121">Used to populate the structure per request when given a native code address.</span></span>                    |
| `rejitDataCurrent`           | <span data-ttu-id="70c48-122">Información sobre la última versión instrumentada del método.</span><span class="sxs-lookup"><span data-stu-id="70c48-122">Information about the latest instrumented version of the method.</span></span>                                   |
| `rejitDataRequested`         | <span data-ttu-id="70c48-123">Rejit información de la dirección nativa solicitada.</span><span class="sxs-lookup"><span data-stu-id="70c48-123">Rejit information for the requested native address.</span></span>                                             |
| `cJittedRejitVersions`       | <span data-ttu-id="70c48-124">Número de veces que se ha rejitted el método a través de la instrumentación.</span><span class="sxs-lookup"><span data-stu-id="70c48-124">Number of times the method has been rejitted through instrumentation.</span></span>                           |

## <a name="remarks"></a><span data-ttu-id="70c48-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="70c48-125">Remarks</span></span>

<span data-ttu-id="70c48-126">Esta estructura reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="70c48-126">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="70c48-127">Para usarlo, defina la estructura tal y como se especificó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="70c48-127">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="70c48-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70c48-128">Requirements</span></span>

<span data-ttu-id="70c48-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70c48-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="70c48-130">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="70c48-130">**Header:** None</span></span>  
<span data-ttu-id="70c48-131">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="70c48-131">**Library:** None</span></span>  
<span data-ttu-id="70c48-132">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="70c48-132">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="70c48-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="70c48-133">See also</span></span>

- [<span data-ttu-id="70c48-134">Depuración</span><span class="sxs-lookup"><span data-stu-id="70c48-134">Debugging</span></span>](index.md)
- [<span data-ttu-id="70c48-135">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="70c48-135">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="70c48-136">Tipos de datos comunes</span><span class="sxs-lookup"><span data-stu-id="70c48-136">Common Data Types</span></span>](../common-data-types-unmanaged-api-reference.md)
