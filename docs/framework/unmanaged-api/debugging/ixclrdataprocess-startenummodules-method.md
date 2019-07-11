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
ms.openlocfilehash: 79c4e0ed99a068d7d806d5c25580dc477aac6475
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752629"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="fdc47-102">Método IXCLRDataProcess::StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="fdc47-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="fdc47-103">Proporciona un identificador para enumerar los módulos de un proceso.</span><span class="sxs-lookup"><span data-stu-id="fdc47-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="fdc47-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fdc47-104">Syntax</span></span>

```cpp
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="fdc47-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fdc47-105">Parameters</span></span>

`handle`\
<span data-ttu-id="fdc47-106">[out] Un identificador para enumerar los módulos.</span><span class="sxs-lookup"><span data-stu-id="fdc47-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="fdc47-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fdc47-107">Remarks</span></span>

<span data-ttu-id="fdc47-108">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura de la tabla de métodos virtuales 24.</span><span class="sxs-lookup"><span data-stu-id="fdc47-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="fdc47-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fdc47-109">Requirements</span></span>

<span data-ttu-id="fdc47-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdc47-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="fdc47-111">**Encabezado**: None</span><span class="sxs-lookup"><span data-stu-id="fdc47-111">**Header:** None</span></span>  
<span data-ttu-id="fdc47-112">**Biblioteca:** None</span><span class="sxs-lookup"><span data-stu-id="fdc47-112">**Library:** None</span></span>  
<span data-ttu-id="fdc47-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fdc47-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="fdc47-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdc47-114">See also</span></span>

- [<span data-ttu-id="fdc47-115">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="fdc47-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="fdc47-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="fdc47-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="fdc47-117">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="fdc47-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
