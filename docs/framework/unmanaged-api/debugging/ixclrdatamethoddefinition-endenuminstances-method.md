---
title: Método IXCLRDataMethodDefinition::EndEnumInstances
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EndEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 3d9e3ca31eddff9d08607c4d6d37ca76139bf5d2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756312"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="59337-102">Método IXCLRDataMethodDefinition::EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="59337-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="59337-103">Libera los recursos utilizados por los iteradores internos usa durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="59337-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="59337-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59337-104">Syntax</span></span>

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="59337-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="59337-105">Parameters</span></span>

`handle`\
<span data-ttu-id="59337-106">[out] Un identificador para enumerar las instancias.</span><span class="sxs-lookup"><span data-stu-id="59337-106">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="59337-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="59337-107">Remarks</span></span>

<span data-ttu-id="59337-108">El método proporcionado forma parte de la `IXCLRDataMethodDefinition` interfaz y corresponde a la ranura de la tabla de métodos virtuales quinta.</span><span class="sxs-lookup"><span data-stu-id="59337-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fifth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="59337-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59337-109">Requirements</span></span>

<span data-ttu-id="59337-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59337-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="59337-111">**Encabezado**: None</span><span class="sxs-lookup"><span data-stu-id="59337-111">**Header:** None</span></span>  
<span data-ttu-id="59337-112">**Biblioteca:** None</span><span class="sxs-lookup"><span data-stu-id="59337-112">**Library:** None</span></span>  
<span data-ttu-id="59337-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="59337-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="59337-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="59337-114">See also</span></span>

- [<span data-ttu-id="59337-115">Depuración</span><span class="sxs-lookup"><span data-stu-id="59337-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="59337-116">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="59337-116">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
