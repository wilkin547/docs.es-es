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
ms.openlocfilehash: 3f6928832d822422177ebd7def142422953468a0
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274295"
---
# <a name="clrdata_il_address_map-structure"></a><span data-ttu-id="e4948-102">Estructura CLRDATA_IL_ADDRESS_MAP</span><span class="sxs-lookup"><span data-stu-id="e4948-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="e4948-103">Define una asignación de IL a dirección.</span><span class="sxs-lookup"><span data-stu-id="e4948-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e4948-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4948-104">Syntax</span></span>

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="e4948-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e4948-105">Members</span></span>

| <span data-ttu-id="e4948-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e4948-106">Member</span></span>         | <span data-ttu-id="e4948-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4948-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="e4948-108">Desplazamiento IL para el intervalo de direcciones contenido</span><span class="sxs-lookup"><span data-stu-id="e4948-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="e4948-109">Dirección de inicio del intervalo.</span><span class="sxs-lookup"><span data-stu-id="e4948-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="e4948-110">Dirección final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="e4948-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="e4948-111">Tipo de los datos.</span><span class="sxs-lookup"><span data-stu-id="e4948-111">The type of the data.</span></span> <span data-ttu-id="e4948-112">Este valor no se usa actualmente</span><span class="sxs-lookup"><span data-stu-id="e4948-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="e4948-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4948-113">Remarks</span></span>

<span data-ttu-id="e4948-114">Esta estructura reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="e4948-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="e4948-115">Para usarlo, defina la estructura como se especificó anteriormente, `CLRDATA_ADDRESS` donde es un entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="e4948-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="e4948-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e4948-116">Requirements</span></span>

<span data-ttu-id="e4948-117">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4948-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e4948-118">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="e4948-118">**Header:** None</span></span>  
<span data-ttu-id="e4948-119">**Biblioteca** Ninguna</span><span class="sxs-lookup"><span data-stu-id="e4948-119">**Library:** None</span></span>   
<span data-ttu-id="e4948-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e4948-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e4948-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4948-121">See also</span></span>

- [<span data-ttu-id="e4948-122">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="e4948-122">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="e4948-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="e4948-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="e4948-124">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="e4948-124">Debugging Structures</span></span>](debugging-structures.md)
