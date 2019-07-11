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
ms.openlocfilehash: 97079b824dbd0e056374af4173e49304babd6c32
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739136"
---
# <a name="dacpmethoddescdata-structure"></a><span data-ttu-id="0d915-102">Estructura DacpMethodDescData</span><span class="sxs-lookup"><span data-stu-id="0d915-102">DacpMethodDescData Structure</span></span>

<span data-ttu-id="0d915-103">Define un búfer de transporte para obtener información de tiempo de ejecución de un método.</span><span class="sxs-lookup"><span data-stu-id="0d915-103">Defines a transport buffer for a method's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="0d915-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d915-104">Syntax</span></span>

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

## <a name="members"></a><span data-ttu-id="0d915-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="0d915-105">Members</span></span>

| <span data-ttu-id="0d915-106">Member</span><span class="sxs-lookup"><span data-stu-id="0d915-106">Member</span></span>                       | <span data-ttu-id="0d915-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0d915-107">Description</span></span>                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | <span data-ttu-id="0d915-108">Indica si el tiempo de ejecución tiene disponible para la instancia especificada del método de código nativo.</span><span class="sxs-lookup"><span data-stu-id="0d915-108">Indicates if the runtime has native code available for the given instantiation of the method.</span></span> |
| `bIsDynamic`                 | <span data-ttu-id="0d915-109">Indica si el método se genera dinámicamente a través de la generación de código ligero.</span><span class="sxs-lookup"><span data-stu-id="0d915-109">Indicates if the method is generated dynamically through lightweight code generation.</span></span>           |
| `wSlotNumber`                | <span data-ttu-id="0d915-110">Número de ranura del método en la tabla de métodos.</span><span class="sxs-lookup"><span data-stu-id="0d915-110">The method's slot number in the method table.</span></span>                                                   |
| `NativeCodeAddr`             | <span data-ttu-id="0d915-111">Direcciones nativo inicial del método.</span><span class="sxs-lookup"><span data-stu-id="0d915-111">The method's initial native address.</span></span>                                                            |
| `data`                       | <span data-ttu-id="0d915-112">Puntero a un búfer utilizado internamente por el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0d915-112">Pointer to a buffer used internally by the runtime.</span></span>                                             |
| `MethodDescPtr`              | <span data-ttu-id="0d915-113">Puntero a la `MethodDesc` en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0d915-113">Pointer to the `MethodDesc` in the runtime.</span></span>                                                     |
| `nativeCodeInfo`             | <span data-ttu-id="0d915-114">Puntero a un búfer que se usa internamente el tiempo de ejecución para realizar un seguimiento de los métodos.</span><span class="sxs-lookup"><span data-stu-id="0d915-114">Pointer to a buffer used internally by the runtime to track methods.</span></span>                            |
| `moduleInfo`                 | <span data-ttu-id="0d915-115">Puntero a un búfer utilizado internamente por el tiempo de ejecución para obtener información de módulo.</span><span class="sxs-lookup"><span data-stu-id="0d915-115">Pointer to a buffer used internally by the runtime for module information.</span></span>                      |
| `MDToken`                    | <span data-ttu-id="0d915-116">Token asociado con el método especificado.</span><span class="sxs-lookup"><span data-stu-id="0d915-116">Token associated with the given method.</span></span>                                                         |
| `payloadGC`                  | <span data-ttu-id="0d915-117">Puntero a un búfer de la colección de elementos no utilizados lo utilizado internamente el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0d915-117">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `payloadGC2`                 | <span data-ttu-id="0d915-118">Puntero a un búfer de la colección de elementos no utilizados lo utilizado internamente el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0d915-118">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `managedDynamicMethodObject` | <span data-ttu-id="0d915-119">Si el método es dinámico, el tiempo de ejecución utiliza internamente este búfer para obtener información de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0d915-119">If the method is dynamic, the runtime uses this buffer internally for information tracking.</span></span>     |
| `requestedIP`                | <span data-ttu-id="0d915-120">Se usa para rellenar la estructura por solicitud cuando se especifica una dirección de código nativo.</span><span class="sxs-lookup"><span data-stu-id="0d915-120">Used to populate the structure per request when given a native code address.</span></span>                    |
| `rejitDataCurrent`           | <span data-ttu-id="0d915-121">Información acerca de la última versión instrumentada del método.</span><span class="sxs-lookup"><span data-stu-id="0d915-121">Information about the latest instrumented version of the method.</span></span>                                   |
| `rejitDataRequested`         | <span data-ttu-id="0d915-122">Información de ReJIT de la dirección solicitada nativa.</span><span class="sxs-lookup"><span data-stu-id="0d915-122">Rejit information for the requested native address.</span></span>                                             |
| `cJittedRejitVersions`       | <span data-ttu-id="0d915-123">Número de veces que el método ha sido rejitted a través de la instrumentación.</span><span class="sxs-lookup"><span data-stu-id="0d915-123">Number of times the method has been rejitted through instrumentation.</span></span>                           |

## <a name="remarks"></a><span data-ttu-id="0d915-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0d915-124">Remarks</span></span>

<span data-ttu-id="0d915-125">Esta estructura reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="0d915-125">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="0d915-126">Para ello, defina la estructura según lo especificado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0d915-126">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="0d915-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0d915-127">Requirements</span></span>
<span data-ttu-id="0d915-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d915-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="0d915-129">**Encabezado**: None</span><span class="sxs-lookup"><span data-stu-id="0d915-129">**Header:** None</span></span>  
<span data-ttu-id="0d915-130">**Biblioteca:** None</span><span class="sxs-lookup"><span data-stu-id="0d915-130">**Library:** None</span></span>  
<span data-ttu-id="0d915-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0d915-131">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="0d915-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d915-132">See also</span></span>

- [<span data-ttu-id="0d915-133">Depuración</span><span class="sxs-lookup"><span data-stu-id="0d915-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="0d915-134">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="0d915-134">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="0d915-135">Tipos de datos comunes</span><span class="sxs-lookup"><span data-stu-id="0d915-135">Common Data Types</span></span>](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)
