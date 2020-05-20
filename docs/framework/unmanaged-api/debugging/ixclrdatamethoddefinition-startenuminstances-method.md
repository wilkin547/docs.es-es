---
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
ms.openlocfilehash: b0c37c666f23f04239ed827246b87c43ee8d5ad9
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420934"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="39fa5-102">IXCLRDataMethodDefinition:: StartEnumInstances (método)</span><span class="sxs-lookup"><span data-stu-id="39fa5-102">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="39fa5-103">Proporciona un identificador para la enumeración de instancias de método para un determinado `IXCLRDataAppDomain` .</span><span class="sxs-lookup"><span data-stu-id="39fa5-103">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="39fa5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39fa5-104">Syntax</span></span>

```cpp
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="39fa5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39fa5-105">Parameters</span></span>

`appDomain`\
<span data-ttu-id="39fa5-106">de AppDomain para la enumeración.</span><span class="sxs-lookup"><span data-stu-id="39fa5-106">[in] An AppDomain for the enumeration.</span></span>

`handle`\
<span data-ttu-id="39fa5-107">enuncia Identificador para enumerar las instancias de.</span><span class="sxs-lookup"><span data-stu-id="39fa5-107">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="39fa5-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="39fa5-108">Remarks</span></span>

<span data-ttu-id="39fa5-109">El método proporcionado forma parte de la `IXCLRDataMethodDefinition` interfaz y corresponde a la quinta ranura de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="39fa5-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 5th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="39fa5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39fa5-110">Requirements</span></span>

<span data-ttu-id="39fa5-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39fa5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="39fa5-112">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="39fa5-112">**Header:** None</span></span>  
<span data-ttu-id="39fa5-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="39fa5-113">**Library:** None</span></span>  
<span data-ttu-id="39fa5-114">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="39fa5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="39fa5-115">Consulta también</span><span class="sxs-lookup"><span data-stu-id="39fa5-115">See also</span></span>

- [<span data-ttu-id="39fa5-116">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="39fa5-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="39fa5-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="39fa5-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="39fa5-118">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="39fa5-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
