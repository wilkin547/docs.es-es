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
ms.openlocfilehash: e92eea9677731756bdbfcbdcfac1531861fb5dce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961271"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="3d3b1-102">Método IXCLRDataMethodDefinition::StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="3d3b1-102">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="3d3b1-103">Proporciona un identificador para la enumeración de instancias de método para un determinado `IXCLRDataAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="3d3b1-103">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="3d3b1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d3b1-104">Syntax</span></span>

```
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="3d3b1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3d3b1-105">Parameters</span></span>

`appDomain`\
<span data-ttu-id="3d3b1-106">[in] Un dominio de aplicación para la enumeración.</span><span class="sxs-lookup"><span data-stu-id="3d3b1-106">[in] An AppDomain for the enumeration.</span></span>

`handle`\
<span data-ttu-id="3d3b1-107">[out] Un identificador para enumerar las instancias.</span><span class="sxs-lookup"><span data-stu-id="3d3b1-107">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="3d3b1-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3d3b1-108">Remarks</span></span>

<span data-ttu-id="3d3b1-109">El método proporcionado forma parte de la `IXCLRDataMethodDefinition` interfaz y corresponde a la tercera ranura a contar de la tabla de métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="3d3b1-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the third slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="3d3b1-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d3b1-110">Requirements</span></span>

<span data-ttu-id="3d3b1-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d3b1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="3d3b1-112">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="3d3b1-112">**Header:** None</span></span>  
<span data-ttu-id="3d3b1-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="3d3b1-113">**Library:** None</span></span>  
<span data-ttu-id="3d3b1-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3d3b1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3d3b1-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d3b1-115">See also</span></span>

- [<span data-ttu-id="3d3b1-116">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="3d3b1-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="3d3b1-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="3d3b1-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="3d3b1-118">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="3d3b1-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)