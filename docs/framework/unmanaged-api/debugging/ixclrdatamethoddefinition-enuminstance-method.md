---
description: 'Más información sobre: IXCLRDataMethodDefinition:: EnumInstance (método)'
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
ms.openlocfilehash: 4038dc4706b8362acaf9c13abd9c7326cce376a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790365"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="b2f4e-103">IXCLRDataMethodDefinition:: EnumInstance (método)</span><span class="sxs-lookup"><span data-stu-id="b2f4e-103">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="b2f4e-104">Enumera las instancias de esta definición de método.</span><span class="sxs-lookup"><span data-stu-id="b2f4e-104">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b2f4e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2f4e-105">Syntax</span></span>

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="b2f4e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b2f4e-106">Parameters</span></span>

`handle`\
<span data-ttu-id="b2f4e-107">[in, out] Identificador para enumerar las instancias de.</span><span class="sxs-lookup"><span data-stu-id="b2f4e-107">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="b2f4e-108">enuncia Instancia enumerada.</span><span class="sxs-lookup"><span data-stu-id="b2f4e-108">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="b2f4e-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b2f4e-109">Remarks</span></span>

<span data-ttu-id="b2f4e-110">El método proporcionado forma parte de la `IXCLRDataMethodDefinition` interfaz y corresponde a la sexta ranura de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="b2f4e-110">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 6th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="b2f4e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2f4e-111">Requirements</span></span>

<span data-ttu-id="b2f4e-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2f4e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b2f4e-113">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="b2f4e-113">**Header:** None</span></span>  
<span data-ttu-id="b2f4e-114">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="b2f4e-114">**Library:** None</span></span>  
<span data-ttu-id="b2f4e-115">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b2f4e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b2f4e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2f4e-116">See also</span></span>

- [<span data-ttu-id="b2f4e-117">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="b2f4e-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="b2f4e-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="b2f4e-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="b2f4e-119">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="b2f4e-119">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="b2f4e-120">Interfaz IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="b2f4e-120">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
