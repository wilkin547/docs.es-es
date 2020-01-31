---
title: Estructura DacpGetModuleAddress
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress Structure
helpviewer.keywords:
- DacpGetModuleAddress Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 1e3a62de3259c012438c64ece26e696682ec96e6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789202"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="1742e-102">Estructura DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="1742e-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="1742e-103">Define el contenedor para una solicitud de dirección del módulo.</span><span class="sxs-lookup"><span data-stu-id="1742e-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="1742e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1742e-104">Syntax</span></span>

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="1742e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="1742e-105">Members</span></span>

| <span data-ttu-id="1742e-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="1742e-106">Member</span></span>      | <span data-ttu-id="1742e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1742e-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="1742e-108">Puntero al módulo.</span><span class="sxs-lookup"><span data-stu-id="1742e-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="1742e-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="1742e-109">Methods</span></span>

| <span data-ttu-id="1742e-110">Método</span><span class="sxs-lookup"><span data-stu-id="1742e-110">Method</span></span>                                                                                               | <span data-ttu-id="1742e-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="1742e-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="1742e-112">Solicitud</span><span class="sxs-lookup"><span data-stu-id="1742e-112">Request</span></span>](dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="1742e-113">Realiza una solicitud para rellenar la estructura a partir de la estructura en tiempo de ejecución especificada.</span><span class="sxs-lookup"><span data-stu-id="1742e-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="1742e-114">Notas</span><span class="sxs-lookup"><span data-stu-id="1742e-114">Remarks</span></span>

<span data-ttu-id="1742e-115">Esta estructura reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="1742e-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="1742e-116">Para usarlo, defina la estructura como se especificó anteriormente, donde `CLRDATA_ADDRESS` es un entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="1742e-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="1742e-117">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="1742e-117">Requirements</span></span>
<span data-ttu-id="1742e-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1742e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="1742e-119">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="1742e-119">**Header:** None</span></span>  
<span data-ttu-id="1742e-120">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="1742e-120">**Library:** None</span></span>  
<span data-ttu-id="1742e-121">**.NET Framework versiones:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1742e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1742e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="1742e-122">See also</span></span>

- [<span data-ttu-id="1742e-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="1742e-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="1742e-124">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="1742e-124">Debugging Structures</span></span>](debugging-structures.md)
