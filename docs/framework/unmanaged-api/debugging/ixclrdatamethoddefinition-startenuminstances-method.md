---
description: 'Más información sobre: IXCLRDataMethodDefinition:: StartEnumInstances (método)'
title: 'IXCLRDataMethodDefinition:: StartEnumInstances (método)'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::StartEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 74de6360c90766cfec17e6b88a495fe2a70858b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800830"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="6268a-103">IXCLRDataMethodDefinition:: StartEnumInstances (método)</span><span class="sxs-lookup"><span data-stu-id="6268a-103">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="6268a-104">Proporciona un identificador para la enumeración de instancias de método para un determinado `IXCLRDataAppDomain` .</span><span class="sxs-lookup"><span data-stu-id="6268a-104">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6268a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6268a-105">Syntax</span></span>

```cpp
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="6268a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6268a-106">Parameters</span></span>

`appDomain`\
<span data-ttu-id="6268a-107">de AppDomain para la enumeración.</span><span class="sxs-lookup"><span data-stu-id="6268a-107">[in] An AppDomain for the enumeration.</span></span>

`handle`\
<span data-ttu-id="6268a-108">enuncia Identificador para enumerar las instancias de.</span><span class="sxs-lookup"><span data-stu-id="6268a-108">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="6268a-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6268a-109">Remarks</span></span>

<span data-ttu-id="6268a-110">El método proporcionado forma parte de la `IXCLRDataMethodDefinition` interfaz y corresponde a la quinta ranura de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="6268a-110">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 5th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6268a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6268a-111">Requirements</span></span>

<span data-ttu-id="6268a-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6268a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6268a-113">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="6268a-113">**Header:** None</span></span>  
<span data-ttu-id="6268a-114">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="6268a-114">**Library:** None</span></span>  
<span data-ttu-id="6268a-115">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6268a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6268a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6268a-116">See also</span></span>

- [<span data-ttu-id="6268a-117">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="6268a-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="6268a-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="6268a-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="6268a-119">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="6268a-119">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
