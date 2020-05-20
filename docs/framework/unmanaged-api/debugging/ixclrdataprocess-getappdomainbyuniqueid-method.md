---
title: 'IXCLRDataProcess:: GetAppDomainByUniqueId (método)'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
helpviewer.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: bb02ffed09cbcc31e653bfd3165050c247908c5d
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420791"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a><span data-ttu-id="44b90-102">IXCLRDataProcess:: GetAppDomainByUniqueId (método)</span><span class="sxs-lookup"><span data-stu-id="44b90-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span></span>

<span data-ttu-id="44b90-103">Obtiene un `AppDomain` en un proceso basado en su identificador único.</span><span class="sxs-lookup"><span data-stu-id="44b90-103">Gets an `AppDomain` in a process based on its unique identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="44b90-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44b90-104">Syntax</span></span>

```cpp
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

## <a name="parameters"></a><span data-ttu-id="44b90-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="44b90-105">Parameters</span></span>

`id`\
<span data-ttu-id="44b90-106">de Identificador único del AppDomain.</span><span class="sxs-lookup"><span data-stu-id="44b90-106">[in] The unique identifier of the AppDomain</span></span>

`appDomain`\
<span data-ttu-id="44b90-107">enuncia AppDomain</span><span class="sxs-lookup"><span data-stu-id="44b90-107">[out] The AppDomain</span></span>

## <a name="remarks"></a><span data-ttu-id="44b90-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="44b90-108">Remarks</span></span>

<span data-ttu-id="44b90-109">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura del vigésimo de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="44b90-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="44b90-110">El `IXCLRDataAppDomain*` devuelto se usa para la interacción con otras API.</span><span class="sxs-lookup"><span data-stu-id="44b90-110">The `IXCLRDataAppDomain*` returned is used for interaction with other APIs.</span></span>

## <a name="requirements"></a><span data-ttu-id="44b90-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44b90-111">Requirements</span></span>

<span data-ttu-id="44b90-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44b90-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="44b90-113">**Encabezado:** Ninguna **biblioteca:** ninguna **.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="44b90-113">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="44b90-114">Consulta también</span><span class="sxs-lookup"><span data-stu-id="44b90-114">See also</span></span>

- [<span data-ttu-id="44b90-115">Depuración</span><span class="sxs-lookup"><span data-stu-id="44b90-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="44b90-116">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="44b90-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
