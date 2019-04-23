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
ms.openlocfilehash: a51c709b0b331127b74d98c4dc42e2772fd7f2db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166444"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="4b3cd-102">Método IXCLRDataProcess::EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="4b3cd-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="4b3cd-103">Enumera las instancias de método de este proceso empezando por un desplazamiento de dirección.</span><span class="sxs-lookup"><span data-stu-id="4b3cd-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="4b3cd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b3cd-104">Syntax</span></span>

```
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="4b3cd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4b3cd-105">Parameters</span></span>

`handle`\
<span data-ttu-id="4b3cd-106">[in] Un identificador para enumerar las instancias de método.</span><span class="sxs-lookup"><span data-stu-id="4b3cd-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="4b3cd-107">[out] La instancia de método enumerado.</span><span class="sxs-lookup"><span data-stu-id="4b3cd-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="4b3cd-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4b3cd-108">Remarks</span></span>

<span data-ttu-id="4b3cd-109">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la fecha del 28 de ranura de la tabla de métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="4b3cd-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="4b3cd-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4b3cd-110">Requirements</span></span>

<span data-ttu-id="4b3cd-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b3cd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="4b3cd-112">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="4b3cd-112">**Header:** None</span></span>   
<span data-ttu-id="4b3cd-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="4b3cd-113">**Library:** None</span></span>   
<span data-ttu-id="4b3cd-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4b3cd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   
 
## <a name="see-also"></a><span data-ttu-id="4b3cd-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b3cd-115">See also</span></span>

- [<span data-ttu-id="4b3cd-116">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="4b3cd-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="4b3cd-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="4b3cd-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="4b3cd-118">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="4b3cd-118">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
