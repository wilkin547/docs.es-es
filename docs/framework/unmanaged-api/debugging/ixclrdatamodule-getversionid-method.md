---
description: 'Más información sobre: IXCLRDataModule:: GetVersionId (método)'
title: 'IXCLRDataModule:: GetVersionId (método)'
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetVersionId Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetVersionId Method
helpviewer.keywords:
- IXCLRDataModule::GetVersionId Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 1b924757f43d106df555ea028270ac873f8f4558
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800765"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="d7769-103">IXCLRDataModule:: GetVersionId (método)</span><span class="sxs-lookup"><span data-stu-id="d7769-103">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="d7769-104">Obtiene el identificador de la versión del módulo.</span><span class="sxs-lookup"><span data-stu-id="d7769-104">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="d7769-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7769-105">Syntax</span></span>

```cpp
HRESULT GetVersionId(
    [out] GUID* vid
);
```

## <a name="parameters"></a><span data-ttu-id="d7769-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d7769-106">Parameters</span></span>

`vid`\
<span data-ttu-id="d7769-107">enuncia Identificador de la versión del módulo.</span><span class="sxs-lookup"><span data-stu-id="d7769-107">[out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="d7769-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d7769-108">Remarks</span></span>

<span data-ttu-id="d7769-109">El método proporcionado forma parte de la `IXCLRDataModule` interfaz y corresponde a la ranura edición nº 41 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="d7769-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 41st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="d7769-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d7769-110">Requirements</span></span>

<span data-ttu-id="d7769-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7769-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d7769-112">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="d7769-112">**Header:** None</span></span>  
<span data-ttu-id="d7769-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="d7769-113">**Library:** None</span></span>  
<span data-ttu-id="d7769-114">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d7769-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d7769-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7769-115">See also</span></span>

- [<span data-ttu-id="d7769-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="d7769-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="d7769-117">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="d7769-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
