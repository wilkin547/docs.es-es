---
description: 'Más información sobre: IXCLRDataProcess:: EnumMethodInstanceByAddress (método)'
title: 'IXCLRDataProcess:: EnumMethodInstanceByAddress (método)'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a0d59956288e39be188628d10c63a52d09d17638
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800700"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="4ce5e-103">IXCLRDataProcess:: EnumMethodInstanceByAddress (método)</span><span class="sxs-lookup"><span data-stu-id="4ce5e-103">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="4ce5e-104">Enumera las instancias de método de este proceso a partir de un desplazamiento de dirección.</span><span class="sxs-lookup"><span data-stu-id="4ce5e-104">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="4ce5e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ce5e-105">Syntax</span></span>

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="4ce5e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4ce5e-106">Parameters</span></span>

`handle`\
<span data-ttu-id="4ce5e-107">de Identificador para enumerar las instancias de método.</span><span class="sxs-lookup"><span data-stu-id="4ce5e-107">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="4ce5e-108">enuncia Instancia de método enumerado.</span><span class="sxs-lookup"><span data-stu-id="4ce5e-108">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="4ce5e-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4ce5e-109">Remarks</span></span>

<span data-ttu-id="4ce5e-110">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura 29 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="4ce5e-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 29th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="4ce5e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4ce5e-111">Requirements</span></span>

<span data-ttu-id="4ce5e-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ce5e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="4ce5e-113">**Encabezado:** Ninguna **biblioteca:** ninguna **.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4ce5e-113">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4ce5e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ce5e-114">See also</span></span>

- [<span data-ttu-id="4ce5e-115">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="4ce5e-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="4ce5e-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="4ce5e-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="4ce5e-117">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="4ce5e-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
