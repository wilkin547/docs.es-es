---
title: Método IXCLRDataMethodDefinition::EndEnumInstances
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EndEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 28cd15a793d303e1d6e64c52c1d0095e8d619c7b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378942"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="d4fe3-102">Método IXCLRDataMethodDefinition::EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="d4fe3-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="d4fe3-103">Libera los recursos utilizados por los iteradores internos usa durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="d4fe3-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="d4fe3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4fe3-104">Syntax</span></span>

```
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="d4fe3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d4fe3-105">Parameters</span></span>

`handle`\
<span data-ttu-id="d4fe3-106">[out] Un identificador para enumerar las instancias.</span><span class="sxs-lookup"><span data-stu-id="d4fe3-106">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="d4fe3-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d4fe3-107">Remarks</span></span>

<span data-ttu-id="d4fe3-108">El método proporcionado forma parte de la `IXCLRDataMethodDefinition` interfaz y corresponde a la ranura de la tabla de métodos virtuales quinta.</span><span class="sxs-lookup"><span data-stu-id="d4fe3-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fifth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="d4fe3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4fe3-109">Requirements</span></span>

<span data-ttu-id="d4fe3-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4fe3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d4fe3-111">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="d4fe3-111">**Header:** None</span></span>  
<span data-ttu-id="d4fe3-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="d4fe3-112">**Library:** None</span></span>  
<span data-ttu-id="d4fe3-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d4fe3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d4fe3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4fe3-114">See also</span></span>

- [<span data-ttu-id="d4fe3-115">Depuración</span><span class="sxs-lookup"><span data-stu-id="d4fe3-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="d4fe3-116">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="d4fe3-116">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
