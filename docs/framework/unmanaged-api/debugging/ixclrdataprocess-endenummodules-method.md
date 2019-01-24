---
title: Método IXCLRDataProcess::EndEnumModules
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
ms.openlocfilehash: 50ad55674360d7b880af3ddf701cf17005f30ce7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722743"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="c39dd-102">Método IXCLRDataProcess::EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="c39dd-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="c39dd-103">Libera los recursos utilizados por los iteradores internos usa durante la enumeración de módulo.</span><span class="sxs-lookup"><span data-stu-id="c39dd-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="c39dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c39dd-104">Syntax</span></span>
```
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

### <a name="parameters"></a><span data-ttu-id="c39dd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c39dd-105">Parameters</span></span>
<span data-ttu-id="c39dd-106">`handle` [out] Un identificador para enumerar los módulos.</span><span class="sxs-lookup"><span data-stu-id="c39dd-106">`handle` [out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="c39dd-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c39dd-107">Remarks</span></span>

<span data-ttu-id="c39dd-108">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura de la tabla de métodos virtuales 26.</span><span class="sxs-lookup"><span data-stu-id="c39dd-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="c39dd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c39dd-109">Requirements</span></span>

<span data-ttu-id="c39dd-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c39dd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="c39dd-111">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="c39dd-111">**Header:** None</span></span>   
<span data-ttu-id="c39dd-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="c39dd-112">**Library:** None</span></span>   
<span data-ttu-id="c39dd-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c39dd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   

## <a name="see-also"></a><span data-ttu-id="c39dd-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c39dd-114">See also</span></span>

- [<span data-ttu-id="c39dd-115">Depuración</span><span class="sxs-lookup"><span data-stu-id="c39dd-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="c39dd-116">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="c39dd-116">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
