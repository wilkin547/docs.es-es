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
ms.openlocfilehash: 89b89a0cb056a0515bf0859069455a73f62aae4a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769617"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="c4e0c-102">Método IXCLRDataProcess::EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="c4e0c-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="c4e0c-103">Enumera las instancias de método de este proceso empezando por un desplazamiento de dirección.</span><span class="sxs-lookup"><span data-stu-id="c4e0c-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="c4e0c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4e0c-104">Syntax</span></span>

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="c4e0c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c4e0c-105">Parameters</span></span>

`handle`\
<span data-ttu-id="c4e0c-106">[in] Un identificador para enumerar las instancias de método.</span><span class="sxs-lookup"><span data-stu-id="c4e0c-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="c4e0c-107">[out] La instancia de método enumerado.</span><span class="sxs-lookup"><span data-stu-id="c4e0c-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="c4e0c-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c4e0c-108">Remarks</span></span>

<span data-ttu-id="c4e0c-109">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la fecha del 28 de ranura de la tabla de métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="c4e0c-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="c4e0c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4e0c-110">Requirements</span></span>

<span data-ttu-id="c4e0c-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4e0c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="c4e0c-112">**Encabezado**: None</span><span class="sxs-lookup"><span data-stu-id="c4e0c-112">**Header:** None</span></span>   
<span data-ttu-id="c4e0c-113">**Biblioteca:** None</span><span class="sxs-lookup"><span data-stu-id="c4e0c-113">**Library:** None</span></span>   
<span data-ttu-id="c4e0c-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c4e0c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   
 
## <a name="see-also"></a><span data-ttu-id="c4e0c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4e0c-115">See also</span></span>

- [<span data-ttu-id="c4e0c-116">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="c4e0c-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="c4e0c-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="c4e0c-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="c4e0c-118">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="c4e0c-118">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
