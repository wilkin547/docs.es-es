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
ms.openlocfilehash: 5e6fde6e4e5bf006da00b62b035cee112efae1d7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373496"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a><span data-ttu-id="fe4da-102">Método IXCLRDataMethodInstance::GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="fe4da-102">IXCLRDataMethodInstance::GetILAddressMap Method</span></span>

<span data-ttu-id="fe4da-103">Obtiene el IL a la información de asignación de dirección.</span><span class="sxs-lookup"><span data-stu-id="fe4da-103">Gets the IL to address mapping information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="fe4da-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe4da-104">Syntax</span></span>

```
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

### <a name="parameters"></a><span data-ttu-id="fe4da-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fe4da-105">Parameters</span></span>

`mapLen`\
<span data-ttu-id="fe4da-106">[in] La longitud de la matriz proporcionada de mapas.</span><span class="sxs-lookup"><span data-stu-id="fe4da-106">[in] The length of the provided maps array.</span></span>

`mapNeeded`\
<span data-ttu-id="fe4da-107">[out] El número de entradas de mapa que necesita el método.</span><span class="sxs-lookup"><span data-stu-id="fe4da-107">[out] The number of map entries that the method needs.</span></span>

`maps`\
<span data-ttu-id="fe4da-108">[out, size_is(mapLen)] La matriz para almacenar las entradas de mapa.</span><span class="sxs-lookup"><span data-stu-id="fe4da-108">[out, size_is(mapLen)] The array for storing the map entries.</span></span>

## <a name="remarks"></a><span data-ttu-id="fe4da-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fe4da-109">Remarks</span></span>

<span data-ttu-id="fe4da-110">El método proporcionado forma parte de la `IXCLRDataMethodInstance` interfaz y corresponde a la ranura de la tabla de métodos virtuales 14.</span><span class="sxs-lookup"><span data-stu-id="fe4da-110">The provided method is part of the `IXCLRDataMethodInstance` interface and corresponds to the 14th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="fe4da-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe4da-111">Requirements</span></span>

<span data-ttu-id="fe4da-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe4da-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="fe4da-113">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="fe4da-113">**Header:** None</span></span>  
<span data-ttu-id="fe4da-114">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="fe4da-114">**Library:** None</span></span>  
<span data-ttu-id="fe4da-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fe4da-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="fe4da-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe4da-116">See also</span></span>

- [<span data-ttu-id="fe4da-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="fe4da-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="fe4da-118">Interfaz IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="fe4da-118">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
