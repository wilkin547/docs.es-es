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
ms.openlocfilehash: d871ca5dfd62dbca309f4ccc3dcedf959033a41e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474168"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="3f61f-102">Método IXCLRDataProcess::StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="3f61f-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="3f61f-103">Proporciona un identificador para enumerar los módulos de un proceso.</span><span class="sxs-lookup"><span data-stu-id="3f61f-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="3f61f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f61f-104">Syntax</span></span>

```
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="3f61f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3f61f-105">Parameters</span></span>

`handle`\
<span data-ttu-id="3f61f-106">[out] Un identificador para enumerar los módulos.</span><span class="sxs-lookup"><span data-stu-id="3f61f-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="3f61f-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3f61f-107">Remarks</span></span>

<span data-ttu-id="3f61f-108">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura de la tabla de métodos virtuales 24.</span><span class="sxs-lookup"><span data-stu-id="3f61f-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="3f61f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f61f-109">Requirements</span></span>

<span data-ttu-id="3f61f-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f61f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="3f61f-111">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="3f61f-111">**Header:** None</span></span>  
<span data-ttu-id="3f61f-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="3f61f-112">**Library:** None</span></span>  
<span data-ttu-id="3f61f-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3f61f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3f61f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f61f-114">See also</span></span>

- [<span data-ttu-id="3f61f-115">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="3f61f-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="3f61f-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="3f61f-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="3f61f-117">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="3f61f-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
