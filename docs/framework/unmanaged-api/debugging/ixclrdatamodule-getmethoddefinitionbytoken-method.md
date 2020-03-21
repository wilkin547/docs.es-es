---
title: IXCLRDataModule::GetMethodDefinitionByToken Método
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetMethodDefinitionByToken Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method
helpviewer.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 294c5340caf2217f9337d654a11a63a43d46febd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176674"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="ad832-102">IXCLRDataModule::GetMethodDefinitionByToken Método</span><span class="sxs-lookup"><span data-stu-id="ad832-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="ad832-103">Obtiene la definición del método correspondiente a un token de metadatos determinado.</span><span class="sxs-lookup"><span data-stu-id="ad832-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ad832-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad832-104">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="ad832-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ad832-105">Parameters</span></span>

`token`\
<span data-ttu-id="ad832-106">[en] El token de método.</span><span class="sxs-lookup"><span data-stu-id="ad832-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="ad832-107">[fuera] La definición del método.</span><span class="sxs-lookup"><span data-stu-id="ad832-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="ad832-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ad832-108">Remarks</span></span>

<span data-ttu-id="ad832-109">El método proporcionado forma `IXCLRDataModule` parte de la interfaz y corresponde a la ranura 25 de la tabla de métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="ad832-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="ad832-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad832-110">Requirements</span></span>

<span data-ttu-id="ad832-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad832-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ad832-112">**Encabezado:** Ninguno</span><span class="sxs-lookup"><span data-stu-id="ad832-112">**Header:** None</span></span>  
<span data-ttu-id="ad832-113">**Biblioteca:** Ninguno</span><span class="sxs-lookup"><span data-stu-id="ad832-113">**Library:** None</span></span>  
<span data-ttu-id="ad832-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ad832-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ad832-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ad832-115">See also</span></span>

- [<span data-ttu-id="ad832-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="ad832-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="ad832-117">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="ad832-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
