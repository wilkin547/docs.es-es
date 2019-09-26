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
ms.openlocfilehash: 8eb841b4c4f06a3932805ae6222bdd693def5ea0
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274309"
---
# <a name="clrdata_address_range-structure"></a><span data-ttu-id="20a39-102">Estructura CLRDATA_ADDRESS_RANGE</span><span class="sxs-lookup"><span data-stu-id="20a39-102">CLRDATA_ADDRESS_RANGE Structure</span></span>

<span data-ttu-id="20a39-103">Define un intervalo de direcciones.</span><span class="sxs-lookup"><span data-stu-id="20a39-103">Defines an address range.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="20a39-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20a39-104">Syntax</span></span>

```cpp
typedef struct
{
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
} CLRDATA_ADDRESS_RANGE;
```

## <a name="members"></a><span data-ttu-id="20a39-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="20a39-105">Members</span></span>

| <span data-ttu-id="20a39-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="20a39-106">Member</span></span>         | <span data-ttu-id="20a39-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="20a39-107">Description</span></span>                     |
| -------------- | ------------------------------- |
| `startAddress` | <span data-ttu-id="20a39-108">Dirección de inicio del intervalo.</span><span class="sxs-lookup"><span data-stu-id="20a39-108">The start address of the range.</span></span> |
| `endAddress`   | <span data-ttu-id="20a39-109">Dirección final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="20a39-109">The end address of the range.</span></span>   |

## <a name="remarks"></a><span data-ttu-id="20a39-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="20a39-110">Remarks</span></span>

<span data-ttu-id="20a39-111">Esta estructura reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="20a39-111">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="20a39-112">Para usarlo, defina la estructura como se especificó anteriormente, `CLRDATA_ADDRESS` donde es un entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="20a39-112">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="20a39-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20a39-113">Requirements</span></span>

<span data-ttu-id="20a39-114">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20a39-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="20a39-115">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="20a39-115">**Header:** None</span></span>  
<span data-ttu-id="20a39-116">**Biblioteca** Ninguna</span><span class="sxs-lookup"><span data-stu-id="20a39-116">**Library:** None</span></span>  
<span data-ttu-id="20a39-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="20a39-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="20a39-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="20a39-118">See also</span></span>

- [<span data-ttu-id="20a39-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="20a39-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="20a39-120">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="20a39-120">Debugging Structures</span></span>](debugging-structures.md)
