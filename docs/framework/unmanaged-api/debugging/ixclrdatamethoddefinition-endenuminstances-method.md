---
description: 'Más información sobre: IXCLRDataMethodDefinition:: EndEnumInstances (método)'
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
ms.openlocfilehash: bfdcb9046b4983e6686410bf2ceadf7119b89e74
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790378"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="9f5f0-103">IXCLRDataMethodDefinition:: EndEnumInstances (método)</span><span class="sxs-lookup"><span data-stu-id="9f5f0-103">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="9f5f0-104">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="9f5f0-104">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9f5f0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f5f0-105">Syntax</span></span>

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="9f5f0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9f5f0-106">Parameters</span></span>

`handle`\
<span data-ttu-id="9f5f0-107">enuncia Identificador para enumerar las instancias de.</span><span class="sxs-lookup"><span data-stu-id="9f5f0-107">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="9f5f0-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9f5f0-108">Remarks</span></span>

<span data-ttu-id="9f5f0-109">El método proporcionado forma parte de la `IXCLRDataMethodDefinition` interfaz y corresponde a la séptima ranura de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="9f5f0-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 7th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="9f5f0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f5f0-110">Requirements</span></span>

<span data-ttu-id="9f5f0-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f5f0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9f5f0-112">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="9f5f0-112">**Header:** None</span></span>  
<span data-ttu-id="9f5f0-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="9f5f0-113">**Library:** None</span></span>  
<span data-ttu-id="9f5f0-114">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9f5f0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9f5f0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f5f0-115">See also</span></span>

- [<span data-ttu-id="9f5f0-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="9f5f0-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="9f5f0-117">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="9f5f0-117">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
