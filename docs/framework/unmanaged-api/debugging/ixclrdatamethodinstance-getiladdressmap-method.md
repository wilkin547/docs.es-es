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
ms.openlocfilehash: 0acfa9ffd6f4bc3be567855008dccd08c9c74153
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420921"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a><span data-ttu-id="3aa92-102">IXCLRDataMethodInstance:: GetILAddressMap (método)</span><span class="sxs-lookup"><span data-stu-id="3aa92-102">IXCLRDataMethodInstance::GetILAddressMap Method</span></span>

<span data-ttu-id="3aa92-103">Obtiene el IL para direccionar la información de asignación.</span><span class="sxs-lookup"><span data-stu-id="3aa92-103">Gets the IL to address mapping information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="3aa92-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3aa92-104">Syntax</span></span>

```cpp
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

## <a name="parameters"></a><span data-ttu-id="3aa92-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3aa92-105">Parameters</span></span>

`mapLen`\
<span data-ttu-id="3aa92-106">de La longitud de la matriz de asignaciones proporcionada.</span><span class="sxs-lookup"><span data-stu-id="3aa92-106">[in] The length of the provided maps array.</span></span>

`mapNeeded`\
<span data-ttu-id="3aa92-107">enuncia El número de entradas de mapa que necesita el método.</span><span class="sxs-lookup"><span data-stu-id="3aa92-107">[out] The number of map entries that the method needs.</span></span>

`maps`\
<span data-ttu-id="3aa92-108">[out, size_is (Arcen)] Matriz para almacenar las entradas de asignación.</span><span class="sxs-lookup"><span data-stu-id="3aa92-108">[out, size_is(mapLen)] The array for storing the map entries.</span></span>

## <a name="remarks"></a><span data-ttu-id="3aa92-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3aa92-109">Remarks</span></span>

<span data-ttu-id="3aa92-110">El método proporcionado forma parte de la `IXCLRDataMethodInstance` interfaz y corresponde a la ranura 15 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="3aa92-110">The provided method is part of the `IXCLRDataMethodInstance` interface and corresponds to the 15th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="3aa92-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3aa92-111">Requirements</span></span>

<span data-ttu-id="3aa92-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3aa92-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="3aa92-113">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="3aa92-113">**Header:** None</span></span>  
<span data-ttu-id="3aa92-114">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="3aa92-114">**Library:** None</span></span>  
<span data-ttu-id="3aa92-115">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3aa92-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3aa92-116">Consulta también</span><span class="sxs-lookup"><span data-stu-id="3aa92-116">See also</span></span>

- [<span data-ttu-id="3aa92-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="3aa92-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="3aa92-118">Interfaz IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="3aa92-118">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
