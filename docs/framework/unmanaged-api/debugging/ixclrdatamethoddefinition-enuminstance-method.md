---
title: 'IXCLRDataMethodDefinition:: EnumInstance (método)'
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
ms.openlocfilehash: 72560de9777b2d826418e63b4a4fcccf1e4fa8b9
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396478"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="3c9a4-102">IXCLRDataMethodDefinition:: EnumInstance (método)</span><span class="sxs-lookup"><span data-stu-id="3c9a4-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="3c9a4-103">Enumera las instancias de esta definición de método.</span><span class="sxs-lookup"><span data-stu-id="3c9a4-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="3c9a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c9a4-104">Syntax</span></span>

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="3c9a4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c9a4-105">Parameters</span></span>

`handle`\
<span data-ttu-id="3c9a4-106">[in, out] Identificador para enumerar las instancias de.</span><span class="sxs-lookup"><span data-stu-id="3c9a4-106">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="3c9a4-107">enuncia Instancia enumerada.</span><span class="sxs-lookup"><span data-stu-id="3c9a4-107">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="3c9a4-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c9a4-108">Remarks</span></span>

<span data-ttu-id="3c9a4-109">El método proporcionado forma parte de la `IXCLRDataMethodDefinition` interfaz y corresponde a la sexta ranura de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="3c9a4-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 6th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="3c9a4-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c9a4-110">Requirements</span></span>

<span data-ttu-id="3c9a4-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c9a4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="3c9a4-112">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="3c9a4-112">**Header:** None</span></span>  
<span data-ttu-id="3c9a4-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="3c9a4-113">**Library:** None</span></span>  
<span data-ttu-id="3c9a4-114">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3c9a4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3c9a4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c9a4-115">See also</span></span>

- [<span data-ttu-id="3c9a4-116">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="3c9a4-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="3c9a4-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="3c9a4-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="3c9a4-118">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="3c9a4-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="3c9a4-119">Interfaz IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="3c9a4-119">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
