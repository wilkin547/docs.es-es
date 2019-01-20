---
title: Método IXCLRDataProcess::GetAppDomainByUniqueId
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
ms.openlocfilehash: 83e7d4e1a4ff3c2e6f573d6c097c7cdb9c5f3c54
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416696"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a><span data-ttu-id="f001d-102">Método IXCLRDataProcess::GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="f001d-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span></span>

<span data-ttu-id="f001d-103">Obtiene un `AppDomain` en un proceso según su identificador único.</span><span class="sxs-lookup"><span data-stu-id="f001d-103">Gets an `AppDomain` in a process based on its unique identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="f001d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f001d-104">Syntax</span></span>
```
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

### <a name="parameters"></a><span data-ttu-id="f001d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f001d-105">Parameters</span></span>
<span data-ttu-id="f001d-106">`id` [in] El identificador único del dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="f001d-106">`id` [in] The unique identifier of the AppDomain</span></span>

<span data-ttu-id="f001d-107">`appDomain` [out] El dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="f001d-107">`appDomain` [out] The AppDomain</span></span>

## <a name="remarks"></a><span data-ttu-id="f001d-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f001d-108">Remarks</span></span>

<span data-ttu-id="f001d-109">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura de la tabla de métodos virtuales 20.</span><span class="sxs-lookup"><span data-stu-id="f001d-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="f001d-110">El `IXCLRDataAppDomain*` devuelto se usa para la interacción con otras API.</span><span class="sxs-lookup"><span data-stu-id="f001d-110">The `IXCLRDataAppDomain*` returned is used for interaction with other APIs.</span></span>

## <a name="requirements"></a><span data-ttu-id="f001d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f001d-111">Requirements</span></span>
<span data-ttu-id="f001d-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f001d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="f001d-113">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="f001d-113">**Header:** None</span></span>  
<span data-ttu-id="f001d-114">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="f001d-114">**Library:** None</span></span>  
<span data-ttu-id="f001d-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f001d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="f001d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f001d-116">See Also</span></span>
- [<span data-ttu-id="f001d-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="f001d-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="f001d-118">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="f001d-118">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
