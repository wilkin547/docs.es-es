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
ms.openlocfilehash: e863f14676acc84f4d9f59d0898dee5b291bd30f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775445"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="e8ba6-102">Método IXCLRDataModule::GetVersionId</span><span class="sxs-lookup"><span data-stu-id="e8ba6-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="e8ba6-103">Obtiene el identificador de la versión del módulo.</span><span class="sxs-lookup"><span data-stu-id="e8ba6-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e8ba6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8ba6-104">Syntax</span></span>

```
HRESULT GetVersionId(
    [out] GUID* vid
);
```

## <a name="parameters"></a><span data-ttu-id="e8ba6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e8ba6-105">Parameters</span></span>

`vid`\
<span data-ttu-id="e8ba6-106">[out] Identificador de la versión del módulo.</span><span class="sxs-lookup"><span data-stu-id="e8ba6-106">[out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="e8ba6-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e8ba6-107">Remarks</span></span>

<span data-ttu-id="e8ba6-108">El método proporcionado forma parte de la `IXCLRDataModule` interfaz y corresponde a la ranura de 40 de la tabla de métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="e8ba6-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 40th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="e8ba6-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8ba6-109">Requirements</span></span>

<span data-ttu-id="e8ba6-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8ba6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e8ba6-111">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="e8ba6-111">**Header:** None</span></span>  
<span data-ttu-id="e8ba6-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="e8ba6-112">**Library:** None</span></span>  
<span data-ttu-id="e8ba6-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e8ba6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e8ba6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8ba6-114">See also</span></span>

- [<span data-ttu-id="e8ba6-115">Depuración</span><span class="sxs-lookup"><span data-stu-id="e8ba6-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="e8ba6-116">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="e8ba6-116">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)