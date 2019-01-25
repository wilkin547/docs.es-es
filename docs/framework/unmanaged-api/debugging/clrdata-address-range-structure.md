---
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
ms.openlocfilehash: 484ca79483fc4a5d8f0d1cf2cd5a961c297249e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654807"
---
# <a name="clrdataaddressrange-structure"></a><span data-ttu-id="39cea-102">Estructura CLRDATA_ADDRESS_RANGE</span><span class="sxs-lookup"><span data-stu-id="39cea-102">CLRDATA_ADDRESS_RANGE Structure</span></span>

<span data-ttu-id="39cea-103">Define un intervalo de direcciones.</span><span class="sxs-lookup"><span data-stu-id="39cea-103">Defines an address range.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="39cea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39cea-104">Syntax</span></span>

```
typedef struct
{
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
} CLRDATA_ADDRESS_RANGE;
```

## <a name="members"></a><span data-ttu-id="39cea-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="39cea-105">Members</span></span>

| <span data-ttu-id="39cea-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="39cea-106">Member</span></span>         | <span data-ttu-id="39cea-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="39cea-107">Description</span></span>                     |
| -------------- | ------------------------------- |
| `startAddress` | <span data-ttu-id="39cea-108">La dirección de inicio del intervalo.</span><span class="sxs-lookup"><span data-stu-id="39cea-108">The start address of the range.</span></span> |
| `endAddress`   | <span data-ttu-id="39cea-109">La dirección final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="39cea-109">The end address of the range.</span></span>   |

## <a name="remarks"></a><span data-ttu-id="39cea-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="39cea-110">Remarks</span></span>

<span data-ttu-id="39cea-111">Esta estructura reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="39cea-111">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="39cea-112">Para ello, defina la estructura según lo especificado anteriormente, donde `CLRDATA_ADDRESS` es un entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="39cea-112">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="39cea-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39cea-113">Requirements</span></span>

<span data-ttu-id="39cea-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39cea-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="39cea-115">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="39cea-115">**Header:** None</span></span>  
<span data-ttu-id="39cea-116">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="39cea-116">**Library:** None</span></span>  
<span data-ttu-id="39cea-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="39cea-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="39cea-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="39cea-118">See also</span></span>

- [<span data-ttu-id="39cea-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="39cea-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="39cea-120">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="39cea-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
