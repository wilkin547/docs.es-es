---
description: 'Más información sobre: IXCLRDataMethodInstance:: GetILAddressMap (método)'
title: 'IXCLRDataMethodInstance:: GetILAddressMap (método)'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodInstance::GetILAddressMap Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method
helpviewer.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: ddddf593c3c18f2b4cd1682b5d6f7c8ff1985ac6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800817"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a><span data-ttu-id="ad91b-103">IXCLRDataMethodInstance:: GetILAddressMap (método)</span><span class="sxs-lookup"><span data-stu-id="ad91b-103">IXCLRDataMethodInstance::GetILAddressMap Method</span></span>

<span data-ttu-id="ad91b-104">Obtiene el IL para direccionar la información de asignación.</span><span class="sxs-lookup"><span data-stu-id="ad91b-104">Gets the IL to address mapping information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ad91b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad91b-105">Syntax</span></span>

```cpp
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

## <a name="parameters"></a><span data-ttu-id="ad91b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ad91b-106">Parameters</span></span>

`mapLen`\
<span data-ttu-id="ad91b-107">de La longitud de la matriz de asignaciones proporcionada.</span><span class="sxs-lookup"><span data-stu-id="ad91b-107">[in] The length of the provided maps array.</span></span>

`mapNeeded`\
<span data-ttu-id="ad91b-108">enuncia El número de entradas de mapa que necesita el método.</span><span class="sxs-lookup"><span data-stu-id="ad91b-108">[out] The number of map entries that the method needs.</span></span>

`maps`\
<span data-ttu-id="ad91b-109">[out, size_is (Arcen)] Matriz para almacenar las entradas de asignación.</span><span class="sxs-lookup"><span data-stu-id="ad91b-109">[out, size_is(mapLen)] The array for storing the map entries.</span></span>

## <a name="remarks"></a><span data-ttu-id="ad91b-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ad91b-110">Remarks</span></span>

<span data-ttu-id="ad91b-111">El método proporcionado forma parte de la `IXCLRDataMethodInstance` interfaz y corresponde a la ranura 15 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="ad91b-111">The provided method is part of the `IXCLRDataMethodInstance` interface and corresponds to the 15th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="ad91b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad91b-112">Requirements</span></span>

<span data-ttu-id="ad91b-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad91b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ad91b-114">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="ad91b-114">**Header:** None</span></span>  
<span data-ttu-id="ad91b-115">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="ad91b-115">**Library:** None</span></span>  
<span data-ttu-id="ad91b-116">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ad91b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ad91b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad91b-117">See also</span></span>

- [<span data-ttu-id="ad91b-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="ad91b-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="ad91b-119">Interfaz IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="ad91b-119">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
