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
ms.openlocfilehash: 84e0ad392c5fee8377115427482d80543454fff3
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397207"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="b12c8-102">IXCLRDataMethodDefinition:: StartEnumInstances (método)</span><span class="sxs-lookup"><span data-stu-id="b12c8-102">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="b12c8-103">Proporciona un identificador para la enumeración de instancias de método para un determinado `IXCLRDataAppDomain` .</span><span class="sxs-lookup"><span data-stu-id="b12c8-103">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b12c8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b12c8-104">Syntax</span></span>

```cpp
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="b12c8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b12c8-105">Parameters</span></span>

`appDomain`\
<span data-ttu-id="b12c8-106">de AppDomain para la enumeración.</span><span class="sxs-lookup"><span data-stu-id="b12c8-106">[in] An AppDomain for the enumeration.</span></span>

`handle`\
<span data-ttu-id="b12c8-107">enuncia Identificador para enumerar las instancias de.</span><span class="sxs-lookup"><span data-stu-id="b12c8-107">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="b12c8-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b12c8-108">Remarks</span></span>

<span data-ttu-id="b12c8-109">El método proporcionado forma parte de la `IXCLRDataMethodDefinition` interfaz y corresponde a la quinta ranura de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="b12c8-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 5th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="b12c8-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b12c8-110">Requirements</span></span>

<span data-ttu-id="b12c8-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b12c8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b12c8-112">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="b12c8-112">**Header:** None</span></span>  
<span data-ttu-id="b12c8-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="b12c8-113">**Library:** None</span></span>  
<span data-ttu-id="b12c8-114">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b12c8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b12c8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b12c8-115">See also</span></span>

- [<span data-ttu-id="b12c8-116">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="b12c8-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="b12c8-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="b12c8-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="b12c8-118">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="b12c8-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
