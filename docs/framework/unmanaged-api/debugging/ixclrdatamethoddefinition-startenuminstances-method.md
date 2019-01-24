---
title: Método IXCLRDataMethodDefinition::StartEnumInstances
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
ms.openlocfilehash: c78af112e9239143c4854e34e9b6aa8e99344ec3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623656"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="8c0e1-102">Método IXCLRDataMethodDefinition::StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="8c0e1-102">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="8c0e1-103">Proporciona un identificador para la enumeración de instancias de método para un determinado `IXCLRDataAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="8c0e1-103">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="8c0e1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c0e1-104">Syntax</span></span>

```
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

### <a name="parameters"></a><span data-ttu-id="8c0e1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8c0e1-105">Parameters</span></span>

<span data-ttu-id="8c0e1-106">`appDomain` [in] Un dominio de aplicación para la enumeración.</span><span class="sxs-lookup"><span data-stu-id="8c0e1-106">`appDomain` [in] An AppDomain for the enumeration.</span></span>

<span data-ttu-id="8c0e1-107">`handle` [out] Un identificador para enumerar las instancias.</span><span class="sxs-lookup"><span data-stu-id="8c0e1-107">`handle` [out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="8c0e1-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8c0e1-108">Remarks</span></span>

<span data-ttu-id="8c0e1-109">El método proporcionado forma parte de la `IXCLRDataMethodDefinition` interfaz y corresponde a la tercera ranura a contar de la tabla de métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="8c0e1-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the third slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="8c0e1-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c0e1-110">Requirements</span></span>

<span data-ttu-id="8c0e1-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c0e1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="8c0e1-112">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="8c0e1-112">**Header:** None</span></span>  
<span data-ttu-id="8c0e1-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="8c0e1-113">**Library:** None</span></span>  
<span data-ttu-id="8c0e1-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8c0e1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8c0e1-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c0e1-115">See also</span></span>

- [<span data-ttu-id="8c0e1-116">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="8c0e1-116">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="8c0e1-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="8c0e1-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="8c0e1-118">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="8c0e1-118">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
