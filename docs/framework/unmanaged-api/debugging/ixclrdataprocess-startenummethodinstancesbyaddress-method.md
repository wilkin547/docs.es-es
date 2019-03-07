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
ms.openlocfilehash: 41b6ff0a3c44d3ad997c54b1c82590cc3583fe52
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474610"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="a63a3-102">Método IXCLRDataProcess::StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="a63a3-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="a63a3-103">Proporciona un identificador para enumerar las instancias de método de `AppDomain` a partir de una dirección determinada.</span><span class="sxs-lookup"><span data-stu-id="a63a3-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a63a3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a63a3-104">Syntax</span></span>

```
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

## <a name="parameters"></a><span data-ttu-id="a63a3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a63a3-105">Parameters</span></span>

`address`\
<span data-ttu-id="a63a3-106">[in] La dirección de la primera instancia de método.</span><span class="sxs-lookup"><span data-stu-id="a63a3-106">[in] The address of the first method instance.</span></span>

`appDomain`\
<span data-ttu-id="a63a3-107">[in] El dominio de aplicación de las instancias de método.</span><span class="sxs-lookup"><span data-stu-id="a63a3-107">[in] The AppDomain of the method instances.</span></span>

`handle`\
<span data-ttu-id="a63a3-108">[out] Un identificador para enumerar las instancias de método.</span><span class="sxs-lookup"><span data-stu-id="a63a3-108">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="a63a3-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a63a3-109">Remarks</span></span>

<span data-ttu-id="a63a3-110">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura de la tabla de métodos virtuales 27.</span><span class="sxs-lookup"><span data-stu-id="a63a3-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 27th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="a63a3-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a63a3-111">Requirements</span></span>

<span data-ttu-id="a63a3-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a63a3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="a63a3-113">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="a63a3-113">**Header:** None</span></span>  
<span data-ttu-id="a63a3-114">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="a63a3-114">**Library:** None</span></span>  
<span data-ttu-id="a63a3-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a63a3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="a63a3-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a63a3-116">See also</span></span>

- [<span data-ttu-id="a63a3-117">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="a63a3-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="a63a3-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="a63a3-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="a63a3-119">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="a63a3-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
