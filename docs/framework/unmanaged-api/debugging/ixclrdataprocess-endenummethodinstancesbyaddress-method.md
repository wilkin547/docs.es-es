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
ms.openlocfilehash: 5960d08ccfc09010a20d28a22c2e2f3f5b339c7d
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420833"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a><span data-ttu-id="1ecb5-102">IXCLRDataProcess:: EndEnumMethodInstancesByAddress (método)</span><span class="sxs-lookup"><span data-stu-id="1ecb5-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="1ecb5-103">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="1ecb5-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="1ecb5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ecb5-104">Syntax</span></span>

```cpp
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="1ecb5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1ecb5-105">Parameters</span></span>

`handle`\
<span data-ttu-id="1ecb5-106">enuncia Identificador para enumerar las instancias de método.</span><span class="sxs-lookup"><span data-stu-id="1ecb5-106">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="1ecb5-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1ecb5-107">Remarks</span></span>

<span data-ttu-id="1ecb5-108">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura del 30 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="1ecb5-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 30th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="1ecb5-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ecb5-109">Requirements</span></span>

<span data-ttu-id="1ecb5-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ecb5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="1ecb5-111">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="1ecb5-111">**Header:** None</span></span>  
<span data-ttu-id="1ecb5-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="1ecb5-112">**Library:** None</span></span>  
<span data-ttu-id="1ecb5-113">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1ecb5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1ecb5-114">Consulta también</span><span class="sxs-lookup"><span data-stu-id="1ecb5-114">See also</span></span>

- [<span data-ttu-id="1ecb5-115">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="1ecb5-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="1ecb5-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="1ecb5-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="1ecb5-117">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="1ecb5-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
