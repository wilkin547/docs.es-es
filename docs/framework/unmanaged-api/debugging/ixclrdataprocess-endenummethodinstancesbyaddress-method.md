---
title: 'IXCLRDataProcess:: EndEnumMethodInstancesByAddress (método)'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 04ce8f44b0c9f532951666de7bfb9de475c14746
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395252"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a><span data-ttu-id="612d6-102">IXCLRDataProcess:: EndEnumMethodInstancesByAddress (método)</span><span class="sxs-lookup"><span data-stu-id="612d6-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="612d6-103">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="612d6-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="612d6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="612d6-104">Syntax</span></span>

```cpp
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="612d6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="612d6-105">Parameters</span></span>

`handle`\
<span data-ttu-id="612d6-106">enuncia Identificador para enumerar las instancias de método.</span><span class="sxs-lookup"><span data-stu-id="612d6-106">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="612d6-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="612d6-107">Remarks</span></span>

<span data-ttu-id="612d6-108">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura del 30 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="612d6-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 30th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="612d6-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="612d6-109">Requirements</span></span>

<span data-ttu-id="612d6-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="612d6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="612d6-111">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="612d6-111">**Header:** None</span></span>  
<span data-ttu-id="612d6-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="612d6-112">**Library:** None</span></span>  
<span data-ttu-id="612d6-113">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="612d6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="612d6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="612d6-114">See also</span></span>

- [<span data-ttu-id="612d6-115">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="612d6-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="612d6-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="612d6-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="612d6-117">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="612d6-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
