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
ms.openlocfilehash: ff8ccf42d1131fb15d7473ae12ecefde9d55177f
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395276"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="ba1dd-102">IXCLRDataModule:: GetVersionId (método)</span><span class="sxs-lookup"><span data-stu-id="ba1dd-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="ba1dd-103">Obtiene el identificador de la versión del módulo.</span><span class="sxs-lookup"><span data-stu-id="ba1dd-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ba1dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba1dd-104">Syntax</span></span>

```cpp
HRESULT GetVersionId(
    [out] GUID* vid
);
```

## <a name="parameters"></a><span data-ttu-id="ba1dd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ba1dd-105">Parameters</span></span>

`vid`\
<span data-ttu-id="ba1dd-106">enuncia Identificador de la versión del módulo.</span><span class="sxs-lookup"><span data-stu-id="ba1dd-106">[out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="ba1dd-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ba1dd-107">Remarks</span></span>

<span data-ttu-id="ba1dd-108">El método proporcionado forma parte de la `IXCLRDataModule` interfaz y corresponde a la ranura edición nº 41 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="ba1dd-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 41st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="ba1dd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba1dd-109">Requirements</span></span>

<span data-ttu-id="ba1dd-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba1dd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ba1dd-111">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="ba1dd-111">**Header:** None</span></span>  
<span data-ttu-id="ba1dd-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="ba1dd-112">**Library:** None</span></span>  
<span data-ttu-id="ba1dd-113">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ba1dd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ba1dd-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba1dd-114">See also</span></span>

- [<span data-ttu-id="ba1dd-115">Depuración</span><span class="sxs-lookup"><span data-stu-id="ba1dd-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="ba1dd-116">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="ba1dd-116">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
