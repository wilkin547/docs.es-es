---
description: 'Más información sobre: IXCLRDataProcess:: EnumModule (método)'
title: 'IXCLRDataProcess:: EnumModule (método)'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumModule Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumModule Method
helpviewer.keywords:
- IXCLRDataProcess::EnumModule Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 33b15da6939a0fb78a4eeafcf75e1a2b2f0d0ab1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800687"
---
# <a name="ixclrdataprocessenummodule-method"></a><span data-ttu-id="5b128-103">IXCLRDataProcess:: EnumModule (método)</span><span class="sxs-lookup"><span data-stu-id="5b128-103">IXCLRDataProcess::EnumModule Method</span></span>

<span data-ttu-id="5b128-104">Enumera los módulos de este proceso.</span><span class="sxs-lookup"><span data-stu-id="5b128-104">Enumerates the modules of this process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5b128-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b128-105">Syntax</span></span>

```cpp
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

## <a name="parameters"></a><span data-ttu-id="5b128-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5b128-106">Parameters</span></span>

`handle`\
<span data-ttu-id="5b128-107">[in, out] Identificador para enumerar los módulos.</span><span class="sxs-lookup"><span data-stu-id="5b128-107">[in, out] A handle for enumerating the modules.</span></span>

`mod`\
<span data-ttu-id="5b128-108">enuncia Módulo enumerado.</span><span class="sxs-lookup"><span data-stu-id="5b128-108">[out] The enumerated module.</span></span>

## <a name="remarks"></a><span data-ttu-id="5b128-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5b128-109">Remarks</span></span>

<span data-ttu-id="5b128-110">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura 25 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="5b128-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="5b128-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5b128-111">Requirements</span></span>

<span data-ttu-id="5b128-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b128-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5b128-113">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="5b128-113">**Header:** None</span></span>  
<span data-ttu-id="5b128-114">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="5b128-114">**Library:** None</span></span>  
<span data-ttu-id="5b128-115">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5b128-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5b128-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b128-116">See also</span></span>

- [<span data-ttu-id="5b128-117">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="5b128-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="5b128-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="5b128-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="5b128-119">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="5b128-119">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
- [<span data-ttu-id="5b128-120">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="5b128-120">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
