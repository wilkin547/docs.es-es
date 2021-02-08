---
description: 'Más información sobre: IXCLRDataProcess:: GetAppDomainByUniqueId (método)'
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
ms.openlocfilehash: 7087362efbb810fcb6e1b6f7eb9f23c54c38fade
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800674"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a><span data-ttu-id="cf42b-103">IXCLRDataProcess:: GetAppDomainByUniqueId (método)</span><span class="sxs-lookup"><span data-stu-id="cf42b-103">IXCLRDataProcess::GetAppDomainByUniqueId Method</span></span>

<span data-ttu-id="cf42b-104">Obtiene un `AppDomain` en un proceso basado en su identificador único.</span><span class="sxs-lookup"><span data-stu-id="cf42b-104">Gets an `AppDomain` in a process based on its unique identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="cf42b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf42b-105">Syntax</span></span>

```cpp
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

## <a name="parameters"></a><span data-ttu-id="cf42b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf42b-106">Parameters</span></span>

`id`\
<span data-ttu-id="cf42b-107">de Identificador único del AppDomain.</span><span class="sxs-lookup"><span data-stu-id="cf42b-107">[in] The unique identifier of the AppDomain</span></span>

`appDomain`\
<span data-ttu-id="cf42b-108">enuncia AppDomain</span><span class="sxs-lookup"><span data-stu-id="cf42b-108">[out] The AppDomain</span></span>

## <a name="remarks"></a><span data-ttu-id="cf42b-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cf42b-109">Remarks</span></span>

<span data-ttu-id="cf42b-110">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura del vigésimo de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="cf42b-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="cf42b-111">El `IXCLRDataAppDomain*` devuelto se usa para la interacción con otras API.</span><span class="sxs-lookup"><span data-stu-id="cf42b-111">The `IXCLRDataAppDomain*` returned is used for interaction with other APIs.</span></span>

## <a name="requirements"></a><span data-ttu-id="cf42b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf42b-112">Requirements</span></span>

<span data-ttu-id="cf42b-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf42b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="cf42b-114">**Encabezado:** Ninguna **biblioteca:** ninguna **.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cf42b-114">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cf42b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf42b-115">See also</span></span>

- [<span data-ttu-id="cf42b-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="cf42b-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="cf42b-117">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="cf42b-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
