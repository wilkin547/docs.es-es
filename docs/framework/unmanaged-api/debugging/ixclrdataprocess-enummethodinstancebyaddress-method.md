---
title: IXCLRDataProcess::EnumMethodInstanceByAddress Método
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
ms.openlocfilehash: afc5fc377dd45d5e8d4d2d7b3385ca0524df69e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176661"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="4b3f4-102">IXCLRDataProcess::EnumMethodInstanceByAddress Método</span><span class="sxs-lookup"><span data-stu-id="4b3f4-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="4b3f4-103">Enumera las instancias de método de este proceso a partir de un desplazamiento de dirección.</span><span class="sxs-lookup"><span data-stu-id="4b3f4-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="4b3f4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b3f4-104">Syntax</span></span>

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="4b3f4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4b3f4-105">Parameters</span></span>

`handle`\
<span data-ttu-id="4b3f4-106">[en] Identificador para enumerar las instancias del método.</span><span class="sxs-lookup"><span data-stu-id="4b3f4-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="4b3f4-107">[fuera] La instancia del método enumerado.</span><span class="sxs-lookup"><span data-stu-id="4b3f4-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="4b3f4-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4b3f4-108">Remarks</span></span>

<span data-ttu-id="4b3f4-109">El método proporcionado forma `IXCLRDataProcess` parte de la interfaz y corresponde a la ranura 28 de la tabla de métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="4b3f4-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="4b3f4-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4b3f4-110">Requirements</span></span>

<span data-ttu-id="4b3f4-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b3f4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="4b3f4-112">**Encabezado:** Ninguna **biblioteca:** ninguna versión de **.NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4b3f4-112">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4b3f4-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4b3f4-113">See also</span></span>

- [<span data-ttu-id="4b3f4-114">CLRDataSourceType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="4b3f4-114">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="4b3f4-115">Depuración</span><span class="sxs-lookup"><span data-stu-id="4b3f4-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="4b3f4-116">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="4b3f4-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
