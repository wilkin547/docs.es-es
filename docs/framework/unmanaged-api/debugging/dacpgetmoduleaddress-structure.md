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
ms.openlocfilehash: e460264e2393858c028ba51aec4a4f2c01649994
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860826"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="f45d4-102">Estructura DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="f45d4-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="f45d4-103">Define el contenedor para una solicitud de dirección del módulo.</span><span class="sxs-lookup"><span data-stu-id="f45d4-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="f45d4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f45d4-104">Syntax</span></span>

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="f45d4-105">Members</span><span class="sxs-lookup"><span data-stu-id="f45d4-105">Members</span></span>

| <span data-ttu-id="f45d4-106">Member</span><span class="sxs-lookup"><span data-stu-id="f45d4-106">Member</span></span>      | <span data-ttu-id="f45d4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f45d4-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="f45d4-108">Puntero al módulo.</span><span class="sxs-lookup"><span data-stu-id="f45d4-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="f45d4-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="f45d4-109">Methods</span></span>

| <span data-ttu-id="f45d4-110">Método</span><span class="sxs-lookup"><span data-stu-id="f45d4-110">Method</span></span>                                                                                               | <span data-ttu-id="f45d4-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="f45d4-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="f45d4-112">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f45d4-112">Request</span></span>](dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="f45d4-113">Realiza una solicitud para rellenar la estructura a partir de la estructura en tiempo de ejecución especificada.</span><span class="sxs-lookup"><span data-stu-id="f45d4-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="f45d4-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f45d4-114">Remarks</span></span>

<span data-ttu-id="f45d4-115">Esta estructura reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="f45d4-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="f45d4-116">Para usarlo, defina la estructura como se especificó anteriormente, `CLRDATA_ADDRESS` donde es un entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="f45d4-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="f45d4-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f45d4-117">Requirements</span></span>
<span data-ttu-id="f45d4-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f45d4-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="f45d4-119">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="f45d4-119">**Header:** None</span></span>  
<span data-ttu-id="f45d4-120">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="f45d4-120">**Library:** None</span></span>  
<span data-ttu-id="f45d4-121">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f45d4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="f45d4-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f45d4-122">See also</span></span>

- [<span data-ttu-id="f45d4-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="f45d4-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="f45d4-124">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="f45d4-124">Debugging Structures</span></span>](debugging-structures.md)
