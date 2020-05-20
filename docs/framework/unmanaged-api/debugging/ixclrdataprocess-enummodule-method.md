---
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
ms.openlocfilehash: 5caadcfe091393a8ff79106d57a50a532c349829
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420785"
---
# <a name="ixclrdataprocessenummodule-method"></a><span data-ttu-id="1535f-102">IXCLRDataProcess:: EnumModule (método)</span><span class="sxs-lookup"><span data-stu-id="1535f-102">IXCLRDataProcess::EnumModule Method</span></span>

<span data-ttu-id="1535f-103">Enumera los módulos de este proceso.</span><span class="sxs-lookup"><span data-stu-id="1535f-103">Enumerates the modules of this process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="1535f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1535f-104">Syntax</span></span>

```cpp
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

## <a name="parameters"></a><span data-ttu-id="1535f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1535f-105">Parameters</span></span>

`handle`\
<span data-ttu-id="1535f-106">[in, out] Identificador para enumerar los módulos.</span><span class="sxs-lookup"><span data-stu-id="1535f-106">[in, out] A handle for enumerating the modules.</span></span>

`mod`\
<span data-ttu-id="1535f-107">enuncia Módulo enumerado.</span><span class="sxs-lookup"><span data-stu-id="1535f-107">[out] The enumerated module.</span></span>

## <a name="remarks"></a><span data-ttu-id="1535f-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1535f-108">Remarks</span></span>

<span data-ttu-id="1535f-109">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura 25 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="1535f-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="1535f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1535f-110">Requirements</span></span>

<span data-ttu-id="1535f-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1535f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="1535f-112">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="1535f-112">**Header:** None</span></span>  
<span data-ttu-id="1535f-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="1535f-113">**Library:** None</span></span>  
<span data-ttu-id="1535f-114">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1535f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1535f-115">Consulta también</span><span class="sxs-lookup"><span data-stu-id="1535f-115">See also</span></span>

- [<span data-ttu-id="1535f-116">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="1535f-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="1535f-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="1535f-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="1535f-118">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="1535f-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
- [<span data-ttu-id="1535f-119">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="1535f-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
