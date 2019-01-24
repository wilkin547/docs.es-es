---
title: Método IXCLRDataMethodInstance::GetILAddressMap
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
ms.openlocfilehash: 8442d1373ede241d262ab41928fd5d9924ec9c80
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567196"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a><span data-ttu-id="ce3e2-102">Método IXCLRDataMethodInstance::GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="ce3e2-102">IXCLRDataMethodInstance::GetILAddressMap Method</span></span>

<span data-ttu-id="ce3e2-103">Obtiene el IL a la información de asignación de dirección.</span><span class="sxs-lookup"><span data-stu-id="ce3e2-103">Gets the IL to address mapping information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ce3e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce3e2-104">Syntax</span></span>

```
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

### <a name="parameters"></a><span data-ttu-id="ce3e2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ce3e2-105">Parameters</span></span>

<span data-ttu-id="ce3e2-106">`mapLen` [in] La longitud de la matriz proporcionada de mapas.</span><span class="sxs-lookup"><span data-stu-id="ce3e2-106">`mapLen` [in] The length of the provided maps array.</span></span>

<span data-ttu-id="ce3e2-107">`mapNeeded` [out] El número de entradas de mapa que necesita el método.</span><span class="sxs-lookup"><span data-stu-id="ce3e2-107">`mapNeeded` [out] The number of map entries that the method needs.</span></span>

<span data-ttu-id="ce3e2-108">`maps` [out, size_is(mapLen)] La matriz para almacenar las entradas de mapa.</span><span class="sxs-lookup"><span data-stu-id="ce3e2-108">`maps` [out, size_is(mapLen)] The array for storing the map entries.</span></span>

## <a name="remarks"></a><span data-ttu-id="ce3e2-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ce3e2-109">Remarks</span></span>

<span data-ttu-id="ce3e2-110">El método proporcionado forma parte de la `IXCLRDataMethodInstance` interfaz y corresponde a la ranura de la tabla de métodos virtuales 14.</span><span class="sxs-lookup"><span data-stu-id="ce3e2-110">The provided method is part of the `IXCLRDataMethodInstance` interface and corresponds to the 14th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="ce3e2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce3e2-111">Requirements</span></span>

<span data-ttu-id="ce3e2-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce3e2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ce3e2-113">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="ce3e2-113">**Header:** None</span></span>  
<span data-ttu-id="ce3e2-114">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="ce3e2-114">**Library:** None</span></span>  
<span data-ttu-id="ce3e2-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ce3e2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ce3e2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce3e2-116">See also</span></span>

- [<span data-ttu-id="ce3e2-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="ce3e2-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="ce3e2-118">Interfaz IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="ce3e2-118">IXCLRDataMethodInstance Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md)
