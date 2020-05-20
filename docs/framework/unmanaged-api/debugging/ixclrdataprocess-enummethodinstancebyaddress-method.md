---
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
ms.openlocfilehash: 142099ae5cf9637cc28e8c82aabcd831cc8f0f52
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420804"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="98229-102">IXCLRDataProcess:: EnumMethodInstanceByAddress (método)</span><span class="sxs-lookup"><span data-stu-id="98229-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="98229-103">Enumera las instancias de método de este proceso a partir de un desplazamiento de dirección.</span><span class="sxs-lookup"><span data-stu-id="98229-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="98229-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98229-104">Syntax</span></span>

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="98229-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="98229-105">Parameters</span></span>

`handle`\
<span data-ttu-id="98229-106">de Identificador para enumerar las instancias de método.</span><span class="sxs-lookup"><span data-stu-id="98229-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="98229-107">enuncia Instancia de método enumerado.</span><span class="sxs-lookup"><span data-stu-id="98229-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="98229-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="98229-108">Remarks</span></span>

<span data-ttu-id="98229-109">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura 29 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="98229-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 29th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="98229-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98229-110">Requirements</span></span>

<span data-ttu-id="98229-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98229-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="98229-112">**Encabezado:** Ninguna **biblioteca:** ninguna **.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="98229-112">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="98229-113">Consulta también</span><span class="sxs-lookup"><span data-stu-id="98229-113">See also</span></span>

- [<span data-ttu-id="98229-114">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="98229-114">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="98229-115">Depuración</span><span class="sxs-lookup"><span data-stu-id="98229-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="98229-116">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="98229-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
