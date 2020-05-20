---
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
ms.openlocfilehash: 9a7a23e53f5c2bc7d643046830cf335fec780f11
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420843"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="ca1dd-102">IXCLRDataProcess:: EndEnumModules (método)</span><span class="sxs-lookup"><span data-stu-id="ca1dd-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="ca1dd-103">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de módulos.</span><span class="sxs-lookup"><span data-stu-id="ca1dd-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ca1dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca1dd-104">Syntax</span></span>

```cpp
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="ca1dd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ca1dd-105">Parameters</span></span>

`handle`\
<span data-ttu-id="ca1dd-106">enuncia Identificador para enumerar los módulos.</span><span class="sxs-lookup"><span data-stu-id="ca1dd-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="ca1dd-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ca1dd-107">Remarks</span></span>

<span data-ttu-id="ca1dd-108">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura del 26 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="ca1dd-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="ca1dd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca1dd-109">Requirements</span></span>

<span data-ttu-id="ca1dd-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca1dd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="ca1dd-111">**Encabezado:** Ninguna **biblioteca:** ninguna **.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ca1dd-111">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ca1dd-112">Consulta también</span><span class="sxs-lookup"><span data-stu-id="ca1dd-112">See also</span></span>

- [<span data-ttu-id="ca1dd-113">Depuración</span><span class="sxs-lookup"><span data-stu-id="ca1dd-113">Debugging</span></span>](index.md)
- [<span data-ttu-id="ca1dd-114">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="ca1dd-114">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
