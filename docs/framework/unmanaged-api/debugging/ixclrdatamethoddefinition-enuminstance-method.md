---
title: 'IXCLRDataMethodDefinition:: EnumInstance (método)'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EnumInstance Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: ae1ef2a3c8cf9e042ab9ab233ed993f8e36b2fce
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420947"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="e11b1-102">IXCLRDataMethodDefinition:: EnumInstance (método)</span><span class="sxs-lookup"><span data-stu-id="e11b1-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="e11b1-103">Enumera las instancias de esta definición de método.</span><span class="sxs-lookup"><span data-stu-id="e11b1-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e11b1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e11b1-104">Syntax</span></span>

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="e11b1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e11b1-105">Parameters</span></span>

`handle`\
<span data-ttu-id="e11b1-106">[in, out] Identificador para enumerar las instancias de.</span><span class="sxs-lookup"><span data-stu-id="e11b1-106">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="e11b1-107">enuncia Instancia enumerada.</span><span class="sxs-lookup"><span data-stu-id="e11b1-107">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="e11b1-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e11b1-108">Remarks</span></span>

<span data-ttu-id="e11b1-109">El método proporcionado forma parte de la `IXCLRDataMethodDefinition` interfaz y corresponde a la sexta ranura de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="e11b1-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 6th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="e11b1-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e11b1-110">Requirements</span></span>

<span data-ttu-id="e11b1-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e11b1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e11b1-112">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="e11b1-112">**Header:** None</span></span>  
<span data-ttu-id="e11b1-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="e11b1-113">**Library:** None</span></span>  
<span data-ttu-id="e11b1-114">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e11b1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e11b1-115">Consulta también</span><span class="sxs-lookup"><span data-stu-id="e11b1-115">See also</span></span>

- [<span data-ttu-id="e11b1-116">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="e11b1-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="e11b1-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="e11b1-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="e11b1-118">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="e11b1-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="e11b1-119">Interfaz IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="e11b1-119">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
