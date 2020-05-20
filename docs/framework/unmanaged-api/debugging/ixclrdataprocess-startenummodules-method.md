---
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
ms.openlocfilehash: d55b07ea3fada73237919bf677163a9096d5ad04
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420726"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="fdb3b-102">IXCLRDataProcess:: StartEnumModules (método)</span><span class="sxs-lookup"><span data-stu-id="fdb3b-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="fdb3b-103">Proporciona un identificador para enumerar los módulos de un proceso.</span><span class="sxs-lookup"><span data-stu-id="fdb3b-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="fdb3b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fdb3b-104">Syntax</span></span>

```cpp
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="fdb3b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fdb3b-105">Parameters</span></span>

`handle`\
<span data-ttu-id="fdb3b-106">enuncia Identificador para enumerar los módulos.</span><span class="sxs-lookup"><span data-stu-id="fdb3b-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="fdb3b-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fdb3b-107">Remarks</span></span>

<span data-ttu-id="fdb3b-108">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura de 24 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="fdb3b-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="fdb3b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fdb3b-109">Requirements</span></span>

<span data-ttu-id="fdb3b-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdb3b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="fdb3b-111">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="fdb3b-111">**Header:** None</span></span>  
<span data-ttu-id="fdb3b-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="fdb3b-112">**Library:** None</span></span>  
<span data-ttu-id="fdb3b-113">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fdb3b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="fdb3b-114">Consulta también</span><span class="sxs-lookup"><span data-stu-id="fdb3b-114">See also</span></span>

- [<span data-ttu-id="fdb3b-115">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="fdb3b-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="fdb3b-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="fdb3b-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="fdb3b-117">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="fdb3b-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
