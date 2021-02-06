---
description: 'Más información acerca de: estructura DacpGetModuleAddress'
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
ms.openlocfilehash: 3de76cc4f15bffd35d7a43ae25a313eb2fe59b82
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661602"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="a63f1-103">Estructura DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="a63f1-103">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="a63f1-104">Define el contenedor para una solicitud de dirección del módulo.</span><span class="sxs-lookup"><span data-stu-id="a63f1-104">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a63f1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a63f1-105">Syntax</span></span>

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="a63f1-106">Members</span><span class="sxs-lookup"><span data-stu-id="a63f1-106">Members</span></span>

| <span data-ttu-id="a63f1-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="a63f1-107">Member</span></span>      | <span data-ttu-id="a63f1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a63f1-108">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="a63f1-109">Puntero al módulo.</span><span class="sxs-lookup"><span data-stu-id="a63f1-109">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="a63f1-110">Métodos</span><span class="sxs-lookup"><span data-stu-id="a63f1-110">Methods</span></span>

| <span data-ttu-id="a63f1-111">Método</span><span class="sxs-lookup"><span data-stu-id="a63f1-111">Method</span></span>                                                                                               | <span data-ttu-id="a63f1-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a63f1-112">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="a63f1-113">Solicitud</span><span class="sxs-lookup"><span data-stu-id="a63f1-113">Request</span></span>](dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="a63f1-114">Realiza una solicitud para rellenar la estructura a partir de la estructura en tiempo de ejecución especificada.</span><span class="sxs-lookup"><span data-stu-id="a63f1-114">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="a63f1-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a63f1-115">Remarks</span></span>

<span data-ttu-id="a63f1-116">Esta estructura reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="a63f1-116">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="a63f1-117">Para usarlo, defina la estructura como se especificó anteriormente, donde `CLRDATA_ADDRESS` es un entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="a63f1-117">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="a63f1-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a63f1-118">Requirements</span></span>

<span data-ttu-id="a63f1-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a63f1-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="a63f1-120">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="a63f1-120">**Header:** None</span></span>  
<span data-ttu-id="a63f1-121">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="a63f1-121">**Library:** None</span></span>  
<span data-ttu-id="a63f1-122">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a63f1-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="a63f1-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a63f1-123">See also</span></span>

- [<span data-ttu-id="a63f1-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="a63f1-124">Debugging</span></span>](index.md)
- [<span data-ttu-id="a63f1-125">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="a63f1-125">Debugging Structures</span></span>](debugging-structures.md)
