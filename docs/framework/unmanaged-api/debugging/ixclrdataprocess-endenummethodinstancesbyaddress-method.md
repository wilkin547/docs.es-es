---
description: 'Más información sobre: IXCLRDataProcess:: EndEnumMethodInstancesByAddress (método)'
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
ms.openlocfilehash: 2e01fe0737319a7b336d9f6992bf81b2c57f9e70
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800726"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a><span data-ttu-id="64306-103">IXCLRDataProcess:: EndEnumMethodInstancesByAddress (método)</span><span class="sxs-lookup"><span data-stu-id="64306-103">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="64306-104">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="64306-104">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="64306-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64306-105">Syntax</span></span>

```cpp
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="64306-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="64306-106">Parameters</span></span>

`handle`\
<span data-ttu-id="64306-107">enuncia Identificador para enumerar las instancias de método.</span><span class="sxs-lookup"><span data-stu-id="64306-107">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="64306-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="64306-108">Remarks</span></span>

<span data-ttu-id="64306-109">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura del 30 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="64306-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 30th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="64306-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64306-110">Requirements</span></span>

<span data-ttu-id="64306-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64306-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="64306-112">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="64306-112">**Header:** None</span></span>  
<span data-ttu-id="64306-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="64306-113">**Library:** None</span></span>  
<span data-ttu-id="64306-114">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="64306-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="64306-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="64306-115">See also</span></span>

- [<span data-ttu-id="64306-116">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="64306-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="64306-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="64306-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="64306-118">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="64306-118">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
