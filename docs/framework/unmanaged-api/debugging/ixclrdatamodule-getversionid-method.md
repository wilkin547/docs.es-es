---
title: Método IXCLRDataModule::GetVersionId
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
ms.openlocfilehash: 5184db00b10b53011f24c5096b470608e84546b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567430"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="06c55-102">Método IXCLRDataModule::GetVersionId</span><span class="sxs-lookup"><span data-stu-id="06c55-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="06c55-103">Obtiene el identificador de la versión del módulo.</span><span class="sxs-lookup"><span data-stu-id="06c55-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="06c55-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06c55-104">Syntax</span></span>

```
HRESULT GetVersionId(
    [out] GUID* vid
);
```

### <a name="parameters"></a><span data-ttu-id="06c55-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="06c55-105">Parameters</span></span>

<span data-ttu-id="06c55-106">`vid` [out] Identificador de la versión del módulo.</span><span class="sxs-lookup"><span data-stu-id="06c55-106">`vid` [out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="06c55-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="06c55-107">Remarks</span></span>

<span data-ttu-id="06c55-108">El método proporcionado forma parte de la `IXCLRDataModule` interfaz y corresponde a la ranura de 40 de la tabla de métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="06c55-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 40th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="06c55-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06c55-109">Requirements</span></span>

<span data-ttu-id="06c55-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06c55-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="06c55-111">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="06c55-111">**Header:** None</span></span>  
<span data-ttu-id="06c55-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="06c55-112">**Library:** None</span></span>  
<span data-ttu-id="06c55-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="06c55-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="06c55-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="06c55-114">See also</span></span>

- [<span data-ttu-id="06c55-115">Depuración</span><span class="sxs-lookup"><span data-stu-id="06c55-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="06c55-116">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="06c55-116">IXCLRDataModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md)
