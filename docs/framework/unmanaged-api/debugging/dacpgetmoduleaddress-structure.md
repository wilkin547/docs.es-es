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
ms.openlocfilehash: cbea6c0562c68ae5d18247dc97bc53eb9dfbfd7e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104115"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="81a9a-102">Estructura DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="81a9a-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="81a9a-103">Define el contenedor para una solicitud de dirección del módulo.</span><span class="sxs-lookup"><span data-stu-id="81a9a-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="81a9a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81a9a-104">Syntax</span></span>

```
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="81a9a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="81a9a-105">Members</span></span>

| <span data-ttu-id="81a9a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="81a9a-106">Member</span></span>      | <span data-ttu-id="81a9a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="81a9a-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="81a9a-108">Puntero al módulo.</span><span class="sxs-lookup"><span data-stu-id="81a9a-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="81a9a-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="81a9a-109">Methods</span></span>

| <span data-ttu-id="81a9a-110">Método</span><span class="sxs-lookup"><span data-stu-id="81a9a-110">Method</span></span>                                                                                               | <span data-ttu-id="81a9a-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="81a9a-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="81a9a-112">Solicitud</span><span class="sxs-lookup"><span data-stu-id="81a9a-112">Request</span></span>](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="81a9a-113">Realiza una solicitud para rellenar la estructura de la estructura de tiempo de ejecución determinado.</span><span class="sxs-lookup"><span data-stu-id="81a9a-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="81a9a-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="81a9a-114">Remarks</span></span>

<span data-ttu-id="81a9a-115">Esta estructura reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="81a9a-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="81a9a-116">Para ello, defina la estructura según lo especificado anteriormente, donde `CLRDATA_ADDRESS` es un entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="81a9a-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="81a9a-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81a9a-117">Requirements</span></span>
<span data-ttu-id="81a9a-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81a9a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="81a9a-119">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="81a9a-119">**Header:** None</span></span>  
<span data-ttu-id="81a9a-120">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="81a9a-120">**Library:** None</span></span>  
<span data-ttu-id="81a9a-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="81a9a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="81a9a-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="81a9a-122">See also</span></span>

- [<span data-ttu-id="81a9a-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="81a9a-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="81a9a-124">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="81a9a-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
