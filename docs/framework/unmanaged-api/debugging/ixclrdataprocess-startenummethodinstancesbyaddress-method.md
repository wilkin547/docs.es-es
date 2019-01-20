---
title: Método IXCLRDataProcess::StartEnumMethodInstancesByAddress
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
ms.openlocfilehash: 88ce9dd928871d71058fe28c243a9fb51b729778
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416686"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="be89b-102">Método IXCLRDataProcess::StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="be89b-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="be89b-103">Proporciona un identificador para enumerar las instancias de método de `AppDomain` a partir de una dirección determinada.</span><span class="sxs-lookup"><span data-stu-id="be89b-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="be89b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be89b-104">Syntax</span></span>

```
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

### <a name="parameters"></a><span data-ttu-id="be89b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="be89b-105">Parameters</span></span>

<span data-ttu-id="be89b-106">`address` [in] La dirección de la primera instancia de método.</span><span class="sxs-lookup"><span data-stu-id="be89b-106">`address` [in] The address of the first method instance.</span></span>

<span data-ttu-id="be89b-107">`appDomain` [in] El dominio de aplicación de las instancias de método.</span><span class="sxs-lookup"><span data-stu-id="be89b-107">`appDomain` [in] The AppDomain of the method instances.</span></span>

<span data-ttu-id="be89b-108">`handle` [out] Un identificador para enumerar las instancias de método.</span><span class="sxs-lookup"><span data-stu-id="be89b-108">`handle` [out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="be89b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="be89b-109">Remarks</span></span>

<span data-ttu-id="be89b-110">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura de la tabla de métodos virtuales 27.</span><span class="sxs-lookup"><span data-stu-id="be89b-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 27th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="be89b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="be89b-111">Requirements</span></span>

<span data-ttu-id="be89b-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be89b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="be89b-113">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="be89b-113">**Header:** None</span></span>  
<span data-ttu-id="be89b-114">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="be89b-114">**Library:** None</span></span>  
<span data-ttu-id="be89b-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="be89b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="be89b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="be89b-116">See Also</span></span>

- [<span data-ttu-id="be89b-117">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="be89b-117">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="be89b-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="be89b-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="be89b-119">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="be89b-119">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
