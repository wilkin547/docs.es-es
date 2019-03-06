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
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361348"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="2a573-102">Método IXCLRDataMethodDefinition::StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="2a573-102">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="2a573-103">Proporciona un identificador para la enumeración de instancias de método para un determinado `IXCLRDataAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="2a573-103">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="2a573-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a573-104">Syntax</span></span>

```
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="2a573-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a573-105">Parameters</span></span>

`appDomain`\
<span data-ttu-id="2a573-106">[in] Un dominio de aplicación para la enumeración.</span><span class="sxs-lookup"><span data-stu-id="2a573-106">[in] An AppDomain for the enumeration.</span></span>

`handle`\
<span data-ttu-id="2a573-107">[out] Un identificador para enumerar las instancias.</span><span class="sxs-lookup"><span data-stu-id="2a573-107">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="2a573-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2a573-108">Remarks</span></span>

<span data-ttu-id="2a573-109">El método proporcionado forma parte de la `IXCLRDataMethodDefinition` interfaz y corresponde a la tercera ranura a contar de la tabla de métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="2a573-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the third slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="2a573-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a573-110">Requirements</span></span>

<span data-ttu-id="2a573-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a573-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="2a573-112">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="2a573-112">**Header:** None</span></span>  
<span data-ttu-id="2a573-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="2a573-113">**Library:** None</span></span>  
<span data-ttu-id="2a573-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2a573-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="2a573-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a573-115">See also</span></span>

- [<span data-ttu-id="2a573-116">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="2a573-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="2a573-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="2a573-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="2a573-118">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="2a573-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)