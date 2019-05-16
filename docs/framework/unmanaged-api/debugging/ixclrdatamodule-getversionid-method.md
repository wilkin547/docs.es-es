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
ms.openlocfilehash: 6ec18bcf079c7687df4ac9b7c5db23b84383c517
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632303"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="7ecc8-102">Método IXCLRDataModule::GetVersionId</span><span class="sxs-lookup"><span data-stu-id="7ecc8-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="7ecc8-103">Obtiene el identificador de la versión del módulo.</span><span class="sxs-lookup"><span data-stu-id="7ecc8-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="7ecc8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ecc8-104">Syntax</span></span>

```
HRESULT GetVersionId(
    [out] GUID* vid
);
```

## <a name="parameters"></a><span data-ttu-id="7ecc8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7ecc8-105">Parameters</span></span>

`vid`\
<span data-ttu-id="7ecc8-106">[out] Identificador de la versión del módulo.</span><span class="sxs-lookup"><span data-stu-id="7ecc8-106">[out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="7ecc8-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7ecc8-107">Remarks</span></span>

<span data-ttu-id="7ecc8-108">El método proporcionado forma parte de la `IXCLRDataModule` interfaz y corresponde a la ranura de 40 de la tabla de métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="7ecc8-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 40th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="7ecc8-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ecc8-109">Requirements</span></span>

<span data-ttu-id="7ecc8-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ecc8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="7ecc8-111">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="7ecc8-111">**Header:** None</span></span>  
<span data-ttu-id="7ecc8-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="7ecc8-112">**Library:** None</span></span>  
<span data-ttu-id="7ecc8-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7ecc8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="7ecc8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ecc8-114">See also</span></span>

- [<span data-ttu-id="7ecc8-115">Depuración</span><span class="sxs-lookup"><span data-stu-id="7ecc8-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="7ecc8-116">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="7ecc8-116">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
