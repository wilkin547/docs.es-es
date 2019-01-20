---
title: Método IXCLRDataProcess::EnumMethodInstanceByAddress
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: b42939e8e64e75337478ace67a9a91c6a03a94e3
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416685"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="cd297-102">Método IXCLRDataProcess::EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="cd297-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="cd297-103">Enumera las instancias de método de este proceso empezando por un desplazamiento de dirección.</span><span class="sxs-lookup"><span data-stu-id="cd297-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="cd297-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd297-104">Syntax</span></span>

```
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

### <a name="parameters"></a><span data-ttu-id="cd297-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cd297-105">Parameters</span></span>

<span data-ttu-id="cd297-106">`handle` [in] Un identificador para enumerar las instancias de método.</span><span class="sxs-lookup"><span data-stu-id="cd297-106">`handle` [in] A handle for enumerating the method instances.</span></span>

<span data-ttu-id="cd297-107">`mod` [out] La instancia de método enumerado.</span><span class="sxs-lookup"><span data-stu-id="cd297-107">`mod` [out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="cd297-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cd297-108">Remarks</span></span>

<span data-ttu-id="cd297-109">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la fecha del 28 de ranura de la tabla de métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="cd297-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="cd297-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd297-110">Requirements</span></span>

<span data-ttu-id="cd297-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd297-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="cd297-112">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="cd297-112">**Header:** None</span></span>   
<span data-ttu-id="cd297-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="cd297-113">**Library:** None</span></span>   
<span data-ttu-id="cd297-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cd297-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   
 
## <a name="see-also"></a><span data-ttu-id="cd297-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd297-115">See Also</span></span>
- [<span data-ttu-id="cd297-116">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="cd297-116">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="cd297-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="cd297-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="cd297-118">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="cd297-118">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
