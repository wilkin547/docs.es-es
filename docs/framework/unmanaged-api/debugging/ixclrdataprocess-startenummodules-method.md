---
title: Método IXCLRDataProcess::StartEnumModules
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a81da147c1483e7649612050f4aba29a2cc63b49
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416715"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="2d42c-102">Método IXCLRDataProcess::StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="2d42c-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="2d42c-103">Proporciona un identificador para enumerar los módulos de un proceso.</span><span class="sxs-lookup"><span data-stu-id="2d42c-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="2d42c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d42c-104">Syntax</span></span>

```
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

### <a name="parameters"></a><span data-ttu-id="2d42c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d42c-105">Parameters</span></span>

<span data-ttu-id="2d42c-106">`handle` [out] Un identificador para enumerar los módulos.</span><span class="sxs-lookup"><span data-stu-id="2d42c-106">`handle` [out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d42c-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d42c-107">Remarks</span></span>

<span data-ttu-id="2d42c-108">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura de la tabla de métodos virtuales 24.</span><span class="sxs-lookup"><span data-stu-id="2d42c-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="2d42c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d42c-109">Requirements</span></span>

<span data-ttu-id="2d42c-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d42c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="2d42c-111">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="2d42c-111">**Header:** None</span></span>  
<span data-ttu-id="2d42c-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="2d42c-112">**Library:** None</span></span>  
<span data-ttu-id="2d42c-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2d42c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="2d42c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d42c-114">See Also</span></span>

- [<span data-ttu-id="2d42c-115">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="2d42c-115">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="2d42c-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="2d42c-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="2d42c-117">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="2d42c-117">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
