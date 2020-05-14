---
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
ms.openlocfilehash: d9f9e16d243c0f3b45ac24776caea5bb9c32dcc1
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395749"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a><span data-ttu-id="cd0ea-102">IXCLRDataMethodInstance:: GetRepresentativeEntryAddress (método)</span><span class="sxs-lookup"><span data-stu-id="cd0ea-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method</span></span>

<span data-ttu-id="cd0ea-103">Obtiene la dirección de punto de entrada más representativa para la compilación nativa de todos los puntos de entrada posibles para un método.</span><span class="sxs-lookup"><span data-stu-id="cd0ea-103">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="cd0ea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd0ea-104">Syntax</span></span>

```cpp
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a><span data-ttu-id="cd0ea-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cd0ea-105">Parameters</span></span>

`addr`\
<span data-ttu-id="cd0ea-106">enuncia Dirección del punto de entrada nativo más representativo para el método.</span><span class="sxs-lookup"><span data-stu-id="cd0ea-106">[out] The address of the most representative native entry point for the method.</span></span>

## <a name="remarks"></a><span data-ttu-id="cd0ea-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cd0ea-107">Remarks</span></span>

<span data-ttu-id="cd0ea-108">El método proporcionado forma parte de la [ `IXCLRDataMethodInstance` interfaz](ixclrdatamethodinstance-interface.md) y corresponde a la ranura del vigésimo de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="cd0ea-108">The provided method is part of the [`IXCLRDataMethodInstance` interface](ixclrdatamethodinstance-interface.md) and corresponds to the 20th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="cd0ea-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd0ea-109">Requirements</span></span>

<span data-ttu-id="cd0ea-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd0ea-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="cd0ea-111">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="cd0ea-111">**Header:** None</span></span>  
<span data-ttu-id="cd0ea-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="cd0ea-112">**Library:** None</span></span>  
<span data-ttu-id="cd0ea-113">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cd0ea-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="cd0ea-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd0ea-114">See also</span></span>

- [<span data-ttu-id="cd0ea-115">Depuración</span><span class="sxs-lookup"><span data-stu-id="cd0ea-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="cd0ea-116">Interfaz IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="cd0ea-116">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
