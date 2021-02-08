---
description: 'Más información sobre: IXCLRDataMethodInstance:: GetRepresentativeEntryAddress (método)'
title: 'IXCLRDataMethodInstance:: GetRepresentativeEntryAddress (método)'
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
helpviewer.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 21cc6c50ab460c0e3a3a92c11fcfe51d4a2a4606
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800804"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a><span data-ttu-id="03eeb-103">IXCLRDataMethodInstance:: GetRepresentativeEntryAddress (método)</span><span class="sxs-lookup"><span data-stu-id="03eeb-103">IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method</span></span>

<span data-ttu-id="03eeb-104">Obtiene la dirección de punto de entrada más representativa para la compilación nativa de todos los puntos de entrada posibles para un método.</span><span class="sxs-lookup"><span data-stu-id="03eeb-104">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="03eeb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03eeb-105">Syntax</span></span>

```cpp
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a><span data-ttu-id="03eeb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="03eeb-106">Parameters</span></span>

`addr`\
<span data-ttu-id="03eeb-107">enuncia Dirección del punto de entrada nativo más representativo para el método.</span><span class="sxs-lookup"><span data-stu-id="03eeb-107">[out] The address of the most representative native entry point for the method.</span></span>

## <a name="remarks"></a><span data-ttu-id="03eeb-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="03eeb-108">Remarks</span></span>

<span data-ttu-id="03eeb-109">El método proporcionado forma parte de la [ `IXCLRDataMethodInstance` interfaz](ixclrdatamethodinstance-interface.md) y corresponde a la ranura del vigésimo de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="03eeb-109">The provided method is part of the [`IXCLRDataMethodInstance` interface](ixclrdatamethodinstance-interface.md) and corresponds to the 20th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="03eeb-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03eeb-110">Requirements</span></span>

<span data-ttu-id="03eeb-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03eeb-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="03eeb-112">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="03eeb-112">**Header:** None</span></span>  
<span data-ttu-id="03eeb-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="03eeb-113">**Library:** None</span></span>  
<span data-ttu-id="03eeb-114">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="03eeb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="03eeb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="03eeb-115">See also</span></span>

- [<span data-ttu-id="03eeb-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="03eeb-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="03eeb-117">Interfaz IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="03eeb-117">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
