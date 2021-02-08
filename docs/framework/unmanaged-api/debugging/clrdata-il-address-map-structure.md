---
description: 'Más información acerca de: estructura de CLRDATA_IL_ADDRESS_MAP'
title: Estructura CLRDATA_IL_ADDRESS_MAP
ms.date: 01/16/2019
api.name:
- CLRDATA_IL_ADDRESS_MAP Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure
helpviewer.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 02ee14154de0c1609e58cf6a2ad1ca62710567f5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801857"
---
# <a name="clrdata_il_address_map-structure"></a><span data-ttu-id="5e7ef-103">Estructura CLRDATA_IL_ADDRESS_MAP</span><span class="sxs-lookup"><span data-stu-id="5e7ef-103">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="5e7ef-104">Define una asignación de IL a dirección.</span><span class="sxs-lookup"><span data-stu-id="5e7ef-104">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5e7ef-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e7ef-105">Syntax</span></span>

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="5e7ef-106">Members</span><span class="sxs-lookup"><span data-stu-id="5e7ef-106">Members</span></span>

| <span data-ttu-id="5e7ef-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="5e7ef-107">Member</span></span>         | <span data-ttu-id="5e7ef-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e7ef-108">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="5e7ef-109">Desplazamiento IL para el intervalo de direcciones contenido</span><span class="sxs-lookup"><span data-stu-id="5e7ef-109">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="5e7ef-110">Dirección de inicio del intervalo.</span><span class="sxs-lookup"><span data-stu-id="5e7ef-110">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="5e7ef-111">Dirección final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="5e7ef-111">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="5e7ef-112">Tipo de los datos.</span><span class="sxs-lookup"><span data-stu-id="5e7ef-112">The type of the data.</span></span> <span data-ttu-id="5e7ef-113">Este valor no se usa actualmente</span><span class="sxs-lookup"><span data-stu-id="5e7ef-113">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="5e7ef-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5e7ef-114">Remarks</span></span>

<span data-ttu-id="5e7ef-115">Esta estructura reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="5e7ef-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="5e7ef-116">Para usarlo, defina la estructura como se especificó anteriormente, donde `CLRDATA_ADDRESS` es un entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="5e7ef-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="5e7ef-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e7ef-117">Requirements</span></span>

<span data-ttu-id="5e7ef-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e7ef-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5e7ef-119">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="5e7ef-119">**Header:** None</span></span>  
<span data-ttu-id="5e7ef-120">**Biblioteca:** Ninguna **.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5e7ef-120">**Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5e7ef-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e7ef-121">See also</span></span>

- [<span data-ttu-id="5e7ef-122">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="5e7ef-122">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="5e7ef-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="5e7ef-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="5e7ef-124">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="5e7ef-124">Debugging Structures</span></span>](debugging-structures.md)
