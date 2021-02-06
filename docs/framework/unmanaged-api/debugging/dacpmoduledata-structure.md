---
description: 'Más información acerca de: estructura DacpModuleData'
title: Estructura DacpModuleData
ms.date: 02/01/2019
api.name:
- DacpModuleData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpModuleData Structure
helpviewer.keywords:
- DacpModuleData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 376a49ab78db08e5906e8d33389cdc45fe76e81e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661589"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="56a9a-103">Estructura DacpModuleData</span><span class="sxs-lookup"><span data-stu-id="56a9a-103">DacpModuleData Structure</span></span>

<span data-ttu-id="56a9a-104">Define un búfer de transporte para la información de tiempo de ejecución de un módulo.</span><span class="sxs-lookup"><span data-stu-id="56a9a-104">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="56a9a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56a9a-105">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File;
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="56a9a-106">Members</span><span class="sxs-lookup"><span data-stu-id="56a9a-106">Members</span></span>

| <span data-ttu-id="56a9a-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="56a9a-107">Member</span></span>    | <span data-ttu-id="56a9a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="56a9a-108">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="56a9a-109">Dirección del objeto de módulo.</span><span class="sxs-lookup"><span data-stu-id="56a9a-109">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="56a9a-110">Puntero al archivo portable ejecutable (PE).</span><span class="sxs-lookup"><span data-stu-id="56a9a-110">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="56a9a-111">Dirección de la base de la imagen cargada.</span><span class="sxs-lookup"><span data-stu-id="56a9a-111">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="56a9a-112">Búfer de carga para la información adicional del módulo que utiliza el motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="56a9a-112">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="56a9a-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="56a9a-113">Remarks</span></span>

<span data-ttu-id="56a9a-114">Esta estructura reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="56a9a-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="56a9a-115">Para usarlo, defina la estructura tal y como se especificó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="56a9a-115">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="56a9a-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56a9a-116">Requirements</span></span>

<span data-ttu-id="56a9a-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56a9a-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="56a9a-118">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="56a9a-118">**Header:** None</span></span>  
<span data-ttu-id="56a9a-119">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="56a9a-119">**Library:** None</span></span>  
<span data-ttu-id="56a9a-120">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="56a9a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="56a9a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="56a9a-121">See also</span></span>

- [<span data-ttu-id="56a9a-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="56a9a-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="56a9a-123">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="56a9a-123">Debugging Structures</span></span>](debugging-structures.md)
