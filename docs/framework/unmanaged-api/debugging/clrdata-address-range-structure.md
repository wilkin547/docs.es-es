---
description: 'Más información acerca de: estructura de CLRDATA_ADDRESS_RANGE'
title: Estructura CLRDATA_ADDRESS_RANGE
ms.date: 01/16/2019
api.name:
- CLRDATA_ADDRESS_RANGE Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDATA_ADDRESS_RANGE Structure
helpviewer.keywords:
- CLRDATA_ADDRESS_RANGE Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 5d671a08064781b71756efc3c753468e6769d4ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662343"
---
# <a name="clrdata_address_range-structure"></a><span data-ttu-id="d48c3-103">Estructura CLRDATA_ADDRESS_RANGE</span><span class="sxs-lookup"><span data-stu-id="d48c3-103">CLRDATA_ADDRESS_RANGE Structure</span></span>

<span data-ttu-id="d48c3-104">Define un intervalo de direcciones.</span><span class="sxs-lookup"><span data-stu-id="d48c3-104">Defines an address range.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="d48c3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d48c3-105">Syntax</span></span>

```cpp
typedef struct
{
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
} CLRDATA_ADDRESS_RANGE;
```

## <a name="members"></a><span data-ttu-id="d48c3-106">Members</span><span class="sxs-lookup"><span data-stu-id="d48c3-106">Members</span></span>

| <span data-ttu-id="d48c3-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="d48c3-107">Member</span></span>         | <span data-ttu-id="d48c3-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d48c3-108">Description</span></span>                     |
| -------------- | ------------------------------- |
| `startAddress` | <span data-ttu-id="d48c3-109">Dirección de inicio del intervalo.</span><span class="sxs-lookup"><span data-stu-id="d48c3-109">The start address of the range.</span></span> |
| `endAddress`   | <span data-ttu-id="d48c3-110">Dirección final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="d48c3-110">The end address of the range.</span></span>   |

## <a name="remarks"></a><span data-ttu-id="d48c3-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d48c3-111">Remarks</span></span>

<span data-ttu-id="d48c3-112">Esta estructura reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="d48c3-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="d48c3-113">Para usarlo, defina la estructura como se especificó anteriormente, donde `CLRDATA_ADDRESS` es un entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="d48c3-113">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="d48c3-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d48c3-114">Requirements</span></span>

<span data-ttu-id="d48c3-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d48c3-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d48c3-116">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="d48c3-116">**Header:** None</span></span>  
<span data-ttu-id="d48c3-117">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="d48c3-117">**Library:** None</span></span>  
<span data-ttu-id="d48c3-118">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d48c3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d48c3-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d48c3-119">See also</span></span>

- [<span data-ttu-id="d48c3-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="d48c3-120">Debugging</span></span>](index.md)
- [<span data-ttu-id="d48c3-121">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="d48c3-121">Debugging Structures</span></span>](debugging-structures.md)
