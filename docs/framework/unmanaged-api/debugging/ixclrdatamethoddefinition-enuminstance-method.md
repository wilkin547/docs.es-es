---
title: Método IXCLRDataMethodDefinition::EnumInstance
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EnumInstance Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: dacf76582916ad50f51ae7c8818b496f31f9553e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353119"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="d9634-102">Método IXCLRDataMethodDefinition::EnumInstance</span><span class="sxs-lookup"><span data-stu-id="d9634-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="d9634-103">Enumera las instancias de esta definición de método.</span><span class="sxs-lookup"><span data-stu-id="d9634-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="d9634-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9634-104">Syntax</span></span>

```
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="d9634-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d9634-105">Parameters</span></span>

`handle`\
<span data-ttu-id="d9634-106">[in, out] Un identificador para enumerar las instancias.</span><span class="sxs-lookup"><span data-stu-id="d9634-106">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="d9634-107">[out] La instancia enumerada.</span><span class="sxs-lookup"><span data-stu-id="d9634-107">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="d9634-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d9634-108">Remarks</span></span>

<span data-ttu-id="d9634-109">El método proporcionado forma parte de la `IXCLRDataMethodDefinition` interfaz y corresponde a la cuarta ranura de la tabla de métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="d9634-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="d9634-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9634-110">Requirements</span></span>

<span data-ttu-id="d9634-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9634-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d9634-112">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="d9634-112">**Header:** None</span></span>  
<span data-ttu-id="d9634-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="d9634-113">**Library:** None</span></span>  
<span data-ttu-id="d9634-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d9634-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d9634-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9634-115">See also</span></span>

- [<span data-ttu-id="d9634-116">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="d9634-116">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="d9634-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="d9634-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="d9634-118">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="d9634-118">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="d9634-119">Interfaz IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="d9634-119">IXCLRDataMethodInstance Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md)
