---
description: 'Más información sobre: IXCLRDataModule:: GetMethodDefinitionByToken (método)'
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
ms.openlocfilehash: 1eb1187d09183bfff97324a8032d23cbf471f580
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800778"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="2a5c6-103">IXCLRDataModule:: GetMethodDefinitionByToken (método)</span><span class="sxs-lookup"><span data-stu-id="2a5c6-103">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="2a5c6-104">Obtiene la definición de método correspondiente a un token de metadatos determinado.</span><span class="sxs-lookup"><span data-stu-id="2a5c6-104">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="2a5c6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a5c6-105">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="2a5c6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a5c6-106">Parameters</span></span>

`token`\
<span data-ttu-id="2a5c6-107">de Token del método.</span><span class="sxs-lookup"><span data-stu-id="2a5c6-107">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="2a5c6-108">enuncia La definición del método.</span><span class="sxs-lookup"><span data-stu-id="2a5c6-108">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="2a5c6-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2a5c6-109">Remarks</span></span>

<span data-ttu-id="2a5c6-110">El método proporcionado forma parte de la `IXCLRDataModule` interfaz y corresponde a la ranura del 26 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="2a5c6-110">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="2a5c6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a5c6-111">Requirements</span></span>

<span data-ttu-id="2a5c6-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a5c6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="2a5c6-113">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="2a5c6-113">**Header:** None</span></span>  
<span data-ttu-id="2a5c6-114">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="2a5c6-114">**Library:** None</span></span>  
<span data-ttu-id="2a5c6-115">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2a5c6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="2a5c6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a5c6-116">See also</span></span>

- [<span data-ttu-id="2a5c6-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="2a5c6-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="2a5c6-118">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="2a5c6-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
