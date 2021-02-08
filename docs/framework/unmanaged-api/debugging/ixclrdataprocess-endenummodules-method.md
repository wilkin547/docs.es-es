---
description: 'Más información sobre: IXCLRDataProcess:: EndEnumModules (método)'
title: 'IXCLRDataProcess:: EndEnumModules (método)'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 454d4fa3616f9ba8312dc3d1ac02c228625aa488
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800713"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="5517d-103">IXCLRDataProcess:: EndEnumModules (método)</span><span class="sxs-lookup"><span data-stu-id="5517d-103">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="5517d-104">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de módulos.</span><span class="sxs-lookup"><span data-stu-id="5517d-104">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5517d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5517d-105">Syntax</span></span>

```cpp
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="5517d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5517d-106">Parameters</span></span>

`handle`\
<span data-ttu-id="5517d-107">enuncia Identificador para enumerar los módulos.</span><span class="sxs-lookup"><span data-stu-id="5517d-107">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="5517d-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5517d-108">Remarks</span></span>

<span data-ttu-id="5517d-109">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura del 26 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="5517d-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="5517d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5517d-110">Requirements</span></span>

<span data-ttu-id="5517d-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5517d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="5517d-112">**Encabezado:** Ninguna **biblioteca:** ninguna **.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5517d-112">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5517d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5517d-113">See also</span></span>

- [<span data-ttu-id="5517d-114">Depuración</span><span class="sxs-lookup"><span data-stu-id="5517d-114">Debugging</span></span>](index.md)
- [<span data-ttu-id="5517d-115">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="5517d-115">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
