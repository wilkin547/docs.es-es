---
title: 'IXCLRDataMethodDefinition:: EndEnumInstances (método)'
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
ms.openlocfilehash: 7271c9594a679af205c404f59ff6731821aa0acf
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420999"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="e71c8-102">IXCLRDataMethodDefinition:: EndEnumInstances (método)</span><span class="sxs-lookup"><span data-stu-id="e71c8-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="e71c8-103">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="e71c8-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e71c8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e71c8-104">Syntax</span></span>

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="e71c8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e71c8-105">Parameters</span></span>

`handle`\
<span data-ttu-id="e71c8-106">enuncia Identificador para enumerar las instancias de.</span><span class="sxs-lookup"><span data-stu-id="e71c8-106">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="e71c8-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e71c8-107">Remarks</span></span>

<span data-ttu-id="e71c8-108">El método proporcionado forma parte de la `IXCLRDataMethodDefinition` interfaz y corresponde a la séptima ranura de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="e71c8-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 7th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="e71c8-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e71c8-109">Requirements</span></span>

<span data-ttu-id="e71c8-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e71c8-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e71c8-111">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="e71c8-111">**Header:** None</span></span>  
<span data-ttu-id="e71c8-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="e71c8-112">**Library:** None</span></span>  
<span data-ttu-id="e71c8-113">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e71c8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e71c8-114">Consulta también</span><span class="sxs-lookup"><span data-stu-id="e71c8-114">See also</span></span>

- [<span data-ttu-id="e71c8-115">Depuración</span><span class="sxs-lookup"><span data-stu-id="e71c8-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="e71c8-116">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="e71c8-116">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
