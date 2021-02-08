---
description: 'Más información sobre: IXCLRDataProcess:: StartEnumMethodInstancesByAddress (método)'
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
ms.openlocfilehash: 155d09192b60b8671435abb439f07dfbb290bc87
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800596"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="409a4-103">IXCLRDataProcess:: StartEnumMethodInstancesByAddress (método)</span><span class="sxs-lookup"><span data-stu-id="409a4-103">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="409a4-104">Proporciona un identificador para enumerar las instancias de método de que `AppDomain` empiezan en una dirección determinada.</span><span class="sxs-lookup"><span data-stu-id="409a4-104">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="409a4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="409a4-105">Syntax</span></span>

```cpp
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

## <a name="parameters"></a><span data-ttu-id="409a4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="409a4-106">Parameters</span></span>

`address`\
<span data-ttu-id="409a4-107">de Dirección de la primera instancia de método.</span><span class="sxs-lookup"><span data-stu-id="409a4-107">[in] The address of the first method instance.</span></span>

`appDomain`\
<span data-ttu-id="409a4-108">de AppDomain de las instancias de método.</span><span class="sxs-lookup"><span data-stu-id="409a4-108">[in] The AppDomain of the method instances.</span></span>

`handle`\
<span data-ttu-id="409a4-109">enuncia Identificador para enumerar las instancias de método.</span><span class="sxs-lookup"><span data-stu-id="409a4-109">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="409a4-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="409a4-110">Remarks</span></span>

<span data-ttu-id="409a4-111">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura 28 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="409a4-111">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="409a4-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="409a4-112">Requirements</span></span>

<span data-ttu-id="409a4-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="409a4-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="409a4-114">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="409a4-114">**Header:** None</span></span>  
<span data-ttu-id="409a4-115">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="409a4-115">**Library:** None</span></span>  
<span data-ttu-id="409a4-116">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="409a4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="409a4-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="409a4-117">See also</span></span>

- [<span data-ttu-id="409a4-118">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="409a4-118">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="409a4-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="409a4-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="409a4-120">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="409a4-120">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
