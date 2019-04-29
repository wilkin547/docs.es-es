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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775537"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a><span data-ttu-id="cf501-102">Método IXCLRDataMethodInstance::GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="cf501-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method</span></span>

<span data-ttu-id="cf501-103">Obtiene la dirección del punto de entrada más representativa de la compilación nativa de todos los puntos de entrada posibles para un método.</span><span class="sxs-lookup"><span data-stu-id="cf501-103">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="cf501-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf501-104">Syntax</span></span>

```
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a><span data-ttu-id="cf501-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf501-105">Parameters</span></span>

`addr`\
<span data-ttu-id="cf501-106">[out] La dirección del punto de entrada nativo más representativo del método.</span><span class="sxs-lookup"><span data-stu-id="cf501-106">[out] The address of the most representative native entry point for the method.</span></span>

## <a name="remarks"></a><span data-ttu-id="cf501-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cf501-107">Remarks</span></span>

<span data-ttu-id="cf501-108">El método proporcionado forma parte de la [ `IXCLRDataMethodInstance` interfaz](ixclrdatamethodinstance-interface.md) y corresponde a la ranura de 19 de la tabla de métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="cf501-108">The provided method is part of the [`IXCLRDataMethodInstance` interface](ixclrdatamethodinstance-interface.md) and corresponds to the 19th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="cf501-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf501-109">Requirements</span></span>

<span data-ttu-id="cf501-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf501-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="cf501-111">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="cf501-111">**Header:** None</span></span>  
<span data-ttu-id="cf501-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="cf501-112">**Library:** None</span></span>  
<span data-ttu-id="cf501-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cf501-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="cf501-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf501-114">See also</span></span>

- [<span data-ttu-id="cf501-115">Depuración</span><span class="sxs-lookup"><span data-stu-id="cf501-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="cf501-116">Interfaz IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="cf501-116">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
