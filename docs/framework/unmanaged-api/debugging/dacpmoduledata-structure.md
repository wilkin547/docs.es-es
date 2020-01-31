---
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
ms.openlocfilehash: b46a04d67f59c5031b5bd195cef4cc2275e1e5e0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793807"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="1629b-102">Estructura DacpModuleData</span><span class="sxs-lookup"><span data-stu-id="1629b-102">DacpModuleData Structure</span></span>

<span data-ttu-id="1629b-103">Define un búfer de transporte para la información de tiempo de ejecución de un módulo.</span><span class="sxs-lookup"><span data-stu-id="1629b-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="1629b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1629b-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File; 
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="1629b-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="1629b-105">Members</span></span>

| <span data-ttu-id="1629b-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="1629b-106">Member</span></span>    | <span data-ttu-id="1629b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1629b-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="1629b-108">Dirección del objeto de módulo.</span><span class="sxs-lookup"><span data-stu-id="1629b-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="1629b-109">Puntero al archivo portable ejecutable (PE).</span><span class="sxs-lookup"><span data-stu-id="1629b-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="1629b-110">Dirección de la base de la imagen cargada.</span><span class="sxs-lookup"><span data-stu-id="1629b-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="1629b-111">Búfer de carga para la información adicional del módulo que utiliza el motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1629b-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="1629b-112">Notas</span><span class="sxs-lookup"><span data-stu-id="1629b-112">Remarks</span></span>

<span data-ttu-id="1629b-113">Esta estructura reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="1629b-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="1629b-114">Para usarlo, defina la estructura tal y como se especificó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1629b-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="1629b-115">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="1629b-115">Requirements</span></span>
<span data-ttu-id="1629b-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1629b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="1629b-117">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="1629b-117">**Header:** None</span></span>  
<span data-ttu-id="1629b-118">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="1629b-118">**Library:** None</span></span>  
<span data-ttu-id="1629b-119">**.NET Framework versiones:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1629b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1629b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1629b-120">See also</span></span>

- [<span data-ttu-id="1629b-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="1629b-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="1629b-122">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="1629b-122">Debugging Structures</span></span>](debugging-structures.md)
