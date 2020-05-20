---
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
ms.openlocfilehash: 9d5ef137a5d76c3d7545ab16921352123e978fb1
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420869"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="1376a-102">IXCLRDataModule:: GetVersionId (método)</span><span class="sxs-lookup"><span data-stu-id="1376a-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="1376a-103">Obtiene el identificador de la versión del módulo.</span><span class="sxs-lookup"><span data-stu-id="1376a-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="1376a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1376a-104">Syntax</span></span>

```cpp
HRESULT GetVersionId(
    [out] GUID* vid
);
```

## <a name="parameters"></a><span data-ttu-id="1376a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1376a-105">Parameters</span></span>

`vid`\
<span data-ttu-id="1376a-106">enuncia Identificador de la versión del módulo.</span><span class="sxs-lookup"><span data-stu-id="1376a-106">[out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="1376a-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1376a-107">Remarks</span></span>

<span data-ttu-id="1376a-108">El método proporcionado forma parte de la `IXCLRDataModule` interfaz y corresponde a la ranura edición nº 41 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="1376a-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 41st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="1376a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1376a-109">Requirements</span></span>

<span data-ttu-id="1376a-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1376a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="1376a-111">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="1376a-111">**Header:** None</span></span>  
<span data-ttu-id="1376a-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="1376a-112">**Library:** None</span></span>  
<span data-ttu-id="1376a-113">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1376a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1376a-114">Consulta también</span><span class="sxs-lookup"><span data-stu-id="1376a-114">See also</span></span>

- [<span data-ttu-id="1376a-115">Depuración</span><span class="sxs-lookup"><span data-stu-id="1376a-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="1376a-116">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="1376a-116">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
