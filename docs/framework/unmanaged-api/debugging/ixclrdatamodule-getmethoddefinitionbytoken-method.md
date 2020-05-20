---
title: 'IXCLRDataModule:: GetMethodDefinitionByToken (método)'
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
ms.openlocfilehash: 074949145be588fc34266a9f2ee501caeeffb9d3
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420882"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="bf7b3-102">IXCLRDataModule:: GetMethodDefinitionByToken (método)</span><span class="sxs-lookup"><span data-stu-id="bf7b3-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="bf7b3-103">Obtiene la definición de método correspondiente a un token de metadatos determinado.</span><span class="sxs-lookup"><span data-stu-id="bf7b3-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="bf7b3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf7b3-104">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="bf7b3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bf7b3-105">Parameters</span></span>

`token`\
<span data-ttu-id="bf7b3-106">de Token del método.</span><span class="sxs-lookup"><span data-stu-id="bf7b3-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="bf7b3-107">enuncia La definición del método.</span><span class="sxs-lookup"><span data-stu-id="bf7b3-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="bf7b3-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bf7b3-108">Remarks</span></span>

<span data-ttu-id="bf7b3-109">El método proporcionado forma parte de la `IXCLRDataModule` interfaz y corresponde a la ranura del 26 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="bf7b3-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="bf7b3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf7b3-110">Requirements</span></span>

<span data-ttu-id="bf7b3-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf7b3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="bf7b3-112">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="bf7b3-112">**Header:** None</span></span>  
<span data-ttu-id="bf7b3-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="bf7b3-113">**Library:** None</span></span>  
<span data-ttu-id="bf7b3-114">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bf7b3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="bf7b3-115">Consulta también</span><span class="sxs-lookup"><span data-stu-id="bf7b3-115">See also</span></span>

- [<span data-ttu-id="bf7b3-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="bf7b3-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="bf7b3-117">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="bf7b3-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
