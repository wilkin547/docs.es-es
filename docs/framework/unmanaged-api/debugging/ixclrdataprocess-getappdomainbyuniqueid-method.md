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
ms.openlocfilehash: 8b468d40ef8eb523ba8881627fae15cf9b7c7b80
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2019
ms.locfileid: "59614027"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a><span data-ttu-id="6927f-102">Método IXCLRDataProcess::GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="6927f-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span></span>

<span data-ttu-id="6927f-103">Obtiene un `AppDomain` en un proceso según su identificador único.</span><span class="sxs-lookup"><span data-stu-id="6927f-103">Gets an `AppDomain` in a process based on its unique identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6927f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6927f-104">Syntax</span></span>

```cpp
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

## <a name="parameters"></a><span data-ttu-id="6927f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6927f-105">Parameters</span></span>

`id`\
<span data-ttu-id="6927f-106">[in] El identificador único del dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="6927f-106">[in] The unique identifier of the AppDomain</span></span>

`appDomain`\
<span data-ttu-id="6927f-107">[out] El dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="6927f-107">[out] The AppDomain</span></span>

## <a name="remarks"></a><span data-ttu-id="6927f-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6927f-108">Remarks</span></span>

<span data-ttu-id="6927f-109">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura de la tabla de métodos virtuales 20.</span><span class="sxs-lookup"><span data-stu-id="6927f-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="6927f-110">El `IXCLRDataAppDomain*` devuelto se usa para la interacción con otras API.</span><span class="sxs-lookup"><span data-stu-id="6927f-110">The `IXCLRDataAppDomain*` returned is used for interaction with other APIs.</span></span>

## <a name="requirements"></a><span data-ttu-id="6927f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6927f-111">Requirements</span></span>

<span data-ttu-id="6927f-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6927f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="6927f-113">**Encabezado**: Ninguno **biblioteca:** Ninguno **versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6927f-113">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6927f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6927f-114">See also</span></span>

- [<span data-ttu-id="6927f-115">Depuración</span><span class="sxs-lookup"><span data-stu-id="6927f-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="6927f-116">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="6927f-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
