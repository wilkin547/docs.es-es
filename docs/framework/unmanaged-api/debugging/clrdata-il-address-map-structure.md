---
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
ms.openlocfilehash: e680a7a0dc3209d1988f6c84be0864572a74b3a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179375"
---
# <a name="clrdata_il_address_map-structure"></a><span data-ttu-id="36b1b-102">Estructura CLRDATA_IL_ADDRESS_MAP</span><span class="sxs-lookup"><span data-stu-id="36b1b-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="36b1b-103">Define una asignación de IL para direccionar.</span><span class="sxs-lookup"><span data-stu-id="36b1b-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="36b1b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36b1b-104">Syntax</span></span>

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="36b1b-105">Members</span><span class="sxs-lookup"><span data-stu-id="36b1b-105">Members</span></span>

| <span data-ttu-id="36b1b-106">Member</span><span class="sxs-lookup"><span data-stu-id="36b1b-106">Member</span></span>         | <span data-ttu-id="36b1b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="36b1b-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="36b1b-108">Desplazamiento de IL para el rango de direcciones contenido</span><span class="sxs-lookup"><span data-stu-id="36b1b-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="36b1b-109">La dirección de inicio del rango.</span><span class="sxs-lookup"><span data-stu-id="36b1b-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="36b1b-110">La dirección final del rango.</span><span class="sxs-lookup"><span data-stu-id="36b1b-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="36b1b-111">Tipo de los datos.</span><span class="sxs-lookup"><span data-stu-id="36b1b-111">The type of the data.</span></span> <span data-ttu-id="36b1b-112">Este valor no se utiliza actualmente</span><span class="sxs-lookup"><span data-stu-id="36b1b-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="36b1b-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="36b1b-113">Remarks</span></span>

<span data-ttu-id="36b1b-114">Esta estructura se encuentra dentro del tiempo de ejecución y no se expone a través de encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="36b1b-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="36b1b-115">Para usarlo, defina la estructura como `CLRDATA_ADDRESS` se especificó anteriormente, donde hay un entero sin signo de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="36b1b-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="36b1b-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36b1b-116">Requirements</span></span>

<span data-ttu-id="36b1b-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36b1b-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="36b1b-118">**Encabezado:** Ninguno</span><span class="sxs-lookup"><span data-stu-id="36b1b-118">**Header:** None</span></span>  
<span data-ttu-id="36b1b-119">**Biblioteca:** Ninguna versión de **.NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="36b1b-119">**Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="36b1b-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="36b1b-120">See also</span></span>

- [<span data-ttu-id="36b1b-121">CLRDataSourceType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="36b1b-121">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="36b1b-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="36b1b-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="36b1b-123">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="36b1b-123">Debugging Structures</span></span>](debugging-structures.md)
