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
ms.openlocfilehash: c24bdce64eb7e208bf3830940d7beab1ebf92e78
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179187"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="0030e-102">Estructura DacpModuleData</span><span class="sxs-lookup"><span data-stu-id="0030e-102">DacpModuleData Structure</span></span>

<span data-ttu-id="0030e-103">Define un búfer de transporte para la información de tiempo de ejecución de un módulo.</span><span class="sxs-lookup"><span data-stu-id="0030e-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="0030e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0030e-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File;
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="0030e-105">Members</span><span class="sxs-lookup"><span data-stu-id="0030e-105">Members</span></span>

| <span data-ttu-id="0030e-106">Member</span><span class="sxs-lookup"><span data-stu-id="0030e-106">Member</span></span>    | <span data-ttu-id="0030e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0030e-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="0030e-108">Dirección del objeto module.</span><span class="sxs-lookup"><span data-stu-id="0030e-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="0030e-109">Un puntero al archivo ejecutable portátil (PE).</span><span class="sxs-lookup"><span data-stu-id="0030e-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="0030e-110">La dirección de la base de la imagen cargada.</span><span class="sxs-lookup"><span data-stu-id="0030e-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="0030e-111">Un búfer de carga útil para la información de módulo adicional utilizada por el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0030e-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="0030e-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0030e-112">Remarks</span></span>

<span data-ttu-id="0030e-113">Esta estructura se encuentra dentro del tiempo de ejecución y no se expone a través de encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="0030e-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="0030e-114">Para utilizarla, defina la estructura como se especificó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0030e-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="0030e-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0030e-115">Requirements</span></span>
<span data-ttu-id="0030e-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0030e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="0030e-117">**Encabezado:** Ninguno</span><span class="sxs-lookup"><span data-stu-id="0030e-117">**Header:** None</span></span>  
<span data-ttu-id="0030e-118">**Biblioteca:** Ninguno</span><span class="sxs-lookup"><span data-stu-id="0030e-118">**Library:** None</span></span>  
<span data-ttu-id="0030e-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0030e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="0030e-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0030e-120">See also</span></span>

- [<span data-ttu-id="0030e-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="0030e-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="0030e-122">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="0030e-122">Debugging Structures</span></span>](debugging-structures.md)
