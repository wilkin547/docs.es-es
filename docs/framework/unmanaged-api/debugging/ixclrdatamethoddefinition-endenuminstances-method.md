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
ms.openlocfilehash: 605a4244d20ef6c0b7af3c2b26b65ff2a63fa9dd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790456"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="dbe08-102">IXCLRDataMethodDefinition:: EndEnumInstances (método)</span><span class="sxs-lookup"><span data-stu-id="dbe08-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="dbe08-103">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="dbe08-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="dbe08-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dbe08-104">Syntax</span></span>

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="dbe08-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="dbe08-105">Parameters</span></span>

`handle`\
<span data-ttu-id="dbe08-106">enuncia Identificador para enumerar las instancias de.</span><span class="sxs-lookup"><span data-stu-id="dbe08-106">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="dbe08-107">Notas</span><span class="sxs-lookup"><span data-stu-id="dbe08-107">Remarks</span></span>

<span data-ttu-id="dbe08-108">El método proporcionado forma parte de la interfaz `IXCLRDataMethodDefinition` y corresponde a la quinta ranura de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="dbe08-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fifth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="dbe08-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="dbe08-109">Requirements</span></span>

<span data-ttu-id="dbe08-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbe08-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="dbe08-111">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="dbe08-111">**Header:** None</span></span>  
<span data-ttu-id="dbe08-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="dbe08-112">**Library:** None</span></span>  
<span data-ttu-id="dbe08-113">**.NET Framework versiones:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dbe08-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="dbe08-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbe08-114">See also</span></span>

- [<span data-ttu-id="dbe08-115">Depuración</span><span class="sxs-lookup"><span data-stu-id="dbe08-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="dbe08-116">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="dbe08-116">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
