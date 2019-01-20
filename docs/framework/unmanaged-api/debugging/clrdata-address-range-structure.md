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
ms.openlocfilehash: 3a8832a0eb173da00715bd0441b7efd337eae932
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416545"
---
# <a name="clrdataaddressrange-structure"></a><span data-ttu-id="d6d85-102">Estructura CLRDATA_ADDRESS_RANGE</span><span class="sxs-lookup"><span data-stu-id="d6d85-102">CLRDATA_ADDRESS_RANGE Structure</span></span>

<span data-ttu-id="d6d85-103">Define un intervalo de direcciones.</span><span class="sxs-lookup"><span data-stu-id="d6d85-103">Defines an address range.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="d6d85-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6d85-104">Syntax</span></span>

```
typedef struct
{
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
} CLRDATA_ADDRESS_RANGE;
```

## <a name="members"></a><span data-ttu-id="d6d85-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="d6d85-105">Members</span></span>

| <span data-ttu-id="d6d85-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="d6d85-106">Member</span></span>         | <span data-ttu-id="d6d85-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6d85-107">Description</span></span>                     |
| -------------- | ------------------------------- |
| `startAddress` | <span data-ttu-id="d6d85-108">La dirección de inicio del intervalo.</span><span class="sxs-lookup"><span data-stu-id="d6d85-108">The start address of the range.</span></span> |
| `endAddress`   | <span data-ttu-id="d6d85-109">La dirección final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="d6d85-109">The end address of the range.</span></span>   |

## <a name="remarks"></a><span data-ttu-id="d6d85-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6d85-110">Remarks</span></span>

<span data-ttu-id="d6d85-111">Esta estructura reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="d6d85-111">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="d6d85-112">Para ello, defina la estructura según lo especificado anteriormente, donde `CLRDATA_ADDRESS` es un entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="d6d85-112">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="d6d85-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6d85-113">Requirements</span></span>

<span data-ttu-id="d6d85-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6d85-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d6d85-115">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="d6d85-115">**Header:** None</span></span>  
<span data-ttu-id="d6d85-116">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="d6d85-116">**Library:** None</span></span>  
<span data-ttu-id="d6d85-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d6d85-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d6d85-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6d85-118">See Also</span></span>

- [<span data-ttu-id="d6d85-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="d6d85-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="d6d85-120">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="d6d85-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
