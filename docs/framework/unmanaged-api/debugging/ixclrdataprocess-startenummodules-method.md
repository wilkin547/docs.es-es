---
description: 'Más información sobre: IXCLRDataProcess:: StartEnumModules (método)'
title: 'IXCLRDataProcess:: StartEnumModules (método)'
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
ms.openlocfilehash: 2e90c646ee8815ec10ce0bbd7538f13d7b5dcf8a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800590"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="27c6c-103">IXCLRDataProcess:: StartEnumModules (método)</span><span class="sxs-lookup"><span data-stu-id="27c6c-103">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="27c6c-104">Proporciona un identificador para enumerar los módulos de un proceso.</span><span class="sxs-lookup"><span data-stu-id="27c6c-104">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="27c6c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27c6c-105">Syntax</span></span>

```cpp
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="27c6c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="27c6c-106">Parameters</span></span>

`handle`\
<span data-ttu-id="27c6c-107">enuncia Identificador para enumerar los módulos.</span><span class="sxs-lookup"><span data-stu-id="27c6c-107">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="27c6c-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="27c6c-108">Remarks</span></span>

<span data-ttu-id="27c6c-109">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura de 24 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="27c6c-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="27c6c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27c6c-110">Requirements</span></span>

<span data-ttu-id="27c6c-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27c6c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="27c6c-112">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="27c6c-112">**Header:** None</span></span>  
<span data-ttu-id="27c6c-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="27c6c-113">**Library:** None</span></span>  
<span data-ttu-id="27c6c-114">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="27c6c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="27c6c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="27c6c-115">See also</span></span>

- [<span data-ttu-id="27c6c-116">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="27c6c-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="27c6c-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="27c6c-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="27c6c-118">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="27c6c-118">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
