---
title: Estructura DacpGetModuleAddress
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress Structure
helpviewer.keywords:
- DacpGetModuleAddress Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a65fa9974165fa36e59a7fb83dca6dd902f7d8dc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724400"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="e99de-102">Estructura DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="e99de-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="e99de-103">Define el contenedor para una solicitud de dirección del módulo.</span><span class="sxs-lookup"><span data-stu-id="e99de-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e99de-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e99de-104">Syntax</span></span>

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="e99de-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e99de-105">Members</span></span>

| <span data-ttu-id="e99de-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e99de-106">Member</span></span>      | <span data-ttu-id="e99de-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e99de-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="e99de-108">Puntero al módulo.</span><span class="sxs-lookup"><span data-stu-id="e99de-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="e99de-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="e99de-109">Methods</span></span>

| <span data-ttu-id="e99de-110">Método</span><span class="sxs-lookup"><span data-stu-id="e99de-110">Method</span></span>                                                                                               | <span data-ttu-id="e99de-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="e99de-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="e99de-112">Solicitud</span><span class="sxs-lookup"><span data-stu-id="e99de-112">Request</span></span>](dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="e99de-113">Realiza una solicitud para rellenar la estructura a partir de la estructura en tiempo de ejecución especificada.</span><span class="sxs-lookup"><span data-stu-id="e99de-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="e99de-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e99de-114">Remarks</span></span>

<span data-ttu-id="e99de-115">Esta estructura reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="e99de-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="e99de-116">Para usarlo, defina la estructura como se especificó anteriormente, donde `CLRDATA_ADDRESS` es un entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="e99de-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="e99de-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e99de-117">Requirements</span></span>

<span data-ttu-id="e99de-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e99de-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e99de-119">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="e99de-119">**Header:** None</span></span>  
<span data-ttu-id="e99de-120">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="e99de-120">**Library:** None</span></span>  
<span data-ttu-id="e99de-121">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e99de-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e99de-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e99de-122">See also</span></span>

- [<span data-ttu-id="e99de-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="e99de-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="e99de-124">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="e99de-124">Debugging Structures</span></span>](debugging-structures.md)
