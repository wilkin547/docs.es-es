---
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
ms.openlocfilehash: 7c4dcf59ce159434d5012120043f5bb548d49731
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396812"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a><span data-ttu-id="2e846-102">IXCLRDataMethodInstance:: GetILAddressMap (método)</span><span class="sxs-lookup"><span data-stu-id="2e846-102">IXCLRDataMethodInstance::GetILAddressMap Method</span></span>

<span data-ttu-id="2e846-103">Obtiene el IL para direccionar la información de asignación.</span><span class="sxs-lookup"><span data-stu-id="2e846-103">Gets the IL to address mapping information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="2e846-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e846-104">Syntax</span></span>

```cpp
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

## <a name="parameters"></a><span data-ttu-id="2e846-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2e846-105">Parameters</span></span>

`mapLen`\
<span data-ttu-id="2e846-106">de La longitud de la matriz de asignaciones proporcionada.</span><span class="sxs-lookup"><span data-stu-id="2e846-106">[in] The length of the provided maps array.</span></span>

`mapNeeded`\
<span data-ttu-id="2e846-107">enuncia El número de entradas de mapa que necesita el método.</span><span class="sxs-lookup"><span data-stu-id="2e846-107">[out] The number of map entries that the method needs.</span></span>

`maps`\
<span data-ttu-id="2e846-108">[out, size_is (Arcen)] Matriz para almacenar las entradas de asignación.</span><span class="sxs-lookup"><span data-stu-id="2e846-108">[out, size_is(mapLen)] The array for storing the map entries.</span></span>

## <a name="remarks"></a><span data-ttu-id="2e846-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2e846-109">Remarks</span></span>

<span data-ttu-id="2e846-110">El método proporcionado forma parte de la `IXCLRDataMethodInstance` interfaz y corresponde a la ranura 15 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="2e846-110">The provided method is part of the `IXCLRDataMethodInstance` interface and corresponds to the 15th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="2e846-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e846-111">Requirements</span></span>

<span data-ttu-id="2e846-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e846-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="2e846-113">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="2e846-113">**Header:** None</span></span>  
<span data-ttu-id="2e846-114">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="2e846-114">**Library:** None</span></span>  
<span data-ttu-id="2e846-115">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2e846-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="2e846-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e846-116">See also</span></span>

- [<span data-ttu-id="2e846-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="2e846-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="2e846-118">Interfaz IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="2e846-118">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
