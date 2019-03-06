---
title: Método IXCLRDataMethodInstance::GetRepresentativeEntryAddress
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
ms.openlocfilehash: 6f204e2ed9cb1409d53432355467bb11946f8809
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372456"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a><span data-ttu-id="30773-102">Método IXCLRDataMethodInstance::GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="30773-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method</span></span>

<span data-ttu-id="30773-103">Obtiene la dirección del punto de entrada más representativa de la compilación nativa de todos los puntos de entrada posibles para un método.</span><span class="sxs-lookup"><span data-stu-id="30773-103">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="30773-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30773-104">Syntax</span></span>

```
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a><span data-ttu-id="30773-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="30773-105">Parameters</span></span>

`addr`\
<span data-ttu-id="30773-106">[out] La dirección del punto de entrada nativo más representativo del método.</span><span class="sxs-lookup"><span data-stu-id="30773-106">[out] The address of the most representative native entry point for the method.</span></span>

## <a name="remarks"></a><span data-ttu-id="30773-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="30773-107">Remarks</span></span>

<span data-ttu-id="30773-108">El método proporcionado forma parte de la [ `IXCLRDataMethodInstance` interfaz](ixclrdatamethodinstance-interface.md) y corresponde a la ranura de 19 de la tabla de métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="30773-108">The provided method is part of the [`IXCLRDataMethodInstance` interface](ixclrdatamethodinstance-interface.md) and corresponds to the 19th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="30773-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30773-109">Requirements</span></span>

<span data-ttu-id="30773-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30773-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="30773-111">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="30773-111">**Header:** None</span></span>  
<span data-ttu-id="30773-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="30773-112">**Library:** None</span></span>  
<span data-ttu-id="30773-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="30773-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="30773-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="30773-114">See also</span></span>

- [<span data-ttu-id="30773-115">Depuración</span><span class="sxs-lookup"><span data-stu-id="30773-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="30773-116">Interfaz IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="30773-116">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
