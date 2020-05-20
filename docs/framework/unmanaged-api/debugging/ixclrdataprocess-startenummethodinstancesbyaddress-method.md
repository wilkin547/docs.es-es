---
title: 'IXCLRDataProcess:: StartEnumMethodInstancesByAddress (método)'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 52d533f1c86b34b7b9febade8590e7ab58d8221e
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420740"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="27011-102">IXCLRDataProcess:: StartEnumMethodInstancesByAddress (método)</span><span class="sxs-lookup"><span data-stu-id="27011-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="27011-103">Proporciona un identificador para enumerar las instancias de método de que `AppDomain` empiezan en una dirección determinada.</span><span class="sxs-lookup"><span data-stu-id="27011-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="27011-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27011-104">Syntax</span></span>

```cpp
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

## <a name="parameters"></a><span data-ttu-id="27011-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="27011-105">Parameters</span></span>

`address`\
<span data-ttu-id="27011-106">de Dirección de la primera instancia de método.</span><span class="sxs-lookup"><span data-stu-id="27011-106">[in] The address of the first method instance.</span></span>

`appDomain`\
<span data-ttu-id="27011-107">de AppDomain de las instancias de método.</span><span class="sxs-lookup"><span data-stu-id="27011-107">[in] The AppDomain of the method instances.</span></span>

`handle`\
<span data-ttu-id="27011-108">enuncia Identificador para enumerar las instancias de método.</span><span class="sxs-lookup"><span data-stu-id="27011-108">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="27011-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="27011-109">Remarks</span></span>

<span data-ttu-id="27011-110">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura 28 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="27011-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="27011-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27011-111">Requirements</span></span>

<span data-ttu-id="27011-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27011-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="27011-113">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="27011-113">**Header:** None</span></span>  
<span data-ttu-id="27011-114">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="27011-114">**Library:** None</span></span>  
<span data-ttu-id="27011-115">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="27011-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="27011-116">Consulta también</span><span class="sxs-lookup"><span data-stu-id="27011-116">See also</span></span>

- [<span data-ttu-id="27011-117">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="27011-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="27011-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="27011-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="27011-119">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="27011-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
