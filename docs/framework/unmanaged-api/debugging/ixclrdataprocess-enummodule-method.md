---
title: Método IXCLRDataProcess::EnumModule
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
ms.openlocfilehash: a0398d18f9568754231082d63b4c6a2c865d8c6f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775276"
---
# <a name="ixclrdataprocessenummodule-method"></a><span data-ttu-id="3272b-102">Método IXCLRDataProcess::EnumModule</span><span class="sxs-lookup"><span data-stu-id="3272b-102">IXCLRDataProcess::EnumModule Method</span></span>

<span data-ttu-id="3272b-103">Enumera los módulos de este proceso.</span><span class="sxs-lookup"><span data-stu-id="3272b-103">Enumerates the modules of this process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="3272b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3272b-104">Syntax</span></span>

```
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

## <a name="parameters"></a><span data-ttu-id="3272b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3272b-105">Parameters</span></span>

`handle`\
<span data-ttu-id="3272b-106">[in, out] Un identificador para enumerar los módulos.</span><span class="sxs-lookup"><span data-stu-id="3272b-106">[in, out] A handle for enumerating the modules.</span></span>

`mod`\
<span data-ttu-id="3272b-107">[out] El módulo enumerado.</span><span class="sxs-lookup"><span data-stu-id="3272b-107">[out] The enumerated module.</span></span>

## <a name="remarks"></a><span data-ttu-id="3272b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3272b-108">Remarks</span></span>

<span data-ttu-id="3272b-109">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura de la tabla de métodos virtuales 25.</span><span class="sxs-lookup"><span data-stu-id="3272b-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="3272b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3272b-110">Requirements</span></span>

<span data-ttu-id="3272b-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3272b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="3272b-112">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="3272b-112">**Header:** None</span></span>  
<span data-ttu-id="3272b-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="3272b-113">**Library:** None</span></span>  
<span data-ttu-id="3272b-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3272b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3272b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3272b-115">See also</span></span>

- [<span data-ttu-id="3272b-116">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="3272b-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="3272b-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="3272b-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="3272b-118">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="3272b-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
- [<span data-ttu-id="3272b-119">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="3272b-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
