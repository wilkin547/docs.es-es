---
title: Método IXCLRDataProcess::EndEnumMethodInstancesByAddress
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 67978e49a8c23c4b25234ecbb3639c696c7232f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655652"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a><span data-ttu-id="69b15-102">Método IXCLRDataProcess::EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="69b15-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="69b15-103">Libera los recursos utilizados por los iteradores internos usa durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="69b15-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="69b15-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69b15-104">Syntax</span></span>

```
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

### <a name="parameters"></a><span data-ttu-id="69b15-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="69b15-105">Parameters</span></span>

<span data-ttu-id="69b15-106">`handle` [out] Un identificador para enumerar las instancias de método.</span><span class="sxs-lookup"><span data-stu-id="69b15-106">`handle` [out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="69b15-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="69b15-107">Remarks</span></span>

<span data-ttu-id="69b15-108">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura de 29 de la tabla de métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="69b15-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 29th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="69b15-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69b15-109">Requirements</span></span>

<span data-ttu-id="69b15-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69b15-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="69b15-111">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="69b15-111">**Header:** None</span></span>  
<span data-ttu-id="69b15-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="69b15-112">**Library:** None</span></span>  
<span data-ttu-id="69b15-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="69b15-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="69b15-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="69b15-114">See also</span></span>

- [<span data-ttu-id="69b15-115">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="69b15-115">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="69b15-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="69b15-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="69b15-117">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="69b15-117">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
