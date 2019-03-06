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
ms.openlocfilehash: 072e775d11d44dfbca27f1616889e388ae61d467
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366002"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a><span data-ttu-id="38848-102">Método IXCLRDataProcess::EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="38848-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="38848-103">Libera los recursos utilizados por los iteradores internos usa durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="38848-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="38848-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38848-104">Syntax</span></span>

```
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="38848-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="38848-105">Parameters</span></span>

`handle`\
<span data-ttu-id="38848-106">[out] Un identificador para enumerar las instancias de método.</span><span class="sxs-lookup"><span data-stu-id="38848-106">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="38848-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="38848-107">Remarks</span></span>

<span data-ttu-id="38848-108">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura de 29 de la tabla de métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="38848-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 29th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="38848-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="38848-109">Requirements</span></span>

<span data-ttu-id="38848-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38848-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="38848-111">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="38848-111">**Header:** None</span></span>  
<span data-ttu-id="38848-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="38848-112">**Library:** None</span></span>  
<span data-ttu-id="38848-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="38848-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="38848-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="38848-114">See also</span></span>

- [<span data-ttu-id="38848-115">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="38848-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="38848-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="38848-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="38848-117">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="38848-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
