---
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
ms.openlocfilehash: cc54664ea8ad61005de3f3fae7407946d1c861b2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793845"
---
# <a name="dacpmethoddescdata-structure"></a><span data-ttu-id="9c624-102">Estructura DacpMethodDescData</span><span class="sxs-lookup"><span data-stu-id="9c624-102">DacpMethodDescData Structure</span></span>

<span data-ttu-id="9c624-103">Define un búfer de transporte para la información de tiempo de ejecución de un método.</span><span class="sxs-lookup"><span data-stu-id="9c624-103">Defines a transport buffer for a method's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9c624-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c624-104">Syntax</span></span>

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

## <a name="members"></a><span data-ttu-id="9c624-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9c624-105">Members</span></span>

| <span data-ttu-id="9c624-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9c624-106">Member</span></span>                       | <span data-ttu-id="9c624-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c624-107">Description</span></span>                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | <span data-ttu-id="9c624-108">Indica si el tiempo de ejecución tiene código nativo disponible para la creación de instancias dada del método.</span><span class="sxs-lookup"><span data-stu-id="9c624-108">Indicates if the runtime has native code available for the given instantiation of the method.</span></span> |
| `bIsDynamic`                 | <span data-ttu-id="9c624-109">Indica si el método se genera dinámicamente a través de la generación de código ligero.</span><span class="sxs-lookup"><span data-stu-id="9c624-109">Indicates if the method is generated dynamically through lightweight code generation.</span></span>           |
| `wSlotNumber`                | <span data-ttu-id="9c624-110">El número de ranura del método en la tabla de métodos.</span><span class="sxs-lookup"><span data-stu-id="9c624-110">The method's slot number in the method table.</span></span>                                                   |
| `NativeCodeAddr`             | <span data-ttu-id="9c624-111">Dirección nativa inicial del método.</span><span class="sxs-lookup"><span data-stu-id="9c624-111">The method's initial native address.</span></span>                                                            |
| `data`                       | <span data-ttu-id="9c624-112">Puntero a un búfer utilizado internamente por el motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9c624-112">Pointer to a buffer used internally by the runtime.</span></span>                                             |
| `MethodDescPtr`              | <span data-ttu-id="9c624-113">Puntero al `MethodDesc` en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9c624-113">Pointer to the `MethodDesc` in the runtime.</span></span>                                                     |
| `nativeCodeInfo`             | <span data-ttu-id="9c624-114">Puntero a un búfer utilizado internamente por el motor en tiempo de ejecución para realizar el seguimiento de los métodos.</span><span class="sxs-lookup"><span data-stu-id="9c624-114">Pointer to a buffer used internally by the runtime to track methods.</span></span>                            |
| `moduleInfo`                 | <span data-ttu-id="9c624-115">Puntero a un búfer utilizado internamente por el motor en tiempo de ejecución para obtener información del módulo.</span><span class="sxs-lookup"><span data-stu-id="9c624-115">Pointer to a buffer used internally by the runtime for module information.</span></span>                      |
| `MDToken`                    | <span data-ttu-id="9c624-116">Token asociado al método especificado.</span><span class="sxs-lookup"><span data-stu-id="9c624-116">Token associated with the given method.</span></span>                                                         |
| `payloadGC`                  | <span data-ttu-id="9c624-117">Puntero a un búfer de recolección de elementos no utilizados que el Runtime usa internamente.</span><span class="sxs-lookup"><span data-stu-id="9c624-117">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `payloadGC2`                 | <span data-ttu-id="9c624-118">Puntero a un búfer de recolección de elementos no utilizados que el Runtime usa internamente.</span><span class="sxs-lookup"><span data-stu-id="9c624-118">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `managedDynamicMethodObject` | <span data-ttu-id="9c624-119">Si el método es dinámico, el motor en tiempo de ejecución utiliza este búfer internamente para realizar el seguimiento de la información.</span><span class="sxs-lookup"><span data-stu-id="9c624-119">If the method is dynamic, the runtime uses this buffer internally for information tracking.</span></span>     |
| `requestedIP`                | <span data-ttu-id="9c624-120">Se usa para rellenar la estructura por solicitud cuando se proporciona una dirección de código nativo.</span><span class="sxs-lookup"><span data-stu-id="9c624-120">Used to populate the structure per request when given a native code address.</span></span>                    |
| `rejitDataCurrent`           | <span data-ttu-id="9c624-121">Información sobre la última versión instrumentada del método.</span><span class="sxs-lookup"><span data-stu-id="9c624-121">Information about the latest instrumented version of the method.</span></span>                                   |
| `rejitDataRequested`         | <span data-ttu-id="9c624-122">Rejit información de la dirección nativa solicitada.</span><span class="sxs-lookup"><span data-stu-id="9c624-122">Rejit information for the requested native address.</span></span>                                             |
| `cJittedRejitVersions`       | <span data-ttu-id="9c624-123">Número de veces que se ha rejitted el método a través de la instrumentación.</span><span class="sxs-lookup"><span data-stu-id="9c624-123">Number of times the method has been rejitted through instrumentation.</span></span>                           |

## <a name="remarks"></a><span data-ttu-id="9c624-124">Notas</span><span class="sxs-lookup"><span data-stu-id="9c624-124">Remarks</span></span>

<span data-ttu-id="9c624-125">Esta estructura reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="9c624-125">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="9c624-126">Para usarlo, defina la estructura tal y como se especificó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9c624-126">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="9c624-127">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="9c624-127">Requirements</span></span>
<span data-ttu-id="9c624-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c624-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9c624-129">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="9c624-129">**Header:** None</span></span>  
<span data-ttu-id="9c624-130">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="9c624-130">**Library:** None</span></span>  
<span data-ttu-id="9c624-131">**.NET Framework versiones:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9c624-131">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9c624-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c624-132">See also</span></span>

- [<span data-ttu-id="9c624-133">Depuración</span><span class="sxs-lookup"><span data-stu-id="9c624-133">Debugging</span></span>](index.md)
- [<span data-ttu-id="9c624-134">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="9c624-134">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="9c624-135">Tipos de datos comunes</span><span class="sxs-lookup"><span data-stu-id="9c624-135">Common Data Types</span></span>](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)
