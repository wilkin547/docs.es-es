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
ms.openlocfilehash: b6393d7fa4853c230203521e665bbe89d7b228e2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790439"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="6ca57-102">IXCLRDataMethodDefinition:: EnumInstance (método)</span><span class="sxs-lookup"><span data-stu-id="6ca57-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="6ca57-103">Enumera las instancias de esta definición de método.</span><span class="sxs-lookup"><span data-stu-id="6ca57-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6ca57-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ca57-104">Syntax</span></span>

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="6ca57-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="6ca57-105">Parameters</span></span>

`handle`\
<span data-ttu-id="6ca57-106">[in, out] Identificador para enumerar las instancias de.</span><span class="sxs-lookup"><span data-stu-id="6ca57-106">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="6ca57-107">enuncia Instancia enumerada.</span><span class="sxs-lookup"><span data-stu-id="6ca57-107">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="6ca57-108">Notas</span><span class="sxs-lookup"><span data-stu-id="6ca57-108">Remarks</span></span>

<span data-ttu-id="6ca57-109">El método proporcionado forma parte de la interfaz `IXCLRDataMethodDefinition` y corresponde a la cuarta ranura de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="6ca57-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6ca57-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="6ca57-110">Requirements</span></span>

<span data-ttu-id="6ca57-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ca57-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6ca57-112">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="6ca57-112">**Header:** None</span></span>  
<span data-ttu-id="6ca57-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="6ca57-113">**Library:** None</span></span>  
<span data-ttu-id="6ca57-114">**.NET Framework versiones:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6ca57-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6ca57-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ca57-115">See also</span></span>

- [<span data-ttu-id="6ca57-116">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="6ca57-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="6ca57-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="6ca57-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="6ca57-118">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="6ca57-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="6ca57-119">Interfaz IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="6ca57-119">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
