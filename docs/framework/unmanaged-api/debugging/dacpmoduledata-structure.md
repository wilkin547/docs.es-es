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
ms.openlocfilehash: 2e27082ba4c35bc10eb65139b2af6c81c10d79a6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739120"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="b3a14-102">Estructura DacpModuleData</span><span class="sxs-lookup"><span data-stu-id="b3a14-102">DacpModuleData Structure</span></span>

<span data-ttu-id="b3a14-103">Define un búfer de transporte para obtener información de tiempo de ejecución de un módulo.</span><span class="sxs-lookup"><span data-stu-id="b3a14-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b3a14-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b3a14-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File; 
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="b3a14-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b3a14-105">Members</span></span>

| <span data-ttu-id="b3a14-106">Member</span><span class="sxs-lookup"><span data-stu-id="b3a14-106">Member</span></span>    | <span data-ttu-id="b3a14-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b3a14-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="b3a14-108">Dirección del objeto de módulo.</span><span class="sxs-lookup"><span data-stu-id="b3a14-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="b3a14-109">Un puntero al archivo ejecutable portable (PE).</span><span class="sxs-lookup"><span data-stu-id="b3a14-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="b3a14-110">Básico de la dirección de la imagen cargada.</span><span class="sxs-lookup"><span data-stu-id="b3a14-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="b3a14-111">Un búfer de carga para obtener información de módulos adicionales utilizado por el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b3a14-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="b3a14-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b3a14-112">Remarks</span></span>

<span data-ttu-id="b3a14-113">Esta estructura reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="b3a14-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="b3a14-114">Para ello, defina la estructura según lo especificado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b3a14-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="b3a14-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3a14-115">Requirements</span></span>
<span data-ttu-id="b3a14-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3a14-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b3a14-117">**Encabezado**: None</span><span class="sxs-lookup"><span data-stu-id="b3a14-117">**Header:** None</span></span>  
<span data-ttu-id="b3a14-118">**Biblioteca:** None</span><span class="sxs-lookup"><span data-stu-id="b3a14-118">**Library:** None</span></span>  
<span data-ttu-id="b3a14-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b3a14-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b3a14-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3a14-120">See also</span></span>

- [<span data-ttu-id="b3a14-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="b3a14-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="b3a14-122">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="b3a14-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
